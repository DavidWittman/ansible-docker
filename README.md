# Ansible Docker role for EL 6/7

[![Ansible Galaxy](https://img.shields.io/badge/galaxy-DavidWittman.docker-blue.svg?style=flat)](https://galaxy.ansible.com/detail#/role/6099)

This role installs the latest version of Docker from the official Docker repositories. All the other roles I've found seemed to be way more opinionated. This one just installs `docker-ce`, starts the service, then leaves you alone. Good day sir.

## CentOS 6 Support

The `master` branch uses Docker CE and thus only supports CentOS 7. For CentOS 6 support, use the `centos6` branch. Updates will be made to this branch for maintenance only and support for CentOS 6 will be fully deprecated in the future.

## Role Variables

 * `docker_opts` - Arguments passed to the docker daemon at start time
 * `docker_env` - Dictionary of environment variables to set for the docker daemon
 * `docker_engine_cleanup` - Set this variable to `true` to clean up the old `docker-engine` repositories and packages.

## Common Settings

### Using an HTTP(S) proxy with Docker

Use the `docker_env` variable to set the `HTTP_PROXY` and/or `HTTPS_PROXY` environment variables:

``` yaml
- hosts: all
  roles:
    - role: DavidWittman.docker
      docker_env:
        HTTP_PROXY: "http://127.0.0.1:8080"
        HTTPS_PROXY: "https://127.0.0.1:8080"
```

## Testing

This role can be quickly deployed with [Vagrant](http://vagrantup.com) or with [Test Kitchen](http://kitchen.ci) to deploy and run a set of automated tests with [bats](https://github.com/sstephenson/bats).

### Vagrant

``` bash
$ vagrant up
```

### Test Kitchen

``` bash
# Install dependencies
$ bundle install
# Deploy, provision, and run tests
$ kitchen test
```
