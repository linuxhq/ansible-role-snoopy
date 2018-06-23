# ansible-role-snoopy

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-snoopy.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-snoopy)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-snoopy-blue.svg?style=flat)](https://galaxy.ansible.com/linuxhq/snoopy)
[![License](https://img.shields.io/badge/license-GPLv3-brightgreen.svg?style=flat)](COPYING)

RHEL/CentOS - Log every executed command to syslog

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    snoopy_error_logging: false
    snoopy_filter_chain: []
    snoopy_ld_preload: '/usr/$LIB/libsnoopy.so'
    snoopy_message_format:
      - uid:%{uid}
      - sid:%{sid}
      - tty:%{tty}
      - cwd:%{cwd}
      - filename:%{filename}
    snoopy_output: devlog
    snoopy_syslog_facility: LOG_AUTHPRIV
    snoopy_syslog_ident: snoopy
    snoopy_syslog_level: LOG_INFO

## Dependencies

 * https://galaxy.ansible.com/linuxhq/linuxhq

## Example Playbook

    - hosts: servers
      roles:
        - role: linuxhq.snoopy
          snoopy_message_format:
            - gecos:%{env:USER}
            - uid:%{uid}
            - tty:%{tty}
            - cwd:%{cwd}

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
