# Building image

## 1. VM Image

Image được tạo là 1 file qcow2 `image.qcow2`, nó chứa HĐH và có thể boot.

## 2. Elements

 Elements là những thứ quyết định cái gì sẽ có trong image và những chỉnh sửa sẽ được thực hiện.
 
Một số elements cung cấp `root filesystem` như `ubuntu` hoặc `fedora`, các `elements` khác sẽ sửa đổi image. Ít nhất 1 trong các `distro elements` phải được chỉ định khi thực hiện build image. Có thể tự tạo ra các `elements`.

Element `vm` để đảm bảo iamge có `bootloader` được cài đúng cách. Điều này chỉ cần thiết cho các trường hợp sử dụng nhất định và các định dạng đầu ra nhất định và do đó nó không được thực hiện theo mặc định.

## 2. Output Formats

Mặc định image qcow2 được tạo bởi lệnh `disk-image-create`. Các formats đầu ra có thể được chỉ địng bằng cách sử dụng tham số`-t <format>`. Nhiều formats đầu ra có thể được chỉ định bằng dấu phầy. Formats bao gồm:
- qcow2
- tar
- tgz
- squashfs
- vhd
- docker
- raw

Khi building 1 image tgz, lưu ý rằng biến môi trường `DIB_GZIP_BIN` có thể đượng sử dụng để đặt thiết lập đường dẫn của file thực thi `gzip`.

## 3. Disk Image Layout

Disk image layout (số images, partitions, LVM, disk encryption) thi thoảng mêm được cài đặt trong quá trình build image build: hầu như không thể thay đổi sau này.

Hiện tại có 2 mặc định:

- Khi sử dụng element `vm`, nên bao gồm `element` cung cấp `block-device`. Elements có sẵn `block-device-*` bao gồm trường hợp phổ biến của một phân vùng được lấp đầy toàn bộ và được sử dụng làm root device. Hiện tại bao gồm `MBR`, `GPT` và `EFI`. Ví dụ để sử dụng `GPT disk`:

```sh
disk-image-create -o output.qcow vm block-device-gpt ubuntu-minimal
```

- Nếu không sử dụng element `vm`, 1 image filesystem không có phân vùng nào được tạo ra.

Nếu muốn chỉnh sửa file `block-device-default.yaml` từ 1 trong các elements `block-device-*`, đặt biến môi trường `DIB_BLOCK_DEVICE_CONFIG`. Biến này phải chứa dữ liệu cấu hình có cấu trúc YAML hoặc `file://` tham chiếu `URL` đến file cấu hình trên disk.

Có rất nhiều tùy chọn khác nhau cho các cấp độ khác nhau. Các phần sau đây mô tả chi tiết từng cấp độ.

## 4. General Remarks
