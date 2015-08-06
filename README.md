Ansible NTP Role
================
[![Build Status](https://semaphoreci.com/api/v1/projects/f88d8675-d744-492e-911d-0ff92d987107/461763/badge.svg)](https://semaphoreci.com/michaelrigart/ansible-role-ntp) [![Build Status](https://travis-ci.org/michaelrigart/ansible-role-ntp.svg?branch=master)](https://travis-ci.org/michaelrigart/ansible-role-ntp)

An ansible role for installing and configuring NTP.

For more information on NTP, [visit the NTP website](http://www.ntp.org)

Role Variables
--------------

```yaml
ntp_pkg_version: specify the specific package version you wish to install
ntp_pkg_state: indicates the package state; Allowed setting: installed, latest. When specifying a version, the state will be forced to installed. When omitting the variable or leaving it empty it will install the package as specified by the state variable
ntp_service_state: indicates the service state; Allowed setting: started, stopped
ntp_service_enabled: indicates if service needs to be enabled on boot; Allowed settings: yes, no
ntp_driftfile: location of the drift file
ntp_servers: list of NTP servers to use
ntp_restrict: list of NTP restrictions
ntp_crypto: enable / disable usage of cryptography type
ntp_keys: location of the keys file
ntp_trustedkey: specify the key identifier which are trusted
ntp_requestkey: speciy the key identifier to use with the ntpdc
ntp_controlkey: Specifies the key identifier to use with the ntpq
ntp_includefile: location of a an ntp file that needs to be included
ntp_statistics: specify which statistics to enable
ntp_statsdir: specify location of statistics files
ntp_filegen: specify which statistics files to generate
ntp_broadcast: enable broadcast mode
ntp_broadcastclient: enable reception of broadcast server messages
ntp_disable: specify a list to disable various server options
ntp_enable: specify a list to enable various server options
ntp_manycastserver: enable reception of manycast client messages
ntp_multicastclient: enable reception of multicast server messages
```

View the default vars - defaults/main.yml - for a more detailed example.

Example Playbook
-------------------------

```yaml
- hosts: servers
  roles:
     - { role: MichaelRigart.ntp, sudo: Yes }
```

License
-------

GPLv3

Author Information
------------------

Michaël Rigart <michael@netronix.be>
