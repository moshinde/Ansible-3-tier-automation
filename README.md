# AnsibleCourse

cd group_vars/all

ansible-valut create vault =>password encryption- will ask to create the passphrase , then editor will open up to store the password and its value which will be storeed encrypted on host
ansible-vault edit vault => to edit it
ansible-plyabook --ask-valut-pass sites.yml
or store that passphraze in text file and edit the ansible.cfg for vault_pass_file path

ansible-playbook sites.yml

ansible-playbook --limit database sites.yml

ansible-playbook --limit 192.168.2.15 sites.yml => sites.yml will be executed only for host mentioned in limit and others will be skipped

