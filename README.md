Role Name
=========

[![Build Status](https://travis-ci.org/Mohitsharma44/ansible-supervisord.svg?branch=master)](https://travis-ci.org/Mohitsharma44/ansible-supervisord)

Asible Role for installing and configuring Supervisord

Requirements
------------

N/A

Role Variables
--------------

Following variables are required for configuring and installing Supervisord

``` yaml
# version of supervisor to be installed
supervisor_version: latest

# to run supervisor in foreground?
supervisor_nodaemon: false

# to start and enable supervisord at boot
supervisor_started: true
supervisor_enabled: true

# configuration paths for supervisord
supervisor_conf_dir: /etc/supervisord
supervisor_bin_path: /usr/local/bin/
supervisorctl_bin_path: /usr/local/bin/
supervisor_log_dir: /var/log/supervisor

# sample configuration for program using supervisor
supervisor_programs: []
#  - name: cuiccapture
#    command: command=/opt/pleora/ebus_sdk/Ubuntu-14.04-x86_64/share/samples/cuic/src/cuiccapture
#    configuration: |
#      environment=PUREGEV_ROOT=/opt/pleora/ebus_sdk/Ubuntu-14.04-x86_64,GENICAM_ROOT=%(ENV_PUREGEV_ROOT)s/lib/genicam,GENICAM_ROOT_V2_4=%(ENV_GENICAM_ROOT)s
#      numprocs=1
#      autostart=false
#      autorestart=true
#      startsecs=3
#      startretries=10
#      redirect_stderr=true
#      stdout_logfile_maxbytes=10MB
#      stdout_logfile=
#      stderr_logfile=
#      stderr_logfile_backups=10
#      stderr_logfile_maxbytes=10MB

# Authentication if required
supervisor_user: root
supervisor_password: '1change_me_please1'

# enable and configure unix socket for supervisor
supervisor_unix_http_enable: true
supervisor_unix_http_sock_path: /var/run/supervisor.sock
supervisor_unix_http_protect: true

# enable and configure supervisor http server
supervisor_inet_http_enable: false
supervisor_inet_http_port: '*:9001'
supervisor_inet_http_protect: true
```

Dependencies
------------

(To be verified)

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

``` yaml
- hosts: localhost
  vars: <above mentioned vars>
  roles:
    - mohitsharma44.ansible_supervisord
```

License
-------

MIT

Author Information
------------------

Mohit Sharma (Mohitsharma44@gmail.com)
