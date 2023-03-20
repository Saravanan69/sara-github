---
- name: This sets up an httpd webserver
  hosts: Test
  become: yes
  tasks:
    - name: Install apache packages
      dnf:
        name: httpd
        state: latest

    - name: ensure httpd is running
      service:
        name:  httpd
        state: started
    - debub:
        msg : the service is running
