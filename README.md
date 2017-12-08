# ansible-role-systemd

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-systemd.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-systemd)

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
    systemd_logind_hibernatekeyignoreinhibited: False
    systemd_logind_holdofftimeoutsec: 30s
    systemd_logind_idleaction: ignore
    systemd_logind_idleactionsec: 30min
    systemd_logind_inhibitdelaymaxsec: 5
    systemd_logind_inhibitorsmax: 8192
    systemd_logind_killexcludeusers: ''
    systemd_logind_killonlyusers: ''
    systemd_logind_killuserprocesses: False
    systemd_logind_lidswitchignoreinhibited: True
    systemd_logind_nautovts: 6
    systemd_logind_powerkeyignoreinhibited: False
    systemd_logind_removeipc: False
    systemd_logind_reservevt: 6
    systemd_logind_runtimedirectorysize: 10%
    systemd_logind_sessionsmax: 8192
    systemd_logind_suspendkeyignoreinhibited: False
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

GPLv3

## Author Information

This role was created by [Taylor Kimball](http://www.linuxhq.org).
