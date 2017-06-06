# ansible-cabot
An Ansible role to build Cabot from source and deploy it.

## Usage

You need to provide an environment file for Cabot.

```
- role: cabot
  vars:
    cabot_config_file_path: templates/cabot.production.env
  tags: cabot
```
