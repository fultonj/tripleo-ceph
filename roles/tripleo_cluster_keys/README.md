TripleO Cluster Keys
====================

Adds CephX keys to Ceph cluster


Role Variables
--------------

ceph_client: path to the ceph client command
ceph_cluster_name: the name of the ceph cluster
ceph_config_home: the path of the ceph configuration files (e.g. /etc/ceph)
keys: a list of hashes matching the format used by the ceph-ansible keys module


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - name: Add OpenStack key to the Ceph cluster
      include_role:
        name: tripleo_cluster_keys
        tasks_from: add
      vars:
        ceph_client: "{{ ceph_cli }}"
        ceph_cluster_name: ceph
        ceph_config_home: "/etc/ceph"
        keys:
          - name: "client.openstack"
            caps:
              mgr: "allow *"
              mon: "profile rbd"
              osd: "profile rbd pool=vms, profile rbd pool=volumes, profile rbd pool=images"

License
-------

BSD
