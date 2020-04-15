# Ansible Role: New Relic

[![Build Status](https://travis-ci.org/Aplyca/ansible-role-newrelic.svg?branch=master)](https://travis-ci.org/Aplyca/ansible-role-newrelic)
[![Circle CI](https://circleci.com/gh/Aplyca/ansible-role-newrelic.png?style=badge)](https://circleci.com/gh/Aplyca/ansible-role-newrelic)

Ansible Role that installs and configure New Relic on Debian/Ubuntu.

## Requirements

Use hash behavior for variables in ansible.cfg
See example: https://github.com/Aplyca/ansible-role-newrelic/blob/master/tests/ansible.cfg
See official docs: http://docs.ansible.com/intro_configuration.html#hash-behaviour

## Installation

Using ansible galaxy:
```bash
ansible-galaxy install Aplyca.NewRelic
```
You can add this role as a dependency for other roles, add the role to the meta/main.yml file of your own role:
```yaml
dependencies:
  - { role: Aplyca.NewRelic }
```



## Dependencies

None.

## Testing

Use Vagrant to test the role:

```bash
cd tests;
vagrant box add ubuntu/trusty64;
vagrant up;
```

## License

MIT / BSD

## Author Information

Mauricio Sánchez from Aplyca SAS (http://www.aplyca.com)
