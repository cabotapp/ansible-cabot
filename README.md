# ansible-cabot
An Ansible role to build Cabot from source and deploy it.

## Usage

```
- role: cabot
  vars:
    cabot_config_file_path: templates/cabot.production.env
  tags: cabot
```
