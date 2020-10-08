# Docker on Ubuntu 20.04

This playbook will install Docker an Ubuntu 20.04 machine, as explained in the guide on
[How to Use Ansible to Install and Set Up Docker on Ubuntu 18.04](https://www.digitalocean.com/community/tutorials/how-to-use-ansible-to-install-and-set-up-docker-on-ubuntu-18-04).

# macosx

https://spinupwp.com/automating-server-setup-ansible/

```bash
brew install ansible
```

in work dir setup:

- hosts
- ansible.cfg

```bash
ansible-playbook -u root bedrock-server/ansible/setup_ubuntu/playbook.yml
```

optional: run docker container manually

```bash
docker create --name=minecraft   -v "/root:/backup"   -v "/root/bedrock-server/config:/bedrock-server/config"   -v "/root/bedrock-server/worlds:/bedrock-server/worlds"    -v "/root/bedrock-server/behavior_packs:/bedrock-server/behavior_packs"   -v "/root/bedrock-server/resource_packs:/bedrock-server/resource_packs"   -p 19132:19132/udp      --restart=unless-stopped   mmatiaschek/bedrock-server:v1.16.40.02
 #  docker start minecraft
 #  docker restart minecraft
 #  docker exec -ti minecraft bash
