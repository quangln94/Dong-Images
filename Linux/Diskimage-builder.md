# Disk Image Builder
Diskimage-builder laf 1 tool tự động tạo image hỗ trợ nhiều bản distributions và architectures. 

Diskimage-builder (DIB) có thể build images cho:
 - Fedora
 - Red Hat Enterprise Linux
 - Ubuntu
 - Debian
 - CentOS
 - openSUSE
 
 DIB là tập hợp các `elements` được build chồng lên nhau để tạo ra các images cụ thể.

Để build 1 image Ubuntu phiên bản latest, thực hiện như sau:
```sh
disk-image-create ubuntu vm
```

Có thể thực hiện thêm các tùy chọn bằng cách thiết lập biết môi trường hoặc thêm các `elements` vào lệnh:
```sh
disk-image-create -a armhf ubuntu vm
```

## Tài liệu tham khảo
- https://docs.openstack.org/image-guide/create-images-automatically.html
- https://opendev.org/openstack/diskimage-builder/src/branch/master/diskimage_builder/elements
