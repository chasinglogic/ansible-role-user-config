Ansible role for updates
==================================

Optionally run blanket package updates on your Linux systems

[![CircleCI](https://img.shields.io/circleci/build/github/chasinglogic/ansible-role-updates/master?style=flat-square)](https://circleci.com/gh/chasinglogic/ansible-role-updates)


Example Playbook
----------------

All that's required to enable this role is to add it to the role list
for your hosts. All is generally a good choice since it works on
(almost) all Linux distributions.

```yaml
- hosts: all
  roles:
    - role: updates
```

You can then disable updates for any `ansible-playbook` run by adding
the flag `--skip-tags updates`. All tasks in this role use this tag so
conversely, you can only run updates (i.e. no other tasks) but using
`--tags updates`. Without one of the aforementioned flags updates will
always run on your systems.

Development
-----------

Testing this role locally requires the Molecule.

After installing the CLI, invoke the following command to run the Molecule tests:

    $ make test

License
-------

[Apache License](LICENSE)
