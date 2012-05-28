Console
-------

The enStratus console is a tomcat service installed to /services/console.

Console Overview
~~~~~~~~~~~~~~~~
The enStratus console service is a tomcat service that provides the web front-end, or enStratus user console.

Starting Console
~~~~~~~~~~~~~~~~
To start the console service:

.. code-block:: bash

	/etc/init.d/enstratus-console start

Console Start Process
^^^^^^^^^^^^^^^^^^^^^
The console init script performs the following action:

#. Executes /services/console/bin/tomcat, passing it the argument: start. This starts the console process.

Stopping Console
~~~~~~~~~~~~~~~~
To stop the console service:

.. code-block:: bash

	/etc/init.d/enstratus-console stop

Console Stop Process
^^^^^^^^^^^^^^^^^^^^
The console init script performs the following action:

#. Executes /services/console/bin/tomcat, passing it the argument: stop. This stops the console process.

