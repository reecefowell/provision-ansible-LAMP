README
---

Configuration
---

Copy dist file of required inventory file, for example `ansible/inventories/*.ini.dist`, without the .dist extension.

Make changes to the inventory file copy as necessary.


Running SSH setup on Remote Machine (by IP or inventory)
---

- `ansible-playbook playbook-ssh.yml -i '192.168.0.220,' --ask-sudo-pass --user=reece --ask-pass -vvvv -e 'remote_key=~/.ssh/scripts/ubuntu-14-vm/keys/id_rsa_ubuntu14'`
- `ansible-playbook playbook-ssh.yml -i inventories/dev-remote.ini --ask-sudo-pass --user=reece --ask-pass -vvvv -e 'remote_key=~/.ssh/scripts/ubuntu-14-vm/keys/id_rsa_ubuntu14'`


Running NFS setup on Remote Machine (by IP or inventory)
---

- `ansible-playbook playbook-nfs.yml -i '192.168.0.220,' --ask-sudo-pass --user=reece -vvvv`
- `ansible-playbook playbook-nfs.yml -i inventories/dev-remote.ini --ask-sudo-pass --user=reece -vvvv`

To mount in Finder.app go to `Go` -> `Connect To Server` and type in `nfs://192.168.0.222:/home/reece/projects`


Running LAMP stack deploy on Remote Machine
---

Run dev on remote machine over SSH when user preconfigured in inventory (by IP or inventory)
- `ansible-playbook playbook-dev.yml -i '192.168.0.220,' --ask-sudo-pass -vvvv`
- `ansible-playbook playbook-dev.yml -i inventories/dev-remote.ini --ask-sudo-pass -vvvv`

Run dev on remote machine over SSH with password (by IP or inventory)
- `ansible-playbook playbook-dev.yml -i '192.168.0.220,' --ask-sudo-pass --user=reece --ask-pass -vvvv`
- `ansible-playbook playbook-dev.yml -i inventories/dev-remote.ini --ask-sudo-pass --user=reece --ask-pass -vvvv`

Run dev on remote machine over SSH with public key (by IP or inventory)
- `ansible-playbook playbook-dev.yml -i '192.168.0.220,' --ask-sudo-pass --user=reece -vvvv`
- `ansible-playbook playbook-dev.yml -i inventories/dev-remote.ini --ask-sudo-pass --user=reece -vvvv`

Run dev on remote machine over ssh with unsafe settings (by IP or inventory)
- `ansible-playbook playbook-dev.yml -i '192.168.0.220,' --ask-sudo-pass --user=reece -vvvv -e 'unsafe=true'`
- `ansible-playbook playbook-dev.yml -i inventories/dev-remote.ini --ask-sudo-pass --user=reece -vvvv -e 'unsafe=true'`

Run dev on local machine (by IP or inventory)
- `ansible-playbook playbook-dev.yml -i '192.168.0.220,' --connection=local --ask-sudo-pass --user=reece -vvvv -e 'unsafe=true'`
- `ansible-playbook playbook-dev.yml -i inventories/dev-local.ini --connection=local --ask-sudo-pass -vvvv -e 'unsafe=true'`
- `ansible-playbook playbook-dev.yml -i '192.168.0.220,' --ask-sudo-pass --user=reece -vvvv -e 'unsafe=true'`
- `ansible-playbook playbook-dev.yml -i inventories/dev-remote.ini --ask-sudo-pass --user=reece -vvvv -e 'unsafe=true'`

Sources
---

NFS
- https://www.digitalocean.com/community/tutorials/how-to-set-up-an-nfs-mount-on-ubuntu-14-04
- https://theredblacktree.wordpress.com/2013/02/16/nfs-shares-between-ubuntu-12-04-and-mac-osx-10-8/
