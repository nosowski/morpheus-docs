.. _compatibility:

*******************************************
|morphver| Compatibility & Breaking Changes
*******************************************

When installing and upgrading to |morpheus| |morphver|, refer to the following to ensure compatibility.

Breaking Changes
================

- 4.2.1+: Appliance: OS: Ubuntu 14.04 has reached its end of life (EOL) and is no longer supported as a Morpheus Appliance Host Operating System. Any |morpheus| Appliance running on 14.04 must be upgraded to 16.04, 18.04 or 20.04 BEFORE upgrading to 4.2.1+. Upgrades on 14.04 will not succeed
- 4.2.1+: Clouds: VirtualBox, VirtuSteam, and MetaCloud Cloud Types are no longer supported or available
- 4.2.1+: Puppet: |morpheus| integration now supports version 6+. Puppet versions prior to 6 are no longer supported
- 4.2.1+: Tasks: Python: Virtual environment are now used for Python Tasks. **Note:** ``virtualenv`` is required on all Appliance App nodes: ``pip install virtualenv``
- 4.2.4: For appliances with externalized MySQL databases, due to MySQL deprecation of the "EDT" timezone you may need to update your database timezone to UTC or another compatible value. If this is not done, you will receive errors referencing timezone and |morpheus| will not start. |morpheus| should handle this change automatically for all-in-one appliances.
- 5.0.0+: When upgrading to 5.0.0+ from 4.x.x, any bearer tokens that have been generated are deleted which requires users to request new bearer tokens

|morpheus| Application OS
=========================

|morpheus| can be installed on the following platforms. Please note the table below is for |morpheus| Application OS support, not |morpheus| Agent OS Support.

.. important:: Existing |morpheus| Appliances on 14.04 must upgrade to 16.04, 18.04 or 20.04 PRIOR to upgrading to v4.2+.

.. note:: CentOS v8.3 repo name changes will cause reconfigure failure. ``guacd['yum-power-tools-repo-baseurl'] = 'http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=powertools&infra=$infra'`` can be aded to ``/etc/morpheus/morpheus.rb`` as a workaround until native support is added.

.. list-table:: **Supported Appliance Operating Systems**
   :widths: auto
   :header-rows: 1

   * - OS
     - Version(s)
     - Notes
   * - Amazon Linux
     - 2
     -
   * - CentOS
     - 7.x, 8.0, 8.1, 8.2
     - CentOS v8.3 repo name changes will cause reconfigure failure. ``guacd['yum-power-tools-repo-baseurl'] = 'http://mirrorlist.centos.org/?release=$releasever&arch=$basearch&repo=powertools&infra=$infra'`` can be aded to ``/etc/morpheus/morpheus.rb`` as a workaround until native support is added.
   * - Debian
     - 9, 10
     - FreeRDP 2.0 is not compatible with Debian 9. Guacd will remain at 1.0.0 for Appliances running on Debian 9.
   * - RHEL
     - 7.x, 8.x
     -
   * - SUSE Linux Enterprise Server (SLES)
     - 12, 15
     -
   * - Ubuntu
     - 16.04, 18.04, 20.04
     - 14.04 is no longer supported for Appliance OS. Existing Appliances on 14.04 must upgrade to 16.04, 18.04 or 20.04 PRIOR to upgrading to v4.2.1+. Note: 14.04 is still supported by the |morpheus| Agent.

Services
========

|morphver| Service Version Changes
----------------------------------

No Service Version changes from |previousMorphVer|

|morphver| Service Version Compatibility
----------------------------------------

When externalizing MySQL, Elasticsearch and/or RabbitMQ services, the following versions are compatible with version |morpheus| |morphver|

+---------------------------------------+-----------------------+-------------------------------------+
| **Service**                           | **Compatible Branch** | **Morpheus Installer Version**      |
+---------------------------------------+-----------------------+-------------------------------------+
| MySQL                                 | |mysqlbranch|         | |mysqlver|                          |
+---------------------------------------+-----------------------+-------------------------------------+
| MySQL (FIPS)                          | |mysqlbranch|         | |mysqlverfips|                      |
+---------------------------------------+-----------------------+-------------------------------------+
| Percona                               | 5.7, WSREP 31         | n/a                                 |
+---------------------------------------+-----------------------+-------------------------------------+
| Elasticsearch                         | |esbranch|            | |esver|                             |
+---------------------------------------+-----------------------+-------------------------------------+
| RabbitMQ                              | |rmqbranch|           | |rmqver|                            |
+---------------------------------------+-----------------------+-------------------------------------+
| Tomcat                                |                       | |tcver|                             |
+---------------------------------------+-----------------------+-------------------------------------+
| Nginx                                 |                       | |nginxver|                          |
+---------------------------------------+-----------------------+-------------------------------------+

.. important:: Elasticsearch 7.x is required for |morphver|. Refer to :ref:`upgrading` section for more information.

Integrations
============

.. note:: Current iterations of Amazon AWS, Microsoft Azure, Google Cloud Platform, Digital Ocean, HPE OneView, OpenTelekom Cloud, IBM Bluemix, Softlayer and UpCloud are all supported.

.. include:: compatibility_table.rst
