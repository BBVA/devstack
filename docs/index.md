# Devstack

Creates a complete Openstack environment by using Vagrant + Devstack + Ansible

## Build an image

Setup the custom configuration of Vagrant VM and devstack by editing the ***config.yaml*** file.

### VM parameters

We have a YAML file in order to get a separate configuration and Vagrant file.

Users could get their VM only changing parameters in YAML file.

Some examples of YAML files:

 - http://juliangut.com/blog/configure-vagrant-hosts-yaml
 - http://blog.scottlowe.org/2016/01/14/improved-way-yaml-vagrant/

### Devstack configuration

People who have launched a devstack VM know that there are a lot of variables.
We have tried collect almost all services and plugins in the YAML file and simplify the use ot them.


## Authors

Enrique Garcia Pablos <engapa@gmail.com>