Identity Sources
================
``Administration > Tenants > (Selected Tenant) > Identity Sources``
``Administration > Users > Identity Sources``

Overview
--------

|morpheus| can integrate with many of the most common identity source technologies, such as Active Directory, Okta, and many others. These can be configured via the :guilabel:`Identity Sources` button on any Tenant detail page (Administration > Tenants > Selected Tenant) or on the Users list page (Administration > Users). These integrations map roles within these sign-on tools to equivalent roles in |morpheus| so at first log in users are assigned the appropriate role.

.. include:: /integration_guides/IdentityManagement/active_directory.rst
.. include:: /integration_guides/IdentityManagement/AzureAD.rst
.. include:: /integration_guides/IdentityManagement/okta.rst
.. include:: /integration_guides/IdentityManagement/onelogin.rst
.. include:: /integration_guides/IdentityManagement/saml.rst
