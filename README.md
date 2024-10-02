# role-aap-object-credential
Ansible role to build AAP workflow objects

# Ref
https://console.redhat.com/ansible/automation-hub/repo/published/ansible/controller/content/module/schedule/

# How to use

Step 1: Install the role in your environment.
   - You could have roles/requirements.yml if running on AAP.
   - Or simple install on your environment.

Step 2: Define your variables in the structure below

- build: true/false # Bool value to switch role on off.
- project
- description
- organization
- scm_type
- scm_url
- scm_branch
- scm_credential
- scm_update_cache_timeout

Step 3: Call the role from your playbook.

# Example

## playbook
example-playbook.yml