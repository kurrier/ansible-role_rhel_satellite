Ansible Role: satellite [![CircleCI](https://circleci.com/gh/kurrier/ansible-role_rhel_satellite.svg?style=svg)](https://circleci.com/gh/kurrier/ansible-role_rhel_satellite)
=========

RHEL Satellite Management

Requirements
------------

N/A

Role Variables
--------------
* satellite_url: satellite server URL
* sat_env: lifecycle environment of client server
* sat_org: satellite orginization
* satellite_auth_username: api username
* satellite_auth_password: api password
* satellite_cv_name: CV Name

## Run ##
* sat_register: [true/false] - register host to satellite
* sat_tools: [true/false] - install satellite tools
* sat_tracer [true/false] - install satellite tracer
* sat_publish: [true/false] - publish new CV version
* sat_promote: [true/false] - promote CV version to lifecycle environment
* sat_repos: [true/false] - get repo information

## Misc Settings ##

* satellite_function_encrypt: [true/false] - satellite_auth_api is stored in encrypted file

Dependecies
-----------

None

Example Playbook
----------------
        - hosts: localhost
          become: true
          gather_facts: false
          vars:
            satellite_url: https://my.satelllite.io
            sat_promote: true
            satellite_auth_api: "123API"
            satellite_cv_name: "My APP"
            satellite_env: "QA"
        - role: kurrier.satellite

This will promote the CV to the QA environment

Test
----------------

ansible-playbook tests/test.yml -i tests/inventory

License
-------

Licensed under GPLv3 License. See LICENSE for details.

Author Information
------------------

Nick Lalumiere
