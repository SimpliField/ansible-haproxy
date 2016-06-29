HAProxy
=========

Setup HAProxy

Requirements
------------

Need ansible 2

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

There is no dependencies

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
  - role: SimpliField.haproxy
```

License
-------

BSD
