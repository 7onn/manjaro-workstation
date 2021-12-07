# arch-env
This repository stores Ansible roles and playbooks for bootstrapping my computers

> I'm too lazy to install Arch from scratch, so I rely on [ArchLabs](https://archlabslinux.com/), which provides a GUI for partitioning the disk, setting up users, groups, WiFi, etc.


# Requirements
```bash
sudo pacman -Sy ansible ansible-lint openssh sshpass
systemctl enable sshd.service
systemctl start sshd.service
```

# Installation
Once the requirements are fulfilled run the following commands
```bash
# Clone the repository
git clone https://github.com/7onn/arch-env.git

# Edit the variables accordingly
$EDITOR vars/ansible.yml

# Run the playbook
ansible-playbook -Kk \
		 -u $(whoami) \
		 -i 'localhost,' \
		 --extra-vars "@vars/ansible.yml" \
		 playbook.yml
```

# LICENSE

[GNU General Public License v3.0](./LICENSE)