pass-change-passwd
==================

This role will generate a new user password on localhost, store it in pass and set it on a host.

Requirements
------------

You must have a working pass setup. You should be able to edit/insert new passwords and have any GPG sharing worked out.

Role Variables
--------------

The following variables are set in defaults. They are the most likely to be changed.
```
# The user whose password is to be changed:
pass_user: root 
# The password itself. A fallback value is provided in case pass doesn't override it properly, but it should fail before this is used.
password: Default123 
# The default length for generated passwords
password_length: 15
# The point within the pass tree that serves as a root for inventory passwords. By default all passwords will be in inventory/hosts/hostname.example.com/users/username
pass_inventory_root: inventory 
# Flags to give to pass. By defauly, we generate passwords without symbols.
pass_flags: -n
```

In addition to the above, the `inventory_hostname` variable is used to track the location of the password in the password store.

Dependencies
------------

There are no dependencies on other roles, but you must have a working pass installation on the host executing the role.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```
- hosts: test
  remote_user: root
  roles:
    - { pass-change-passwd, pass_user: root }
```

License
-------

MIT

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
