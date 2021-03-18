# Ansible Notes
## Requirements
ansible, python3, sshpass
---
# Cheat Sheet
ansible -i hosts all -m ping
ansible -i hosts all -m ping --limit host2 # ping only host2
ansible -i hosts all -m copy -a "src=/root/test_ansible/testfile dest=/tmp/testfile" # Copy the file "testfile" on all hosts in the inventory file 
ansible -i hosts all -m yum -a 'name=ncdu state=present' # Install ncdu package on all hosts 
ansible -i hosts all -m yum -a 'name=ncdu state=absent' # Remove ncdu package on all hosts 
ansible-galaxy init role1 # Build the directory structure for role named role1
ansible-playbook -i hosts p4.yml --check # Dry-run p4.yml playbook 
ansible-playbook -i hosts p4.yml -k # Run p4.yml playbook with password authentication for all hosts 
---
# Inventory / node definitions
/etc/ansible/hosts

# Hosts file entries
[ansible-group]
192.168.50.12 ansible_ssh_user=root ansible_ssh_pass=client001

# Check syntax
ansible-playbook /etc/ansible/scripts/httpd.yml --syntax-check

# Push the commands in the playbook to the ansible-group hosts
ansible-playbook httpd.yml
---

# Playbook information
[create-file-with-perm.yaml](create-file-with-perm.yam)
[create-multiple-files.yaml
[del-and-recreate-file.yaml]
[del-multiple-files.yaml]
[delete-file.yaml]
[enable-selinux-httpd.yaml]
[exec-date-install-httpd.yaml]
[install-lldpad-package.yaml]
[install-run-httpd.yaml]
[mod-dns.yaml]
[modify-line.yaml]
