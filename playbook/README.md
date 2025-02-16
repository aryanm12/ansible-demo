# Test connection to all servers

ansible all -i inventory -m ping

# Run the playbook using the local inventory file:

ansible-playbook -i inventory playbook.yml

# To run with specific tags:

# For Ubuntu nginx tasks
ansible-playbook -i inventory playbook.yml --tags nginx

# For RedHat tasks
ansible-playbook -i inventory playbook.yml --tags redhat

# To check syntax first:

ansible-playbook -i inventory playbook.yml --check