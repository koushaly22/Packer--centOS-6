Packer Example - CentOS 6 minimal Vagrant Box using Ansible provisioner

Current CentOS Version Used: 6.8

Pre-built Vagrant Box:
* vagrant init geerlingguy/centos6
* See older versions: http://files.midwesternmac.com/

This example build configuration installs and configures CentOS 6 x86_64 minimal using Ansible, and then generates two Vagrant box files, for:

* VirtualBox
* VMware

The example can be modified to use more Ansible roles, plays, and included playbooks to fully configure (or partially) configure a box file suitable for deployment for development environments.

Requirements
The following software must be installed/present on your local machine before you can use Packer to build the Vagrant box file:
* Packer
* Vagrant
* VirtualBox (if you want to build the VirtualBox box)
* VMware Fusion (or Workstation - if you want to build the VMware box)
* Ansible


Usage
Make sure all the required software (listed above) is installed, then cd to the directory containing this README.md file, and run:
$ packer build centos6.json
After a few minutes, Packer should tell you the box was generated successfully.
If you want to only build a box for one of the supported virtualization platforms (e.g. only build the VMware box), add --only=vmware-iso to the packer build command:
$ packer build --only=vmware-iso centos6.json

Testing built boxes

There's an included Vagrantfile that allows quick testing of the built Vagrant boxes. From this same directory, run one of the following commands after building the boxes:
# For VMware Fusion:
$ vagrant up vmware --provider=vmware_fusion

# For VirtualBox:
$ vagrant up virtualbox --provider=virtualbox

License
MIT license.

