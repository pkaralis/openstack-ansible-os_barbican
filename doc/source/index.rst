===================================
Barbican role for OpenStack-Ansible
===================================

This Ansible role installs and configures OpenStack barbican.

Default variables
~~~~~~~~~~~~~~~~~

.. literalinclude:: ../../defaults/main.yml
   :language: yaml
   :start-after: under the License.

Required variables
~~~~~~~~~~~~~~~~~~

.. code-block:: yaml

    barbican_galera_address
    barbican_galera_password
    barbican_rabbitmq_password
    barbican_service_password
    keystone_admin_user_name
    keystone_auth_admin_password
    keystone_admin_tenant_name

Example playbook
~~~~~~~~~~~~~~~~

.. literalinclude:: ../../examples/playbook.yml
   :language: yaml

Tags
~~~~

This role supports two tags: ``barbican-install`` and ``barbican-config``. The
``barbican-install`` tag can be used to install and upgrade. The ``barbican-
config`` tag can be used to maintain configuration of the service.
