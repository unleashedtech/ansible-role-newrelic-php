# New Relic PHP Agent - Ansible Role

[![Ansible Role](https://img.shields.io/ansible/role/20311.svg)](https://galaxy.ansible.com/TypistTech/trellis-newrelic-php/)
[![Build Status](https://travis-ci.org/unleashedtech/ansible-role-newrelic-php.svg?branch=master)](https://travis-ci.org/unleashedtech/ansible-role-newrelic-php)
[![GitHub tag](https://img.shields.io/github/tag/unleashedtech/ansible-role-newrelic-php.svg)](https://github.com/unleashedtech/ansible-role-newrelic-php/tags)
[![license](https://img.shields.io/github/license/unleashedtech/ansible-role-newrelic-php.svg)](https://github.com/unleashedtech/ansible-role-newrelic-php/blob/master/LICENSE)

Installs [New Relic PHP agent](https://docs.newrelic.com/docs/agents/php-agent) on Debian-based servers. Fully compatible with the `geerlingguy.php` role.

## Requirements

* [Ansible](http://docs.ansible.com/ansible/latest/intro_installation.html) 2.3 or later
* [New Relic](https://newrelic.com/) account
* Debian or Ubuntu (modern versions)

## Installation

Add this role to `requirements.yml`:

```yaml
- src: unleashedtech.newrelic_php
  version: 0.1.0 # Check for latest version!
```

Run `$ ansible-galaxy install -r requirements.yml` to install this new role.

## Role Variables

```yaml
# New Relic License Key
## You should store this in an encrypted vault file!
## See: https://docs.newrelic.com/docs/accounts-partnerships/accounts/account-setup/license-key
newrelic_php_license_key: xxxxxxxxxxx

# Indicates the desired package state.
# `latest` ensures that the latest version is installed.
# `present` does not update if already installed.
# Choices: present|latest
# Default: latest
newrelic_php_package_state: present

# See https://docs.newrelic.com/docs/agents/php-agent/configuration/php-agent-configuration
newrelic_php_config:
  appname: "My Awesome App {{ env }}"
  transaction_tracer.detail: 1
  datastore_tracer.database_name_reporting.enabled: true
```

## Limitations

* Only one New Relic APM application per server

Pull requests are welcomed.

## See Also

* [New Relic PHP agent docs](https://docs.newrelic.com/docs/agents/php-agent)

## License

[New Relic PHP Agent](https://github.com/unleashedtech/ansible-role-newrelic-php) is released under the [MIT License](https://opensource.org/licenses/MIT).
