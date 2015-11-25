# Ansible Docker role for EL 6/7

[![Ansible Galaxy](https://img.shields.io/badge/galaxy-DavidWittman.docker-blue.svg?style=flat)](https://galaxy.ansible.com/detail#/role/6099)

This role installs the latest version of Docker from the official Docker repositories. All the other roles I've found seemed to be way more opinionated. This one just installs `docker-engine`, starts the service, then leaves you alone. Good day sir.

## Configurations

 * `docker_opts` - Arguments passed to the docker daemon at start time

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
