Ambari Server and HDP Installation
==================================

TODOS:

* find a neat way to configure ambari-server .... (maybe deploy config file)
* install hdp using blueprints


Requirements
------------

Role Variables
--------------


Dependencies
------------

* hdp-ambari-agents
* hdp-mysql-server

Example Playbook
----------------

- name: install ambari agents
  hosts: hdp
  gather_facts: yes
  become: yes
  vars_files:
    - ./vars/main.yml
  roles:
    - hdp-ambari-agents

- name: install ambari server
  hosts: utility
  gather_facts: yes
  become: yes
  vars_files:
    - ./vars/main.yml
  roles:
    - hdp-mysql-server
    - hdp-ambari-server

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
