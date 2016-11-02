HAProxy
=========

> Setup HAProxy with splited config files

Requirements
------------

- Ansible 2.x

Role Variables
--------------

```yaml
haproxy_frontends:
  http_front:
  - bind *:80
  - default_backend http_back
  custom_front:
  - bind *:8081
  - default_backend http_back
haproxy_backends:
  http_back:
  - balance roundrobin
  - server http1 127.0.0.1:8000 check
  - server http2 127.0.0.1:8001 check
```

Dependencies
------------

All dependencies are bundled in `meta/main.yml`

Example Playbook
----------------

```yaml
- hosts: haproxy
  vars:
    haproxy_frontends:
      http_front:
      - bind *:80
      - default_backend http_back
    haproxy_backends:
      http_back:
      - balance roundrobin
      - server http1 10.0.0.1:80 check
      - server http2 10.0.0.2:80 check

  roles:
  - role: SimpliField.haproxy
```

License
-------

BSD
