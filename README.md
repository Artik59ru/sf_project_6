Проектная работа 6
==================
- name: Add data_directory configuration to "postgresql.conf"
      lineinfile:
       dest: /etc/postgresql/{{ pg_version }}/main/postgresql.conf
       regexp: '^data_directory\s*='
       line: "data_directory = '{{ pg_data }}'"
       state: present
      notify: Restart Postgresql
