# Ansible Notes

---
## Requirements
* ansible
* python3
* sshpass

---
## Cheat Sheet
* ansible -i hosts all -m ping
* ansible -i hosts all -m ping --limit host2 # ping only host2
* ansible -i hosts all -m copy -a "src=/root/test_ansible/testfile dest=/tmp/testfile" # Copy the file "testfile" on all hosts in the inventory file 
* ansible -i hosts all -m yum -a 'name=ncdu state=present' # Install ncdu package on all hosts 
* ansible -i hosts all -m yum -a 'name=ncdu state=absent' # Remove ncdu package on all hosts 
* ansible-galaxy init role1 # Build the directory structure for role named role1
* ansible-playbook -i hosts p4.yml --check # Dry-run p4.yml playbook 
* ansible-playbook -i hosts p4.yml -k # Run p4.yml playbook with password authentication for all hosts 

---
## Inventory / Node Definitions
/etc/ansible/hosts

## Hosts File Entries
[ansible-group]
192.168.50.12 ansible_ssh_user=root ansible_ssh_pass=client001

## Check Syntax
ansible-playbook /etc/ansible/scripts/httpd.yml --syntax-check

## Push the commands in the playbook to the ansible-group hosts
ansible-playbook httpd.yml

---
## Playbook Information
* [create-file-with-perm.yaml](create-file-with-perm.yam): Creates new file with specified permissions.
* [create-multiple-files.yaml](create-multiple-files.yaml): Creates multiple files.
* [del-and-recreate-file.yaml](del-and-recreate-file.yaml): Delete and recreate a file.
* [del-multiple-files.yaml](del-multiple-files.yaml): Delete multiple files.
* [delete-file.yaml](delete-file.yaml): Delete a file.
* [enable-selinux-httpd.yaml](enable-selinux-httpd.yaml): Enables SELinux and installs apache.
* [exec-date-install-httpd.yaml](exec-date-install-httpd.yaml): Execs date command then installs apache.
* [install-lldpad-package.yaml](install-lldpad-package.yaml): Installs lldpad.
* [install-run-httpd.yaml](install-run-httpd.yaml): Install and run apache.
* [mod-dns.yaml](mod-dns.yaml): DNS resolver modifier.
* [modify-line.yaml](modify-line.yaml): Modifies a line in a file.
