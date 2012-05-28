Console
-------

Required Knowledge
~~~~~~~~~~~~~~~~~~
#. None :)

Relevant files 
~~~~~~~~~~~~~~
consoleInstaller.tar.gz and the setup directory used during the
installation of the enStratus Monitor and Worker services.

Extract the consoleInstaller.tar.gz file. There will be a console/ directory containing
the following items:

#. files
#. installDB.sh
#. installConsole.sh

Next, move the setup/ directory from the monitorWorker/ directory, so that the contents of the
console/ directory are, after this step:

Follow the prompts to complete the installation of the console service.

#. files/
#. installDB.sh
#. installConsole.sh
#. setup/

Upon completion of this step, you will have installed and configured the enStratus console
service along with the console and enstratus console datbases.

The setup/install.credentials file will be appended with the username and password used by
the console service to connect to its database along with a list of the configuration
files used to configure the console service.

Console Configuration Files
~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none

  [ Console Configuration Files ]

  /services/console/bin/tomcat
  /services/console/bin/enstratus
  /services/console/tomcat/webapps/ROOT/META-INF/context.xml
  /services/console/tomcat/webapps/ROOT/WEB-INF/classes/enstratus-webservices.cfg
  /services/console/tomcat/webapps/ROOT/WEB-INF/classes/dasein-persistence.properties
  /services/console/tomcat/webapps/ROOT/WEB-INF/classes/enstratus-console.cfg
  /services/console/tomcat/webapps/ROOT/WEB-INF/classes/custom/networks.cfg
