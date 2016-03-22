OpenStack-Ansible Barbican
##########################
:tags: openstack, barbican, cloud, ansible
:category: \*nix

This Ansible role installs and configures OpenStack Barbican.

Default Variables
=================

.. literalinclude:: ../../defaults/main.yml
   :language: yaml
   :start-after: under the License.

Required Variables
==================

barbican_service_password
barbican_galera_password
barbican_rabbitmq_password

Example Playbook
================

.. code-block:: yaml

   - name: Install barbican server
     hosts: barbican_all
     user: root
     roles:
       - role: "os_barbican"
     vars:
       external_lb_vip_address: 172.16.24.1
       internal_lb_vip_address: 192.168.0.1
       barbican_galera_address: "{{ internal_lb_vip_address }}"
       barbican_service_password: SuperSecretePassword1
       barbican_galera_password: SuperSecretePassword2
       barbican_rabbitmq_password: SuperSecretePassword3
