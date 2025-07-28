# ansible-role-libvirt-openshift

To make this role work ensure user has permissions to create VMs and list VMs
```bash
sudo usermod -aG libvirt $(whoami)
echo "export LIBVIRT_DEFAULT_URI=qemu:///system" >> ~/.bashrc
source ~/.bashrc
```
Not try to list the networks with the user
```bash
virsh net-list --all
 Name      State    Autostart   Persistent
--------------------------------------------
 default   active   yes         yes
```
