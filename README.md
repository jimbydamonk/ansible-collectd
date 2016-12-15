# ansible-collectd
[![Build Status](https://travis-ci.org/jimbydamonk/ansible-collectd.svg?branch=master)](https://travis-ci.org/jimbydamonk/ansible-collectd)

Install and configure collectd.

Requirements
------------

NA

Role Variables
--------------

The default variables for this role are listed below. They are defined in defaults/main.yml`.

```yml
---
collectd_plugin_dir: "{{ dist_collectd_plugin_dir }}"

collectd_conf_dir: "{{ dist_collectd_conf_dir }}"
collectd_confd_dir: "{{ dist_collectd_confd_dir }}"
collectd_template_files: []

collectd_types_db_dir: "{{ dist_collectd_types_db_dir }}"
collectd_types_templates: []

collectd_plugins:
  - logfile
  - aggregation
  - cpu
  - df
  - disk
  - interface
  - load
  - memory

collectd_plugins_config:
  logfile:
    LogLevel: "info"
    File: "/var/log/collectd.log"
    Timestamp: true
    PrintSeverity: false
  aggregation:
    Aggregation:
      Plugin: "cpu"
      Type: "cpu"
      GroupBy: "Host"
      CalculateNum: true
      CalculateSum: true
      CalculateAverage: true
  df:
    ValuesPercentage: true

```

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

Apache

Author Information
------------------
Mike Buzzetti
