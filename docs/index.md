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

## Create a VM

We'll create a VM using VirtualBox as Vagrant provider,
and Ansible will be used to setup devstack configuration.

```
$ vagrant up --provision
...
<url - dashboard>
```

Enter into the VM and check it out the configuration and services:

```
$ vagrant ssh
$ [devstack] : screen
```

## Use external OS clients

Take a look at : <http://engapa.gituhb.io/osc-docker-builder>

Just add the endpoint and credentials of our devstack into ***clouds.yml*** file,
 run the container and use its openstack client

## Authors

Enrique Garcia Pablos <engapa@gmail.com>