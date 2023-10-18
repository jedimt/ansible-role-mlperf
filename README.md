Ansible Role: MLPerf
=========

Install and configure the MLPerf storage I/O benchmark.

Requirements
------------

<wip>

Role Variables
--------------

    # some variable
    some_variable: true


Dependencies
------------

<wip>

Example Playbook [needs update]
----------------

    # ===========================================================================
    # Install MLPerf
    # ===========================================================================

    - name: Install and configure MLPerf
      hosts: servers
      tags: play_mlperf_install
      gather_facts: true

      vars_files:
        # Ansible vault with all required passwords
        - "../../credentials.yml"
        # Ansible vault with server and SPU serials
        - "../../serials.yml"

      roles:
        - { role: jedimt.mlperf }

License
-------

MIT

Author Information
------------------

Aaron Patten
aaronpatten@gmail.com
