Role Name
=========

Ansible playbook to deploy role_deploy_minishift using the KVM virtualization driver. Written on Fedora 29

Requirements
------------

May need to create a volume for /var/lib/libvirt (recommended) depending on usage and size of /var

Role Variables
--------------

Prompt variables: the user needed to add to the libvirt group and domain name you'd like to use with libvirt.

Dependencies
------------

Check the [minishift](https://github.com/minishift/minishift/releases) and [KVM_driver](https://github.com/dhiltgen/docker-machine-kvm/releases) projects for the latest version and checksum.

Example Playbook
----------------

Example run:

```
ansible-playbook -v pb_deploy_minishift.yaml
```

        ---
        # Ansible playbook to deploy role_deploy_minishift
        #
        - hosts: 127.0.0.1
          gather_facts: no
          connection: local
          vars_prompt:
            - name: domain
              prompt: "Enter the domain you'd like to use"
              private: no

            - name: user
              prompt: "Enter user to add to libvirtd group"
              private: no

          roles:
          - { role: role_deploy_minishift }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
