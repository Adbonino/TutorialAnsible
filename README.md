# Ansible - Tutorial


## Ejecutando mi primer Playbook
ejemplo1:
https://github.com/Adbonino/TutorialAnsible.git

```
$ ansible-playbook -i inventories/local playbooks/hostname.yml
```

## Filtros

### Manejo de Variables

    Valores predeterminados:

        {{ antiguedad | default(0) }}

    Variables opcionales:+

        - name: touch files with an optional mode
          ansible.builtin.file:
            dest: "{{ item.path }}"
            statu: touch
            mode: "{{ item.mode | default(omit) }}"
          loop:
            - path: /tmp/foo
            - path: /tmp/bar
            - path: /tmp/baz
              mode: "0444"