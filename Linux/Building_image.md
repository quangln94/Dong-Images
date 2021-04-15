# Building image

## 1. VM Image

Image được tạo là 1 file qcow2 `image.qcow2`, nó chứa HĐH và có thể boot.

## 2. Elements

 Elements là những thứ quyết định cái gì sẽ có trong image và những chỉnh sửa sẽ được thực hiện.
 
Một số elements cung cấp `root filesystem` như `ubuntu` hoặc `fedora`, các `elements` khác sẽ sửa đổi image. Ít nhất 1 trong các `distro elements` phải được chỉ định khi thực hiện build image. Có thể tự tạo ra các `elements`.

Element `vm` để đảm bảo iamge có `bootloader` được cài đúng cách. Điều này chỉ cần thiết cho các trường hợp sử dụng nhất định và các định dạng đầu ra nhất định và do đó nó không được thực hiện theo mặc định
This is only needed for certain use cases and certain output formats and therefore it is not performed by default.
