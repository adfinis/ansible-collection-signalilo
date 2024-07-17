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

### `adfinis.signalilo.signalilo`

Role uses Podman to extract Signalilo binary from Docker image or compiles it
locally and deploys it using systemd.

Extraction (`signalilo_from: docker`) or build (`signalilo_from: source`)
strategies both happen locally on the Ansible controller (localhost).

Requirements:

When `signalilo_from: docker`:

Playbook executor requires working Podman deployment on localhost (Ansible
controller)

When `signalilo_from: source`:

Playbook executor requires Go ecosystem and `make` pre-installed on localhost
(Ansible controller)

Configuration:

See `roles/signalilo/defaults/main.yml`

Example Playbook:

```yaml
- name: Deploy Gitlab
  hosts: signalilo_server
  tasks:
    - name: Import signalilo role
      ansible.builtin.import_role:
        name: adfinis.signalilo.signalilo
```

## License

[GPL-3.0-or-later](https://github.com/adfinis-sygroup/ansible-collection-signalilo/blob/main/LICENSE)

## Author Information

The Ansible collection `adfinis.signalilo` was written by:

* Adfinis AG | [Website](https://www.adfinis.com/) | [GitHub](https://github.com/adfinis)
