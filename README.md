README
---

Run dev on remote machine over SSH with password
`ansible-playbook ./ansible/playbook-dev.yml -i ansible/inventories/dev-remote.ini --user=reece --ask-pass --ask-sudo-pass -vvvv`

Run dev on remote machine over SSH with public key
`ansible-playbook ./ansible/playbook-dev.yml -i ansible/inventories/dev-remote.ini --user=reece --ask-sudo-pass -vvvv`

Run with unsafe settings
`ansible-playbook ./ansible/playbook-dev.yml -i ansible/inventories/dev-remote.ini --user=reece --ask-sudo-pass -e 'unsafe=true' -vvvv`
