# ansible-cabot
[![Galaxy](https://img.shields.io/badge/role-cabotapp.cabot-blue.svg?style=flat-square)](https://galaxy.ansible.com/cabotapp/cabot/)


An Ansible role to deploy Cabot using the Python packages.

## Usage

- Create a Cabot configuration file from the [example in the cabot repository](https://github.com/arachnys/cabot/blob/master/conf/production.env.example)

- Use it as the role variable:

```
- role: cabot
  vars:
    cabot_config_file_path: files/cabot.production.env
  tags: cabot
```


## Issues

If you have any problems using this role please make a github issue on [cabotapp/ansible-cabot](https://github.com/cabotapp/ansible-cabot/issues).

For any problems relating to Cabot itself, please make issues on [arachnys/cabot](https://github.com/arachnys/cabot/issues).
