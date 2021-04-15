# Windows OpenStack Imaging Tools

`windows-openstack-imaging-tools` là 1 PowerShell module tự động tạo image Windows cho OpenStack và hỗ trợ loại image sau:
- VHDX
- QCOW2
- RAW
- VMDK

Để cài đặt dễ dàng, tool được published dưới dạng PowerShellGallery module WindowsImageBuilder.

Ví dụ build image Windows:
```sh
Install-Module WindowsImageBuilder -Force
Import-Module WindowsImageBuilder
New-WindowsImageConfig -ConfigFilePath ".\windows-image-config.ini"
New-WindowsOnlineImage -ConfigFilePath ".\windows-image-config.ini"
```

Yêu cầu:

- Máy Windows được enable **Hyper-V virtualization**, hỗ trợ **PowerShell >=v4** và **Windows Assessment** và **Deployment Kit (ADK)**.
- Bản ISO hoặc DVD Windows installation.
- Windows compatible drivers, nếu môi trường yêu cầu. Ví dụ: **VirtIO**, **network card**, hoặc **storage adapter drivers**.
- Git environment.

## Tài liệu tham khảo
- https://docs.openstack.org/image-guide/create-images-automatically.html#windows-openstack-imaging-tools
- https://github.com/cloudbase/windows-openstack-imaging-tools
