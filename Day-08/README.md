- Hint: To ignore the gather facts tasks while running ansible-playbook commands
```
---
- hosts: all
  become: true
  gather_facts: false
```
- Hint: When running one comands
```
  tasks:
    - name: Make sure the packages openssh and openssl are up to date
      ansible.builtin.apt:
        name: openssh
        state: latest
```
- Hint: When running mutliple comands
```
  tasks:
    - name: Make sure the packages openssh and openssl are up to date
      ansible.builtin.apt:
        name: "{{item}}"
        state: latest
      loop:
        - openssh
        - openssl
```
