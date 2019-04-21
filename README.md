# AnsibleCourse

cd group_vars/all

ansible-valut create vault =>password encryption- will ask to create the passphrase , then editor will open up to store the password and its value which will be storeed encrypted on host
ansible-vault edit vault => to edit it
ansible-plyabook --ask-valut-pass sites.yml
or store that passphraze in text file and edit the ansible.cfg for vault_pass_file path

ansible-playbook sites.yml

ansible-playbook --limit database sites.yml

ansible-playbook --limit 192.168.2.15 sites.yml => sites.yml will be executed only for host mentioned in limit and others will be skipped

TAG
sites.yml
Add tag to any task you want in yml file and then execute the playbok with the tag you desired and it will execute the only that task related to the tag mentioned

---
  - hosts: all
    become: yes
    tasks:
      - name: Tag example
        apt:
          name: curl
          update_cache: yes
        tags: [ 'packages' ]



ansible-playbook site.yml --tags "packages"

#To skip the installation and verification of packages you can add the tags "packages" to all the tasks with apt and the can skip it like below

ansible-playbook --skip-tags "packages" sites.yml


#To Jump to any particular task and then begin with execution from that task:

ansible-playbook sites.yml --list-tasks

ansible-playbook sites.yml --start-at-task "Name of the task"


#To have prompted for user response on the task like "yes/No" for the playbook execution. Use the following code

ansible-playbook sites.yml --step


#To check the syntax before executing file

ansible-playbook sites.yml --syntax-check
