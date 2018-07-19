# Example of deploying Habarshi server


## Prerequirements
1. VirtualBox installed [https://www.virtualbox.org/](https://www.virtualbox.org/)
2. Vagrant installed [https://www.vagrantup.com/](https://www.vagrantup.com/)

## Steps to up virtual machines
1. Run command `vagrant up`. Wait for some time (about for 5 minutes according to your host machine performance)
2. You will see two virtual machines with names: `ansible-master` and `ansible-node`

## Steps to install **Habarshi** server and dependencies to vm named `node`
1. Go to ansible-master by SSH: `vagrant ssh master`
2. Go to `/vagrant` directory: `cd /vagrant`
3. Run `ansible-play site.yml` and wait some time (2-3 minutes)
4. You can see installed **Habarshi** server on host `192.168.33.11`, you can check that through browser (Moreover, you can go to `node` vm: `vagrant ssh node` and detect installed docker, docker-compose, nginx and habarshi docker containers).