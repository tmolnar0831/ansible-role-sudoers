# Ansible role that Ansible role that manages sudo and the sudoers file

[![build status](https://gitlab.com/stiron/ansible-sudoers/badges/master/build.svg)](https://gitlab.com/stiron/ansible-sudoers/commits/master)

## Requirements

This module requires Ansible 2.x version.

## Role variables

```
sudoers_envkeeps:
  - "COLORS DISPLAY HOSTNAME HISTSIZE KDEDIR LS_COLORS"
  - "MAIL PS1 PS2 QTDIR USERNAME LANG LC_ADDRESS LC_CTYPE"
  - "LC_COLLATE LC_IDENTIFICATION LC_MEASUREMENT LC_MESSAGES"
  - "LC_MONETARY LC_NAME LC_NUMERIC LC_PAPER LC_TELEPHONE"
  - "LC_TIME LC_ALL LANGUAGE LINGUAS _XKB_CHARSET XAUTHORITY"

sudoers_securepaths:
  - /sbin
  - /bin
  - /usr/sbin
  - /usr/bin

sudoers_rules:
  - 'root ALL=(ALL) ALL'
  - '%wheel ALL=(ALL) ALL'
  - '%super ALL=(ALL) NOPASSWD:ALL'

sudoers_hostaliases:
  SERVERS:
    - 192.168.0.202
    - 192.168.0.203
  NETWORK:
    - 192.168.0.0/255.255.255.0

sudoers_commandaliases:
  SHUTDOWN_CMDS:
    - /sbin/poweroff
    - /sbin/reboot
    - /sbin/halt

sudoers_mailto: xy@yz.com
```

## Examples

```
- hosts: all 
  roles:
    - sudoers
```

## Dependencies

None

## License

MIT

## Author

Tamas Molnar - <tmolnar0831@gmail.com>
