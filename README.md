project
=======

[Ansible](http://ansible.com) role which setup simple project.

* Create simple catalogs structure:

```shell
example
├── .editorconfig
├── example.sublime-project
├── src
├── .teamocil.yml
└── tmp
```

* Setup [Sublime Text] project.
* Setup and enable [Teamocil] layout.

#### Requirements & Dependencies

- [Teamocil]
- [Sublime Text]

#### Variables

The role variables and default values.

```yaml
project_enabled: true                                     # enable the role

project_root_dir: '~/work'                                # root path for all projects

project_dir: '{{ project_root_dir }}/{{ project_name }}'
project_src_dir: '{{ project_dir }}/src'                  # catalog for source code of project
project_tmp_dir: '{{ project_dir }}/tmp'                  # catalog with project temp data

teamocil_dir: '~/.teamocil'                               # root path for all Teamocil layouts
teamocil_layout_name: '{{ project_name }}'

venv_root_dir: '{{ project_root_dir }}/.venv'             # root path for all venvs
venv_name: '{{ project_name }}'
venv_dir: '{{ venv_root_dir }}/{{ venv_name }}'
```

#### Usage

* Clone dependencies.
* Add `project` to your roles and change variables in your playbook file.

Example:

```yaml
- hosts: localhost
  roles:
    - project
  vars:
    project_dir: false
  vars_prompt:
    project_name: 'What is project name?'
    project_path: 'What is project path?'
```

#### License

Licensed under the MIT License. See the LICENSE file for details.

[Teamocil]: https://github.com/remiprev/teamocil
[Sublime Text]: http://www.sublimetext.com
