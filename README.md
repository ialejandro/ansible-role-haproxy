# Ansible Role: HAProxy

Installs and configures [HAProxy](http://www.haproxy.org/), an open-source high availability load balancer and proxy server.

## Requirements

- Ansible 2.10+
- Supported platforms:
  - Amazon Linux
  - Other platforms might be supported but have not been tested.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml` and `vars/main.yml`):

### General

- `haproxy_version`: The version of HAProxy to install.
  - **Default**: `2.4`
  - **Example**:
    ```yaml
    haproxy_version: 2.4
    ```

- `haproxy_install_dir`: The directory where HAProxy will be installed.
  - **Default**: `/etc/haproxy`
  - **Example**:
    ```yaml
    haproxy_install_dir: /etc/haproxy
    ```

- `haproxy_user`: The user that will run HAProxy.
  - **Default**: `haproxy`
  - **Example**:
    ```yaml
    haproxy_user: haproxy
    ```

### Logging

- `haproxy_log_level`: Log level for HAProxy.
  - **Default**: `info`
  - **Example**:
    ```yaml
    haproxy_log_level: debug
    ```

### Load Balancing

- `haproxy_balance_algorithm`: The load balancing algorithm.
  - **Default**: `roundrobin`
  - **Example**:
    ```yaml
    haproxy_balance_algorithm: leastconn
    ```

## Dependencies

None.

## Example Playbook

```yaml
- hosts: all
  roles:
    - role: ansible-role-haproxy
      haproxy_version: "2.4"
      haproxy_user: "haproxy"
      haproxy_balance_algorithm: "leastconn"
```

## License

MIT

## Author Information

This role was created by [ialejandro](https://github.com/ialejandro).
