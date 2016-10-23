opendronemap |Travis|
=====================

.. |Travis| image:: https://travis-ci.org/qedsoftware/ansible-opendronemap.svg?branch=master
  :target: https://travis-ci.org/qedsoftware/ansible-opendronemap/builds

Ansible version of `OpenDroneMap build script`_.

.. _OpenDroneMap build script: https://github.com/qedsoftware/OpenDroneMap/blob/master/configure.sh

Role Variables
--------------

===================== ===================== ============================================= =====================================
Name                  Description           Example                                       Default
===================== ===================== ============================================= =====================================
opendronemap_work_dir Directory for sources "{{ ansible_env.HOME }}/ansible/OpenDroneMap" "{{ ansible_env.HOME }}/OpenDroneMap"
===================== ===================== ============================================= =====================================

Example Playbook
----------------

.. code-block:: yaml

  ---
  - hosts: opendronemap
    roles:
      - opendronemap
    vars:
      opendronemap_work_dir: "{{ ansible_env.HOME }}/OpenDroneMap"

Local installation
==================

Install Ansible by ``pip``:

.. code-block:: shell

  > sudo apt-get install python-pip python-dev
  > sudo pip install ansible
  > ansible --version
  ansible 2.1.1.0

Clone to directory ``opendronemap``
(name of the directory is important - it's a name of the role):

.. code-block:: shell

  > git clone https://github.com/qedsoftware/ansible-opendronemap opendronemap
  > cd opendronemap
  [opendronemap>

Run playbook with local inventory. Note that since script must install some
packages as ``root`` we should provide a password:

.. code-block:: shell

  [opendronemap]> ansible-playbook --inventory-file local local.yml --ask-become-pass --connection=local

License
-------

BSD

Author Information
------------------

Ruslan Baratov <ruslan@qed.ai>
