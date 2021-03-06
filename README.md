# Ansible Role: Kibana

[![Build Status](https://travis-ci.org/geerlingguy/ansible-role-kibana.svg?branch=master)](https://travis-ci.org/geerlingguy/ansible-role-kibana)

An Ansible Role that installs Kibana on RedHat/CentOS or Debian/Ubuntu.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    major_kibana_version: "5.x"

The version of kibana to install (major and minor only).

    kibana_server_port: 5601

# specify if playbook should open firewall port

    kibana_listen_external: true

# interface where kibana will respond to external request

    kibana_interface: "eth0"


The FQDN or IP address and port Kibana should use.

    kibana_elasticsearch_url: "http://localhost:9200"

The URL (including port) over which Kibana will connect to Elasticsearch.

## Dependencies

None.

# specify security settings

If your elasticsearch cluster is secured using x-pack you must specify those variables

    kibana_elasticsearch_url: "https://localhost:9200"

The URL (including port) over which Kibana will connect to Elasticsearch.

    kibana_use_xpack_authentication: false

Disable or enable x-pack security plugin (default to false)

    kibana_elasticsearch_username: "elastic"
    kibana_elasticsearch_password: "changeme"

If elasticsearch is protected with basic authentication, kibana needs to authenticate with Elasticsearch through proxy.


## Example Playbook

    - hosts: kibana
      roles:
        - kibana

## License

MIT / BSD

## Author Information

This role was created in 2014 by [Jeff Geerling](https://www.jeffgeerling.com/), author of [Ansible for DevOps](https://www.ansiblefordevops.com/). Modified by Eric Caron in 2017.
