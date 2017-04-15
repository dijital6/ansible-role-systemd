# ansible-role-systemd

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-systemd.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-systemd)

RHEL/CentOS - Configure hostname, locale, and timezone via systemd

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    systemd_hostnamectl:
      path: /usr/bin/hostnamectl
      chassis: ''
      deployment: ''
      hostname: localhost
      icon_name: ''
      location: ''
    systemd_localectl:
      path: /usr/bin/localectl
      locale: LANG=en_US.UTF-8
      keymap: us
      x11_keymap: us
    systemd_timedatectl:
      path: /usr/bin/timedatectl
      local_rtc: no
      ntp: no
      timezone: UTC

## Dependencies

None

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.systemd
          systemd_hostnamectl:
            hostname: "{{ inventory_hostname }}"
            location: "{{ inventory_hostname.split('.')[0] }}"
          systemd_timedatectl:
            timezone: 'America/Los_Angeles'

## License

BSD

## Author Information

This role was created by [Taylor Kimball](http://www.linuxhq.org).
