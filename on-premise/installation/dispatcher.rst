Dispatcher
----------

Required Knowledge
~~~~~~~~~~~~~~~~~~
#. IP address/hostname of Key Managment server
#. Credentials and location information for Rabbit MQ
#. IP addresses of dispatcher, monitor, and worker servers

Relevant files 
~~~~~~~~~~~~~~
dispatcherInstaller.tar.gz and the setup directory used during the installation of the
enStratus Key Management software.  Extract the dispatcherInstaller.tar.gz file. There
will be a dispatcher/ directory containing the following items:

Next, move the setup/ directory from the km directory, so that the contents of the
dispatcher/ directory are, after this step:

#. files/
#. installDB.sh
#. installDispatcher.sh
#. setup/

Move the setup directory that was used during the installation of the key management
service into the dispatcher directory and, as root, execute the installDispatcher.sh
script. Follow the prompts to complete the installation of the dispatcher service.  Upon
completion of this step, you will have installed and configured the enStratus dispatcher
service and the provisioning and analytics databases.  

The setup/install.credentials file will be appended with the username and password used by
the dispatcher service to connect to its database along with a list of the configuration
files used to configure the dispatcher service.

Dispatcher Configuration Files
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none

  [ Dispatcher Configuration Files ]

  /services/dispatcher/bin/tomcat
  /services/dispatcher/bin/enstratus
  /services/dispatcher/bin/pinger
  /services/dispatcher/tomcat/webapps/ROOT/META-INF/context.xml
  /services/dispatcher/tomcat/webapps/ROOT/WEB-INF/classes/mq.cfg
  /services/dispatcher/tomcat/webapps/ROOT/WEB-INF/classes/enstratus-km-client.cfg
  /services/dispatcher/tomcat/webapps/ROOT/WEB-INF/classes/enstratus-provisioning.cfg
  /services/dispatcher/tomcat/webapps/ROOT/WEB-INF/classes/dasein-persistence.properties
  /services/dispatcher/tomcat/conf/server.xml
