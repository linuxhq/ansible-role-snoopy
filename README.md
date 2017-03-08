# ansible-role-snoopy

[![Build Status](https://travis-ci.org/linuxhq/ansible-role-snoopy.svg?branch=master)](https://travis-ci.org/linuxhq/ansible-role-snoopy)

RHEL/CentOS - Log every executed command to syslog

## Requirements

None

## Role Variables

Available variables are listed below, along with default values:

    snoopy_error_logging: False
    snoopy_filter_chain: ''
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

## Partners

[![packagecloud](http://dka575ofm4ao0.cloudfront.net/pages-transactional_logos/retina/10543/gKme3F4XRaC5EyKJzKsA)](https://packagecloud.io)

Do you need trustworthy hosted package repositories?  Then packagecloud is for you.

A big thank you to packagecloud for supporting the open source community!

## License

BSD

## Author Information

This role was created by [Taylor Kimball](http://www.linuxhq.org).
