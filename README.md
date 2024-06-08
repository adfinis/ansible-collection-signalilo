# Ansible Collection - adfinis.signalilo

![License](https://img.shields.io/github/license/adfinis/ansible-collection-signalilo)
![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/adfinis/ansible-collection-signalilo/ansible-lint.yml)
[![adfinis.signalilo on Ansible Galaxy](https://img.shields.io/badge/collection-adfinis.signalilo-blue)](https://galaxy.ansible.com/ui/repo/published/adfinis/signalilo/)


This role deploys Signalilo binary as systemd managed service.

To use the role add following to the `requirements.yml`:

```yaml
collections:
  - name: adfinis.signalilo
    version: 1.0.0
```

## Roles

### `adfinis.signalilo.signalilo_docker`

Role uses Podman to extract Signalilo binary from Docker image and deploys it using systemd. Configuration is done with setting environmental variables.

Example Playbook:

```yaml
- name: Deploy Gitlab
  hosts: signalilo_server
  tasks:
    - name: Import signalilo role
      ansible.builtin.import_role:
        name: adfinis.signalilo.signalilo_docker
```

### `adfinis.signalilo.signalilo_compile`

**NOT IMPLEMENTED**

Role compiles Signalilo binary and deploys it using systemd. Configuration is done with setting environmental variables. 

## License

[GPL-3.0-or-later](https://github.com/adfinis-sygroup/ansible-collection-signalilo/blob/main/LICENSE)

## Author Information

The Ansible collection `adfinis.signalilo` was written by:

* Adfinis AG | [Website](https://www.adfinis.com/) | [GitHub](https://github.com/adfinis)

