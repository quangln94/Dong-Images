# Building image

## 1. VM Image

Image được tạo là 1 file qcow2 `image.qcow2`, nó chứa HĐH và có thể boot.

## 2. Elements

 Elements là những thứ quyết định cái gì sẽ có trong image và những chỉnh sửa sẽ được thực hiện.
 
 Some elements provide a root filesystem, such as the ubuntu or fedora element in our example above, which other elements modify to create our image. At least one of these ‘distro elements’ must be specified when performing an image build. It’s worth pointing out that there are many distro elements (you can even create your own), and even multiples for some of the distros. This is because there are often multiple ways to install a distro which are very different. For example: One distro element might use a cloud image while another uses a package installation tool to build a root filesystem for the same distro.

Other elements modify our image in some way. The ‘vm’ element in our example above ensures that our image has a bootloader properly installed. This is only needed for certain use cases and certain output formats and therefore it is not performed by default.
