TripleO Cluster Pools
=========

Creates Ceph pools

Role Variables
--------------

- ceph_client: the client command to run
- pools: a list of hashes describing the pools


Example Playbook
----------------

    - name: Add OpenStack pools to the Ceph cluster
      include_role:
        name: tripleo_cluster_pools
        tasks_from: add
      vars:
        ceph_client: "{{ ceph_cli }}"
        pools:
          - {"name": rbd, "pg_num": 32, "pgp_num": 32, "application": rbd}
          - {"name": volumes, "pg_num": 32, "pgp_num": 32, "application": rbd}
          - {"name": vms, "pg_num": 32, "pgp_num": 32, "application": rbd}
          - {"name": images, "pg_num": 32, "pgp_num": 32, "application": rbd}

License
-------

BSD
