# Devstack

Creates a complete Openstack environment by using Vagrant + Devstack + Ansible

## VM parameters

We have a YAML file in order to get a separate configuration of the Vagrantfile.

Users could get their VM only changing parameters in YAML file.

Some examples of YAML files:

 - <http://juliangut.com/blog/configure-vagrant-hosts-yaml>
 - <http://blog.scottlowe.org/2016/01/14/improved-way-yaml-vagrant/>

## Devstack configuration

People who have launched a devstack VM know that there are a lot of variables.
We have tried collect almost all services and plugins in the YAML file and simplify the use of them.

Devstack configuration is defined under the entry ***devstack*** in the YAML file.

If any plugin has a lot of env variables or another specific configuration it's possible to provide
custom jinja templates by ***env_file*** parameter.

## Create a VM

We'll create a VM using VirtualBox as Vagrant provider,
and Ansible will be used to setup devstack configuration.

```
$ vagrant up --provision
...
==> devstack: =========================
==> devstack: This is your host IP address: 192.168.10.10
==> devstack: This is your host IPv6 address: ::1
==> devstack: Horizon is now available at http://192.168.10.10/dashboard
==> devstack: Keystone is serving at http://192.168.10.10/identity/
==> devstack: The default users are: admin and demo
==> devstack: The password: enrique
==> devstack: 2016-12-19 14:21:53.960 | stack.sh completed in 1806 seconds.
```

Enter into the VM and check it out the configuration and services:

```
$ vagrant ssh
$ screen -ls
There is a screen on:
	12828.stack	(12/19/2016 01:51:42 PM)	(Detached)
1 Socket in /var/run/screen/S-vagrant.
$ screen -r 12828.stack
...
```

## Use external OS clients

Take a look at : <http://engapa.github.io/osc-docker-builder>

Just add the endpoint and credentials of our devstack into ***clouds.yml*** file,
 run the container and use its openstack client

## Authors

Enrique Garcia Pablos <engapa@gmail.com>