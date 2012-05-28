Key Manager
-----------

Required Knowledge
~~~~~~~~~~~~~~~~~~

#. MySQL Root Password
#. Java Home

Relevant files 
~~~~~~~~~~~~~~
kmInstaller.tar.gz, when extracted, will generate a km/ directory containing:

#. files
#. installDB.sh 
#. installKM.sh

Next, move the setup/ directory from the keygen directory, so that the contents of the km/ directory are, after this step:

#. files/
#. installDB.sh 
#. installKM.sh
#. setup/

Upon completion of this step, you will have installed the enStratus key management
software component and the credentials database.  The setup/install.credentials file will
be appended with the username and password used by the KM service to connect to its
database along with a list of the configuration files used to configure the KM service.

Key Manager Configuration Files
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none

  [ KM Configuration Files ]

  /services/km/tomcat/webapps/ROOT/META-INF/context.xml
  /services/km/tomcat/conf/server.xml
