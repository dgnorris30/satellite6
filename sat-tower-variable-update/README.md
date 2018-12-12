sat-tower-variable-update
=========

This role is used in Ansible Tower to automatically create an updated survey with the latest Content Views from satellite for the change-content-view role

Requirements
------------

- Ansible Tower
- change-content-view template  
- the template_id for change-content-view template. This ID can be found via Ansible Tower Web Interface. Log in > Templates > change-content-view (or whatever you named this template) and looking at the url for the template ID #
(Example https://tower.example.com/#/templates/jop_template/25  > template_id: 25)

Role Variables
--------------

base_Sat_URL: (FQDN satellite server)
sat_username: (satellite username)
sat_password: (satellite password)
base_Tower_URL: (FQDN Ansible Tower server)
tower_username: (Ansible Tower username)
tower_password: (Ansible Tower password)
organization_id: (Satellite Organization ID #)
template_id: (This ID can be found via Ansible Tower Web Interface)
Log into Tower > Templates > change-content-view (or whatever you named this template) and looking at the url for the template ID #
(Example https://tower.example.com/#/templates/jop_template/25  => template_id: 25)


Dependencies / Complimentary roles
------------

content-view-change
sat-analysis
sat-patching

Example Playbook
----------------

---
- hosts: localhost
  connection: local
  vars:
    base_Sat_URL: satellite.example.com
    sat_username: admin
    sat_password: password1
    base_Tower_URL: tower.example.com
    tower_username: admin
    tower_password: password1
    organization_id: 3
    template_id: 25
  roles:
  - sat-tower-variable-update
