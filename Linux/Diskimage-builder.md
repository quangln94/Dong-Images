# Disk Image Builder
Diskimage-builder is an automated disk image creation tool that supports a variety of distributions and architectures. Diskimage-builder (DIB) can build images for Fedora, Red Hat Enterprise Linux, Ubuntu, Debian, CentOS, and openSUSE. DIB is organized in a series of elements that build on top of each other to create specific images.

To build an image, call the following script:

# disk-image-create ubuntu vm
This example creates a generic, bootable Ubuntu image of the latest release.

Further customization could be accomplished by setting environment variables or adding elements to the command-line:

# disk-image-create -a armhf ubuntu vm
This example creates the image as before, but for arm architecture. More elements are available in the git source directory and documented in the diskimage-builder elements documentation.
