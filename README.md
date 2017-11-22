# ansible-cabot
[![Build Status](https://travis-ci.org/plumelo/ansible-role-cabot)](https://travis-ci.org/plumelo/ansible-role-cabot)
[![Galaxy](https://img.shields.io/badge/role-cabotapp.cabot-blue.svg?style=flat-square)](https://galaxy.ansible.com/cabotapp/cabot/)


An Ansible role to deploy Cabot using the Python packages.

## Usage

- Create a Cabot configuration file from the [example in the cabot repository](https://github.com/arachnys/cabot/blob/master/conf/production.env.example)
- (For all variables, take a look at defaults/main.yml)

## Role Variables

```yaml
# The cabot version
cabot_version: '0.11.8'

# The cabot user
cabot_user: 'cabot'

# The cabot env path
cabot_venv_path: '/home/{{ cabot_user }}/cabot.venv'

# The cabot log folder path
cabot_log_folder: '/var/log/cabot'

# The cabot config folder path
cabot_config_folder: '/home/{{ cabot_user }}/cabot.config'

# The cabot config file path
cabot_config_file: '{{ cabot_config_folder }}/config'

# The cabot template
cabot_config_template: 'cabot.config.j2'

# If you want to install postgresql with apt
cabot_install_postgres: yes

# Cabot database credentials
cabot_db: 'cabot'
cabot_db_user: 'cabot'
cabot_db_pass: 'cabot'

# If you want to install redis with apt
cabot_install_redis: yes

# Enable default plugins
cabot_plugins:
  - cabot_alert_email
  - cabot_alert_hipchat
  - cabot_alert_twilio
  - cabot_alert_slack
```

## Example

```yaml
- hosts: all
  become: yes
  vars:
    cabot_user: 'cabot'
    cabot_plugins:
      - cabot_alert_email
      - cabot_alert_hipchat
  roles:
    - role: ansible-role-cabot
      cabot_listen_address: 0.0.0.0
```

## Issues

If you have any problems using this role please make a github issue on [cabotapp/ansible-cabot](https://github.com/cabotapp/ansible-cabot/issues).

For any problems relating to Cabot itself, please make issues on [arachnys/cabot](https://github.com/arachnys/cabot/issues).
