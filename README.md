# Ansible Role Squash TM

This Ansible role installs and configures Squash TM (Official website: https://www.squashtest.org/).

## Prerequisites

* Java 8 (it is IMPERATIVE to use Java 8, Java 7 is not supported anymore)
* Database: none or MySQL 5.0 + (but not MySQL 5.6), PostGres 9.1+.

## Usage

    http://<host>:<port>/<context>
    http://localhost:8080/squash

Initial credentials are admin / admin . Do not forget to change it!

## Example Playbook

    - hosts: servers
      roles:
      - role: ansible-role-squash-tm
        squash_db_password: 'oloc4ever'

## Main Variables

The default database is h2.

    squash_db_url: "jdbc:h2:///var/lib/squash-tm/data/squash-tm"
    squash_db_type: "h2"
    squash_db_username: "sa"
    squash_db_password: "sa"

### Mysql

    squash_db_url: "jdbc:mysql://localhost:3306/squashtm"
    squash_db_type: "mysql"
    squash_db_username: "squash-tm"
    squash_db_password: "initial_pw"

### Postgresql

    squash_db_url: "jdbc:postgresql://localhost:5432/squashtm"
    squash_db_type: "postgresql"
    squash_db_username: "squash-tm"
    squash_db_password: "initial_pw"
    squash_db_host: "localhost"

## Advanced Options

### Java Args

    squash_xms: '128m'
    squash_xmx: '512m'
    squash_maxpermsize: '128m'
    squash_extra_java_args: '-javaagent:path/to/glowroot.jar'

### Others

    squash_http_port: '8080'

## License

MIT

##  Author Information

This role was created in 2018 by Olivier Locard on the behalf of Deveryware.
