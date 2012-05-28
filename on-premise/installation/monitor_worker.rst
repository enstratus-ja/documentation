Monitor/Worker
--------------

Required Knowledge
~~~~~~~~~~~~~~~~~~
#. IP address/hostname of dispatcher and worker servers

Relevant files 
~~~~~~~~~~~~~~
monitorWorkerInstaller.tar.gz and the setup directory used during the installation of the
enStratus Dispatcher software.

Extract the monitorWorkerInstaller.tar.gz file. There will be a worker/ directory
containing the following items:

#. files
#. installMonitor.sh 
#. installWorker.sh

Next, move the setup/ directory from the dispatcher directory, so that the contents of the
monitorWorker/ directory are, after this step:

#. files/
#. installMonitor.sh 
#. installWorker.sh
#. setup/

Move the setup directory that was used during the installation of the dispatcher service
and, as root, execute the installMonitor.sh and then the installWorker.sh script.

Follow the prompts to complete the installation of the services.  

Upon completion of this step, you will have installed and configured the enStratus monitor
and worker services.  The setup/install.credentials file will be appended with the list of
the configuration files used to configure the worker service.

Monitor/Worker Configuration Files
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: none

  [ Monitor Configuration Files ]

  /services/monitor/bin/assign
  /services/monitor/bin/controller
  /services/monitor/bin/monitor
  /services/monitor/bin/pinger
  /services/monitor/classes/enstratus-km-client.cfg
  /services/monitor/classes/enstratus-provisioning.cfg
  /services/monitor/classes/mq.cfg
  /services/monitor/etc/cloud.properties
  /services/monitor/etc/monitors.cfg

  [ Workers Configuration Files ]

  /services/worker/classes/dasein-persistence.properties
  /services/worker/classes/enstratus-km-client.cfg
  /services/worker/classes/enstratus-provisioning.cfg
  /services/worker/classes/worker.properties
  /services/worker/classes/mq.cfg
  /services/worker/bin/pinger
  /services/worker/bin/worker
  /services/worker/bin/publisher
  /services/worker/bin/subscriber
