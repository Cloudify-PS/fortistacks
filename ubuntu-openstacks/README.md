# This folder contains how to deploy openstack on fortistacks

To deploy mitaka:

./deploy-openstack

This script will wait for completion.

You follow with juju gui or watch -c juju status --color

Get the linux images to upload:
./get-cloud-images

Once done:
./configure-openstack

You openstack will all set.

Use juju status openstack-dashboard to find the IP adress of the openstack GUI.
Can find it in juju gui.

Install a fresh ubuntu 16.04 with a 100G available free linux
partition or disk.
On a single disk machine go in advance mode for disk to ensure
you create a 100G minimum free partition. (Can be done after install
for power users).

## Run this scripts ##

on your newly installed Ubuntu:
```shell

git clone https://github.com/fortinet-solutions-cse/fortistacks.git

cd fortistacks

./fortistacks -p /dev/sdaX sudoers install desktop
```

Be sure to replace /dev/sdaX with a free to use partition.

## What's now ##

Now you have a lxd ready ubuntu, sudo without passwd and access it
from MacOSX and windows vnc://<IP of fortistacksxs>


Every other step is in its onw folder with a README.md in it.

The first instance of this project contains a openstack mitaka on
ubuntu you can use:

`cd ubuntu-openstack`
`./deploy.sh`
will take some time (like 40mins) monitor with
`watch -c juju status --color`

Fortigate/Fortios folders deal with fortinet products on openstack/heat.

Cloudify deal with a full MANO implementation and blueprint.

Check the README in every folder for details. Those can be used on public or personnal real openstack with minimum adaptation.

##For v1.1
A full explanation/follow along video is available here: https://youtu.be/0y38B61FTSk
For v1.0 :
Previous version https://vimeo.com/215625341 (to see rift.io)

Is a collection of scripts and pre defined setups for running a full
stack of software (openstack, container, later kubernetes, etc..)
orchestrators.

It is based on LXC containers (LXD) on ubuntu 16.04 minimum that
provides a way to simulate 20+ machines in a beefy vm, a small machine
like intel nuc or others.
