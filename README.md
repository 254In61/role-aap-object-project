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

---
- name: Playbook to configure AAP
  hosts: localhost
  gather_facts: false
 
  pre_tasks:
    - name: Include specific project variables
      ansible.builtin.include_vars:
        dir: group_vars

  tasks:
    !
    !
    - name: Import role-aap-object-project
      ansible.builtin.import_role:
        name: role-aap-object-project
      vars:
        build: true
        project: "{{ project_name }}"
        description: "{{ common_description }}"
        organization: "{{ organization_name }}"
        scm_type: git
        scm_url: "{{ project_git_repo }}"
        scm_branch: "{{ project_git_branch }}"
        scm_credential: "{{ git_credential_name }}"
        scm_update_cache_timeout: 60
    !
    !
# Author
Name: Allan Maseghe

Email: amaseghe@redhat.com