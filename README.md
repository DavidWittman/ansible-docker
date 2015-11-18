# Ansible Docker role for EL 6/7

This role installs the latest version of Docker from the official Docker repositories. All the other roles I've found seemed to be way more opinionated. This one just installs `docker-engine`, starts the service, then leaves you alone. Good day sir.

## Configurations

 * `docker_opts` - Arguments passed to the docker daemon at start time
