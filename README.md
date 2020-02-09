Role Name
=========

podman

[![Build Status](https://travis-ci.org/cmihai-ansible/podman.svg?branch=master)](https://travis-ci.org/cmihai-ansible/podman)

Ansible galaxy:
---------------

[https://galaxy.ansible.com/devopstoolbox.podman](https://galaxy.ansible.com/devopstoolbox.podman)

```bash
ansible-galaxy install devopstoolbox.podman
```

Requirements
------------

- For RHEL, a Red Hat subscription or functional local repository.

Role Variables
--------------

```
podman_remove_packages: true
podman_copy_templates: true
podman_max_user_namespaces: 10000
podman_user: devops
podman_subuid: 100000
podman_subgid: 65536
```

Dependencies
------------

- For Red Hat, subscription-manager.

Example Playbook
----------------

```yaml
---
- name: Install podman on localhost
  hosts:
    - localhost
  connection: local

  tasks:
    - name: podman is configured
      import_role:
        name: devopstoolbox.podman
      vars:
        podman_remove_packages: true
        podman_copy_templates: true
        podman_max_user_namespaces: 10000
        podman_user: devops
        podman_subuid: 100000
        podman_subgid: 65536
      tags: podman
```

License
-------

MIT

Author Information
------------------

- [Mihai Criveti](https://www.linkedin.com/in/devopstoolbox.)
