# ansible-role-systemd

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-systemd.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-systemd)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-systemd-blue.svg?style=flat)](https://galaxy.ansible.com/linuxhq/systemd)
[![License](https://img.shields.io/badge/license-GPLv3-brightgreen.svg?style=flat)](COPYING)

RHEL/CentOS - Configure hostname, locale, and timezone via systemd

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    systemd_hostnamectl:
      chassis: ''
      deployment: ''
      hostname: localhost
      icon_name: ''
      location: ''
    systemd_logind_handlehibernatekey: hibernate
    systemd_logind_handlelidswitch: suspend
    systemd_logind_handlelidswitchdocked: ignore
    systemd_logind_handlepowerkey: poweroff
    systemd_logind_handlesuspendkey: suspend
    systemd_logind_hibernatekeyignoreinhibited: false
    systemd_logind_holdofftimeoutsec: 30s
    systemd_logind_idleaction: ignore
    systemd_logind_idleactionsec: 30min
    systemd_logind_inhibitdelaymaxsec: 5
    systemd_logind_inhibitorsmax: 8192
    systemd_logind_killexcludeusers: ''
    systemd_logind_killonlyusers: ''
    systemd_logind_killuserprocesses: false
    systemd_logind_lidswitchignoreinhibited: true
    systemd_logind_nautovts: 6
    systemd_logind_powerkeyignoreinhibited: false
    systemd_logind_removeipc: false
    systemd_logind_reservevt: 6
    systemd_logind_runtimedirectorysize: 10%
    systemd_logind_sessionsmax: 8192
    systemd_logind_suspendkeyignoreinhibited: false
    systemd_logind_usertasksmax: 33%
    systemd_localectl:
      locale: LANG=en_US.UTF-8
      keymap: us
      x11_keymap: us
    systemd_timedatectl:
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

Copyright (C) 2018 Taylor Kimball <tkimball@linuxhq.org>

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <http://www.gnu.org/licenses/>.
