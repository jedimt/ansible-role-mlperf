Ansible Role: MLPerf
=========

Install and configure the MLPerf storage I/O benchmark.

Requirements
------------

Ubuntu 22.04 and Python 3.10

Role Variables
--------------

    # mlperf.yml variables

      # Folder for model data
      mlperf_data_folder: '/data'

      # Path to receive the cloned mlperf storage repo
      mlperf_repo_dest_folder: '{{ ansible_env.HOME }}/github/storage'

      # Python version for venv used for mlperf packages and modules
      venv_python_version: '3.10'

      # MLPerf github
      mlperf_repo_url: 'https://github.com/mlcommons/storage.git'

      # MLPeft version to download
      mlperf_repo_version: 'v0.5'

    # precheck.yml variables
      # Minimum tested version of python
      precheck_python_min_version: '3.10'

      # Minimum tested version of Ansible (7.x)
      precheck_ansible_min_version: '2.14.1'

      # Minimum Ubuntu version
      precheck_ubuntu_min_version: '22.04'

Example Playbook

    # ===========================================================================
    # MLPerf Storage Benchmark Installation and configuration
    # ===========================================================================
    - name: Install and configure MLPerf Storage Benchmark
      hosts: servers
      tags: play_mlperf_install
      # become: true
      gather_facts: true

      vars_files:
        # Ansible vault with all required passwords
        - "../../credentials.yml"

      roles:
        - { role: jedimt.mlperf,
            skip_validation: true
        }

License
-------

MIT

Author Information
------------------

Aaron Patten
aaronpatten@gmail.com
