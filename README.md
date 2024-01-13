# Ansible Collection for Traefik

This collection includes roles to deploy Traefik with Podman and systemd.

## Installation

The collection can be installed with `ansible-galaxy`:

```sh
ansible-galaxy collection install git+https://github.com/ahaydon/ansible-traefik-collection.git
```

## Usage

```yaml
- role: traefik_podman
  traefik_podman_user: traefik
  traefik_podman_home: /home/traefik
  traefik_podman_email: user.name@domain.tld

- role: traefik_http_service
  traefik_http_service_name: homeassistant
  traefik_http_service_url: http://{{ ansible_host }}:8123/
  traefik_http_service_fqdn: hass.local
```

## License

This Ansible collection is [MIT licensed](LICENSE).
