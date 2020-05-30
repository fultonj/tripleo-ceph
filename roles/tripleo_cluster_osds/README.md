TripleO Cluster OSDs
====================

Example Playbook
----------------

Including an example of how to use your role (for instance, with
variables passed in as parameters) is always nice for users too:

    - name: Add OSDs to the Ceph cluster via orchestrator
      include_role:
        name: tripleo_cluster_osds
        tasks_from: add
      vars:
        ceph_client: "{{ ceph_cli }}"
        all_available: false
        devices: []

License
-------

BSD

