# Ansible-Playbook

### Install Ansible on your control node.

'''
sudo apt update && sudo apt install -y ansible  # For Ubuntu
sudo yum install -y ansible                   # For CentOS/RedHat
'''

### Inventory File: Define target servers in the inventory file (e.g., /etc/ansible/hosts)

'''
[webservers]
server1 ansible_host=192.168.1.10 ansible_user=ubuntu ansible_ssh_private_key_file=~/.ssh/id_rsa
server2 ansible_host=192.168.1.11 ansible_user=ubuntu ansible_ssh_private_key_file=~/.ssh/id_rsa
'''

### Generate an SSH key pair on the Ansible control node.

'''
ssh-keygen -t rsa -b 4096  # Save the key pair in the default location (~/.ssh/id_rsa).
'''

### copy the public key (~/.ssh/id_rsa.pub) to the ~/.ssh/authorized_keys file of the user account on each managed node.

'''
ssh-copy-id user@<managed_node_ip_or_hostname>
'''

### Test Connectivity with Ansible

'''
ansible all -m ping
'''

### Run the playbook:

'''
ansible-playbook ping_test.yml
'''