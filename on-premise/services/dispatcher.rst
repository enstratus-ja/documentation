Dispatcher
----------

The enStratus Dispatcher service is a tomcat service installed to /services/dispatcher.

Dispatcher Overview
~~~~~~~~~~~~~~~~~~~
The dispatcher service is the heart of the enStratus provisioning operations. It is responsible for executing
user-initiated actions from the enStratus console.

Starting Dispatcher
~~~~~~~~~~~~~~~~~~~
To start the Dispatcher service:

.. code-block:: bash

	/etc/init.d/enstratus-dispatcher start

Dispatcher Start Process
^^^^^^^^^^^^^^^^^^^^^^^^
The dispatcher init script performs two actions:
#. Executes /services/dispatcher/bin/pinger. This starts the pinger service.
#. Passes the start argument to /services/dispatcher/bin/tomcat, which starts the dispatcher service. 

.. code-block:: bash

	Starting pinger.
	Starting Dispatcher.
	Using CATALINA_BASE:   /services/dispatcher/tomcat
	Using CATALINA_HOME:   /services/dispatcher/tomcat
	Using CATALINA_TMPDIR: /services/dispatcher/tomcat/temp
	Using JRE_HOME:       /usr/lib/jvm/java-6-sun

The pinger is an auxiliary service which is responsible for performing a type of heartbeat operation for
virtual machines provisionined in the cloud.

The dispatcher service will start, and a java service will run on port 3302.

.. code-block:: bash

	netstat -tnlup | grep 3302
	tcp6       0      0 :::3302                 :::*                    LISTEN 7199/java  

Stopping Dispatcher
~~~~~~~~~~~~~~~~~~~
To stop the Dispatcher service:

.. code-block:: bash

	/etc/init.d/enstratus-dispatcher stop

	root@ubuntu:/home/greg# stopDispatcher 
	Stopping Dispatcher.
	Using CATALINA_BASE:   /services/dispatcher/tomcat
	Using CATALINA_HOME:   /services/dispatcher/tomcat
	Using CATALINA_TMPDIR: /services/dispatcher/tomcat/temp
	Using JRE_HOME:       /usr/lib/jvm/java-6-sun

Dispatcher Stop Process
^^^^^^^^^^^^^^^^^^^^^^^
The dispatcher init script passes the stop argument to /services/dispatcher/bin/tomcat, which stops the dispatcher
service.

.. note:: The stop argument does not stop the pinger service. This is expected behavior.


