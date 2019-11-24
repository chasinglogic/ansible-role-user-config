Ansible role for user_config
==================================

Deploy user configuration files into their home directories

Example Playbook
----------------

Add this role to your role lists for the hosts 

```yaml
- hosts: all
  roles:
    - role: chasinglogic.user_config
```

This role is compatible, but does not depend on,
[singleplatform-eng.users](https://galaxy.ansible.com/singleplatform-eng/users). It
reads the same users variable and accepts the same structure as that
playbook. Documented here is the minimum required structure for this role to function:

```yaml
users:
    # Required: Must have a username defined
  - username: chasinglogic
    # Optional: Defaults to /home/{{ username }}
    home: /home/chasinglogic
```

Once the role is added and the users variable is configured this role
will look in the files directory for a directory that matches `{{
username }}/home`. For the above variable definition if we created at
the root of our playbook repository the directories:

```text
playbook.yml
files
└── chasinglogic
    └── home
        ├── .bash_profile
        ├── .bashrc
        ├── .ctags
        ├── .emacs.d
        │   └── init.el
        ├── .gitconfig
        ├── .gitignore
        ├── .mbsyncrc
        ├── .profile
        ├── .projector.yml
        ├── .project.yml
        ├── .tmux.conf
        └── .zshrc
```

Then all of the files, directories, and symlinks shown will be created
in the chasinglogic user's home directory. This is recursive and can
be nested as deep as your file system allows.

License
-------

[Apache License](LICENSE)
