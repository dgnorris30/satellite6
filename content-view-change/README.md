content-view-change
=========

This role is used to change the Satellite Content View for a host uses for yum content


Requirements
------------

sat-tower-variable-update to be run first to populate the survey with updated content view list


Role Variables
--------------

vars:
  base_Sat_URL: (FQDN of satellite)
  organization_id: (Satellite Organization ID#)
  content_view_name: (survey can be automatically populated by using sat-tower-variable-update)
  sat_username: (Satellite username)
  sat_password: (Satellite password)

Complimentary roles
------------

sat-analysis
sat-tower-variable-update
sat-patching



Example Playbook
----------------

---
- hosts: all
  vars:
    base_Sat_URL: satellite.example.com
    organization_id: 3
    content_view_name: oct2018
    sat_username: admin
    sat_password: password1
  roles:
  - content-view-change
