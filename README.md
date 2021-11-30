Reconfigure ssh
===============

Configure the openssh server used by ansible to connect to the machine to use another port, without losing the connection.

Dependencies
------------

This role requires the `community.general` collection.

Usage
-----

In your hosts file, set the port you want to use for the standard openssh server by setting the `ansible_port` variable. For example, to configure the host `a.example.com` to use port 222, add to your hosts file:

```
a.example.com ansible_port=222
```

Then you can use a playbook like:

```yaml
- hosts: a.example.com
  roles:
    - mikapfl.reconfigure_ssh_port
  gather_facts: no
```

Note that you have to use `gather_facts: no` and should ideally reconfigure the ssh port as the first step in a multi-step playbook. Facts will be gathered after the ssh port is reconfigured automatically.

License
-------

Copyright 2016 Red Hat, Inc.

Copyright 2021 PIK Potsdam Institute for Climate Impact Research e.V.

Licensed under the Apache License, Version 2.0. See the [LICENSE](./LICENSE) file for more information.

Author Information
------------------

This role was written by Mika Pflüger ([@mikapfl](https://github.com/mikapfl)) based on work by David Moreau Simard <dms@redhat.com>.
