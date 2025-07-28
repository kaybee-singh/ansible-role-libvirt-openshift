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
To run role follow below steps.
```bash
git clone https://github.com/kaybee-singh/ansible-role-libvirt-openshift;cd ansible-role-libvirt-openshift
```
Modify hosts file and enter the VMs name which you want to create. Same vms will be created in the libvirt.
```bash
vim hosts
[ocp_vms]
bootstrap
master1
master2
master2
[ocp_vms:vars]
ansible_connection=local
```
Run the playbook
```bash
ansible-playbook playbook.yaml
```
