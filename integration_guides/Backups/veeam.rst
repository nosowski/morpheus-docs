Veeam
-----

Adding Veeam Integration
^^^^^^^^^^^^^^^^^^^^^^^^

#. Navigate to `Backups -> Services`
#. Select :guilabel:`+ ADD`
#. Select Veeam
#. Fill in the following:

   Name
      Name of the Integration in |morpheus|
   Enabled
      Enable the Veeam integration
   Host
      IP or Hostname of the Veeam server, must be HTTPS for VEEAM 10
   Port
      Port number configured to access the Veeam server, must be 9398 for VEEAM 10
   Username
      Admin Username for Veeam
   Password
      Password for Username provided (encrypted in |morpheus|).
   Visibility
      Sets Multi-Tenant Visibility
        Private
          Only Available to the Tenant the Integration is added by
        Public
          Available to Sub-Tenants (master tenant option only)

#. Click :guilabel:`SAVE`

.. NOTE:: Veeam Backup Enterprise Manager must be installed in order to successfully integrate |morpheus| with Veeam.

.. IMPORTANT:: Once Veeam service has been integrated with |morpheus|, Veeam server(s) will be available to select as the backup provider for VMware, Hyper-V, and vCloud Director cloud integrations (Infrastructure > Clouds > Edit a compatible Cloud). To enable Veeam backups, select the appropriate Veeam server as the "backup provider" for your cloud integrations as needed. Failure to do so will result in blank ``Backup Repositories`` and ``Backup Job Templates`` options when configuring Veeam Backups during provisioning.
