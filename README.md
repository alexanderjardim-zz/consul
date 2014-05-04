consul
========

Consul is a tool for discovering and configuring services in your infrastructure. Much like Smart Stack from airbnb.com, but it promises to be simpler. This ansible roles aims to help instalation and configuration of Consul.

> http://www.consul.io/intro/index.html

You must keep in my mind three things when you use my roles:

1. All my roles make the assumption that host machines don't have internet connection, as this is the standard behavior of production machines in most companies. So, all the necessary dependencies will be downloaded to the control machine and after that pushed to the host machines. Keep in mind that you will need disk space for these downloads on your control machine.
1. I try to not use any package manager, at all. This way, you will not depend on more than one maintainer for the same software (the software original writer, and the package management team). Going this way, it is your choice to install using root or not. Which I always advise to don't use, if you can.
1. I try to keep all of my roles free from sudo or root access. If you wan't to use root, it is choice and not an specific demand, and I will keep this way as long as I can.


Requirements
------------

unzip

Role Variables
--------------

- **consul_version:** default to _'0.2.0'_
- **consul_download_dir:** download path on control machine. defaults to _'/tmp'_
- **consul_instalation_dir:** consul instalation path at host machines. defaults to  _'/home/vagrant/consul'_

Dependencies
------------

none

Example Playbook
-------------------------

```
    - hosts: all
      roles:
         - { role: alexanderjardim.consul }
```

License
-------

BSD

Author Information
------------------

alexander.ramos.jardim+consul@gmail.com
