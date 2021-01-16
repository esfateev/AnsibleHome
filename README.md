1. Install Ansible:

    `sudo apt update`

    `sudo apt install software-properties-common`

    `sudo apt-add-repository --yes --update ppa:ansible/ansible`

    `sudo apt install ansible`

2. Clone Ansible-NAS:

    `git clone https://github.com/esfateev/home-ansible.git && cd home-ansible`

3. Create your own inventory and config files by copying `inventories/sample` to your own directory:

    `cp -rfp inventories/sample inventories/my-ansible`

4. Review `group_vars/all.yml`. Change settings by overriding them in `inventories/my-ansible/group_vars/server.yml`.

5. Update `inventories/my-ansible/inventory`.

6. Install the dependent roles: `ansible-galaxy install -r requirements.yml` (you might need `sudo` to install Ansible roles).

7. Run the playbook - something like `ansible-playbook -i inventories/my-ansible/inventory server.yml -b -K` should do you nicely.