macos nestgroup
=========

[![Build Status](https://travis-ci.org/ANTS-Framework/macos_nestgroup.svg?branch=master)](https://travis-ci.org/ANTS-Framework/macos_nestgroup)

This role used the `dseditgroup` command to manage group nestings.

By default, this will add the `everyone` group to `lpadmin` allowing users
more flexibility in regard to printer control. But the role is generic enough
to be used for every kind of group nesting.

This role will not create non existend groups. It can only be used to 
nest existing groups or to remove existing group nestings.

Role Variables
--------------

```yml
macos_nestgroup__managed_group: lpadmin
macos_nestgroup__nested_group: everyone
```

Example Playbook
----------------

```yml
    # Used with no argument, the role
    # will add the everyone group to lpadmin
    - hosts: print
      roles:
         - macos_nestgroup

    # Remove the everyone group from lpadmin
    - hosts: noprint
      vars:
        - macos_nestgroup__present: false
      roles:
         - macos_nestgroup
```

License
-------

GPLv3

Author Information
------------------
Part of the [ANTS Framework](https://ants-framework.github.io/)
