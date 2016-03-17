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

barbican_galera_address
barbican_galera_password
barbican_rabbitmq_password
barbican_service_password
keystone_admin_user_name
keystone_auth_admin_password
keystone_admin_tenant_name

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
       keystone_admin_user_name: admin
       keystone_auth_admin_password: SuperSecretePassword4
       keystone_admin_tenant_name: admin
