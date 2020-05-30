ceph_client
===========

Mirror a list of files from a path on first mon server to all other
servers in inventory in same path.

Role Variables
--------------

path: source and destination of files to mirror
files: list of files to mirror, e.g. [ceph.conf, ceph.client.opentsack.keyring]

Example Playbook
----------------

    - name: rsync ceph configuration and openstack key to all nodes
      include_role:
        name: ceph_client
        tasks_from: sync
      vars:
        path: "/etc/ceph"
        files:
          - ceph.conf
          - ceph.client.opentsack.keyring

License
-------

BSD
