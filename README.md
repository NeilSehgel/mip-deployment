# MIP-LOCAL Deployment Guide

## Introduction

The main objective of this pack is to provide you with the information and guidance needed to successfully install MIP.

This pack contains two sets of metadata and data for the following medical conditions:
  - Dementia
  - Trauma Brain Injury

This pack does not contain the data pre-processing tools (Data Factory) that are used to prepare your data and metadata.

## System Requirements

The server must be set up according to the MIP Technical Requirements and must be in a clean state.

It should also have:
  - git
  - docker (tested using version 17.05.0-ce)
  - docker-compose (tested using version 1.17.0)
  - python (2.7)

If you want your MIP installation to be accessible externally you should follow this ports configuration <a href="./documentation/PortsConfiguration.md">guide</a>.

## How to add Custom Data

You can follow this <a href="./documentation/NewDataRequirements.md">guide</a>.

## Deploy

Clone this repository.
Execute `sudo ./run.sh` script to install all the components.

*If at any point during the creation of docker networks (mip_backend,mip_frontend) encounter this error:*
```Creating network "mip_*" with the default driver
ERROR: Failed to program FILTER chain: iptables failed: * DOCKER: iptables v1.6.1: Couldn't load target `DOCKER':No such file or directory

Try `iptables -h' or 'iptables --help' for more information.
 (exit status 2)
```

*try restarting docker as so:*
```sudo systemctl restart docker```

## Test

After the installation is done, MIP will be visible on localhost. To verify everything is working properly go to http://localhost and
  - Check that 2 medical conditions (dementia and TBI) are visible,
  - and that 5 datasets are accessible (4 in dementia and 1 in TBI).

You can login with the default user:
```
username: user
password: password
```



If everything is working properly you should configure the users following this <a href="./documentation/UsersConfiguration.md">guide</a>.

Enjoy!

