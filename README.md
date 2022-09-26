# workshop-examples
Ansible Workshop Example Playbooks for Security Automation

Repositories:
https://github.com/ansible-collections/ibm.qradar
https://github.com/ansible-security/ids_rule/blob/master/tasks/snort.yml

# Sample inventory

[all:vars]
ansible_user=student1
ansible_ssh_pass=XJ3j16egwwbzwI
ansible_port=22

[control]
ansible ansible_host=52.14.175.192 private_ip=172.16.121.254

[attack]
attacker ansible_host=3.135.202.35 ansible_user=ec2-user private_ip=172.16.204.161 private_ip2=172.17.84.100

[siem]
qradar ansible_host=18.119.140.241 ansible_user=admin private_ip=172.16.174.91 ansible_httpapi_pass="Ansible1!" ansible_connection=httpapi ansible_httpapi_use_ssl=yes ansible_httpapi_validate_certs=False ansible_network_os=ibm.qradar.qradar

[ids]
snort ansible_host=3.133.115.162 ansible_user=ec2-user private_ip=172.16.76.30 private_ip2=172.17.114.115

[firewall]
checkpoint ansible_host=18.217.232.86 ansible_user=admin ansible_password=admin123 private_ip=172.16.243.169 ansible_network_os=checkpoint ansible_connection=httpapi ansible_httpapi_use_ssl=yes ansible_httpapi_validate_certs=no

[windows]
windows-ws ansible_host=3.145.45.246 ansible_user=Administrator ansible_pass=qZI8UhDjw9e98A ansible_port=5986 ansible_connection=winrm ansible_winrm_server_cert_validation=ignore private_ip=172.16.96.137

# SQL Injection workflow

Roll back all changes

Whitelist attacker

IR - Add snort rule

IR - Start SQL injection attack

IR - Forward snort logs to QRadar

     or use separate playbooks
