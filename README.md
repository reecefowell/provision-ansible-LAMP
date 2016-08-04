README
---

Configuration
---

Copy dist file of required inventory file, for example `ansible/inventories/*.ini.dist`, without the .dist extension.

Make changes to the inventory file copy as necessary.

Running
---

Run dev on remote machine over SSH when user preconfigured in inventory
`ansible-playbook ./playbook-dev.yml -i ./inventories/dev-remote.ini -v`

Run dev on remote machine over SSH with password
`ansible-playbook ./ansible/playbook-dev.yml -i ansible/inventories/dev-remote.ini -vvvv --ask-sudo-pass --user=reece --ask-pass`

Run dev on remote machine over SSH with public key
`ansible-playbook ./ansible/playbook-dev.yml -i ansible/inventories/dev-remote.ini -vvvv --ask-sudo-pass --user=reece`

Run dev on remote machine over ssh with unsafe settings
`ansible-playbook ./ansible/playbook-dev.yml -i ansible/inventories/dev-remote.ini -vvvv --ask-sudo-pass --user=reece -e 'unsafe=true'`

Run dev on local machine
`ansible-playbook ./ansible/playbook-dev.yml -i ansible/inventories/dev-remote.ini -vvvv --ask-sudo-pass --connection=local -e 'unsafe=true'`
