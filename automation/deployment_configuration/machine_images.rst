Machine Images/Templates
------------------------

.. note:: Creating "golden" or "master" images is common practice. Best practice is to
  utilize tools that are specially suited the task of configuration management. enStratus
  can leverage the power of both Chef and/or Puppet. enStratus also offers its own
  configuration management engine that is a good introduction to the concept.

A machine image is a template from which servers are started. This document assumes a high
degree of familiarity with the process of image creation and maintenance. Methods for
maintaining machines with respect to versioning will be addressed. In an automated
environment, the enStratus agent *must* be installed on a template prior to configuring a
deployment.

Versioning
~~~~~~~~~~

If you are operating in a deployment, enStratus can help you manage the version of machine
image you are using in your launch configurations. This concept is addressed as part of
the auto-rollout feature of enStratus.

In short, you should patch servers running in your deployment as you see fit, and ensure
you maintain an equally patched version of the AMI defined in your launch configuration so
that when/if a scale or recovery event occurs, you utilize the correct machine image
version for the newly created servers.

Dependencies
~~~~~~~~~~~~

enStratus has very few true dependencies. It depends on Java, so ensure you have the
latest JDK installed to support the Agent. Additionally, when you are operating in an
automated deployment environment, we recommend installing the following software:

.. tabularcolumns:: |l|l|l|

+-------------------+----------------------------------+--------------+
| Package           | Purpose                          | Note         |
+===================+==================================+==============+
| zip               | Backups                          | Recommended  |
+-------------------+----------------------------------+--------------+
| openssl           | Adding Users                     | **Required** |
+-------------------+----------------------------------+--------------+
| unzip             | Service install, backups         | Recommended  |
+-------------------+----------------------------------+--------------+
| build-essential   | OSSEC installation and more      | Optional     |
+-------------------+----------------------------------+--------------+
| xfsprogs          | XFS filesystem functionality     | Optional     |
+-------------------+----------------------------------+--------------+
| libapache2-mod-jk | mod_jk load balancing            | Optional     |
+-------------------+----------------------------------+--------------+
| postfix           | Sending mail notifications       | Optional     |
+-------------------+----------------------------------+--------------+
| cryptsetup        | Encryption (LUKS)                | Recommended  |
+-------------------+----------------------------------+--------------+
| haproxy           | Load Balancing                   | Optional     |
+-------------------+----------------------------------+--------------+
| cronolog          | Logging                          | Optional     |
+-------------------+----------------------------------+--------------+
| sysstat           | OS metrics                       | **Required** |
+-------------------+----------------------------------+--------------+
| secure-delete     | Securely delete files            | Recommended  |
+-------------------+----------------------------------+--------------+
| mysql-server      | Running MySQL Databases          | Optional     |
+-------------------+----------------------------------+--------------+
