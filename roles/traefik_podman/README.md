Ansible Role: Traefik
=========

An Ansible role for deploying Traefik as a Podman container managed by systemd.

Requirements
------------

None.

Role Variables
--------------

```yaml
traefik_podman_name: traefik
traefik_podman_user: traefik
traefik_podman_group: "{{ traefik_podman_user }}"
traefik_podman_version: latest
traefik_podman_home: /home/traefik
traefik_podman_email: user.name@domain.tld
```

Dependencies
------------

- [ahaydon.podman](https://github.com/ahaydon/ansible-podman-collection) is used by the `traefik_podman` role.

Example Playbook
----------------

```yaml
- name: Deploy Traefik
  hosts: all
  roles:
    - role: traefik_podman
      traefik_podman_user: "{{ traefik_user }}"
      traefik_podman_home: "{{ podman_user_home }}"
      traefik_acme_email: adam.haydon@gmail.com
```

License
-------

MIT

Author Information
------------------

This role was created by [Adam Haydon](https://github.com/ahaydon)
