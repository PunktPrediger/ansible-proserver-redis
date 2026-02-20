<!-- BEGIN_ANSIBLE_DOCS -->
<!--
Do not edit README.md directly!

This file is generated automatically by aar-doc and will be overwritten.

Please edit meta/argument_specs.yml instead.
-->
# ansible-proserver-redis

redis role for Proserver

## Supported Operating Systems

- Debian 12, 13
- Ubuntu 24.04, 22.04
- FreeBSD [Proserver](https://infrastructure.punkt.de/de/produkte/proserver.html)

## Role Arguments



#### Options for `redis`

|Option|Description|Type|Required|Default|
|---|---|---|---|---|
| `prefix` | Path and naming prefixes (config directory, etc.). | dict of 'prefix' options | no |  |
| `service` | System service names for Redis server and Sentinel. | dict of 'service' options | no |  |
| `redis.conf` | Redis server configuration as key-value pairs. Each key is written to redis.conf with the given value. Empty or false values remove the line. | dict | no |  |
| `sentinel.conf` | Redis Sentinel configuration as key-value pairs. Each key is written to sentinel.conf. Only used when redis.replication.sentinel is true. | dict | no |  |
| `replication` | Replication and Sentinel options. | dict of 'replication' options | no |  |

#### Options for `redis.prefix`

|Option|Description|Type|Required|Default|
|---|---|---|---|---|
| `config` | Directory containing redis.conf and sentinel.conf. Defaults to /etc/redis on Linux and /usr/local/etc on FreeBSD. | str | no |  |

#### Options for `redis.service`

|Option|Description|Type|Required|Default|
|---|---|---|---|---|
| `server` | Redis server service name. Defaults to redis-server on Linux and redis on FreeBSD. | str | no |  |
| `sentinel` | Redis Sentinel service name. Defaults to redis-sentinel on Linux and sentinel on FreeBSD. | str | no | redis-sentinel |

#### Options for `redis.replication`

|Option|Description|Type|Required|Default|
|---|---|---|---|---|
| `sentinel` | Whether to install and configure Redis Sentinel. | bool | no | False |

## Dependencies
None.

## Installation
Add this role to the requirements.yml of your playbook as follows:
```yaml
roles:
  - name: ansible-proserver-redis
    src: https://github.com/punktDe/ansible-proserver-redis
```

Afterwards, install the role by running `ansible-galaxy install -r requirements.yml`

## Example Playbook

```yaml
- hosts: all
  roles:
    - name: redis
```

<!-- END_ANSIBLE_DOCS -->
