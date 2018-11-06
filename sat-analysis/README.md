sat-analysis
=========

Pre-Patching Analysis


Requirements
------------

root/sudo permission for yum command


Role Variables
--------------

email_list: "true" or "false"
   email a a file attachment containing requested patching information
email_username: example@redhat.com
email_pass: password
email_addr: recipient_email@email.com
   * required if email_list: "true"

list_type:
  - none
  - security
  - overview
  - kernel
  - package
  - errata
preferably entered via ansible tower survey, multiple choice (select multiple)


Complimentary roles
------------

content-view-change
sat-patching



Example Playbook
----------------

    - hosts: servers
      vars:
        base_Sat_URL: satellite.example.com
        sat_username: admin
        sat_password: example
        organization_id: 3
        content_view_name: default
        list_type:
          - overview
          - Kernel
        email_list: true
        email_sender: example@email.com
        email_pass: password
        email_addr: recipient_email@email.com
      roles:
         - content-view-change
         - sat-analysis
