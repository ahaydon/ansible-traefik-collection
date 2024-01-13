Ansible Role: Traefik HTTP Service
=========

An Ansible role for creating Traefik configs for forwarding to upstream HTTP services.

Requirements
------------

Traefik must be configured to watch the directory where the configs will be placed, this is setup automatically when using the `traefik_podman` role from this collection.

Role Variables
--------------

```yaml
traefik_http_service_config_dir: /home/traefik/config/conf.d
traefik_http_service_name: homeassistant
traefik_http_service_fqdn: hass.mydomain.tld
traefik_http_service_url: http://homeassistant.local:8123
traefik_http_service_owner: traefik
traefik_http_service_group: traefik
```

Dependencies
------------

None.

Example Playbook
----------------

```yaml
- name: Add Home Assistant service to Traefik
  hosts: all
  roles:
    - role: traefik_http_service
      traefik_http_service_name: homeassistant
      traefik_http_service_fqdn: hass.mydomain.tld
      traefik_http_service_url: http://homeassistant.local:8123
```

License
-------

MIT

Author Information
------------------

This role was created by [Adam Haydon](https://github.com/ahaydon)
