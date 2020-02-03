# Ansible Role: NodeSource

[![Build Status](https://travis-ci.com/transitiv/ansible-role-nodesource.svg?branch=master)](https://travis-ci.com/transitiv/ansible-role-nodesource)

This role installs Node.js from the [NodeSource package repositories](https://github.com/nodesource/distributions/blob/master/README.md) on systems running Debian/Ubuntu and RHEL/CentOS.

## Requirements

Root accesss is required for installing packages, so you must run it in a playbook with global root privileges or define `become: yes` when the role is included:

```yaml
- hosts: nodejs_servers
  roles:
    - role: transitiv.nodesource
      become: yes
```

## Dependencies

This role has no dependencies.

## Variables

```yaml
nodesource_version: 13
```

Defines the version of Node.js that will be installed. NodeSource currently provides versions 10, 12 and 13.

**Note** [Only Node.js 11.x is supported on CentOS / RHEL 6](https://github.com/nodesource/distributions/blob/master/README.md#rpm).

```yaml
nodesource_packages:
  - nodejs
```

Defines the package(s) installed by the role. This variable is "flattened" before it is used so it can contain nested lists if desired.

```yaml
nodesource_packages_state: present
```

Defines the state of the packages defined in `nodesource_packages`. See the `state` parameter in the apt and yum Ansible modules for valid values.

## License

This role is available under the terms of the MIT license.

## Author

This role was created by [Transitiv Technologes Ltd.](https://www.transitiv.co.uk).
