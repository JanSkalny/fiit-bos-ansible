# Asnible demo environment
- `git clone` 
- `docker compose up`
- `docker exec --workdir /root/ -it ansible bash`
- you can ssh to to jump host using user:krokodil
- other hosts such (ie. web and files) are reachable via jump host 
- root home dir of ansible host is persisted under ansible/
- if you wan't to start over, run `docker compose down` and empty ansible/ directory


## TODO
1. generate your ssh key on ansible host using `ssh-keygen -t ed25519`
2. prepare ~/.ssh/config with User, ProxyJump and StrictHostKeyChecking vars
3. disribute your ssh key using ssh-copy-id
4. allow sudo wo/ passwords for %sudo group users, eg.
   ```
   echo '%sudo ALL=(ALL:ALL) NOPASSWD:ALL' > /etc/sudoers.d/nopasswd
   ```
5. install ansible
6. write your inventory.yml and ansible.cfg
7. test ansible connectivity using `ansible -m ping all`
8. challange: deploy sudoers, authorized_keys and other ansible depedencies using sshpass and "initial" playbook using `raw` modules

