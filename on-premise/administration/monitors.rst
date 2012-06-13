.. _monitors:

Monitors
--------

The enStratus monitor service is a java service installed to /services/monitor.

Monitor Overview
~~~~~~~~~~~~~~~~

.. note:: The enStratus monitors service is in the process of being deprecated in favor of
   a more efficient workers process. 

The enStratus monitors service is responsible for maintaining an accurate representation of cloud state,
checking on the completion of jobs initiated by the dispatcher service, orchestrating server launches and
service installations.

Starting Monitor
~~~~~~~~~~~~~~~~

To start the monitor services:

.. code-block:: bash

	/etc/init.d/enstratus-monitor start

Monitor Start Process
^^^^^^^^^^^^^^^^^^^^^

The monitor init script performs the following actions:

#. Executes /services/monitor/bin/assign. This starts the assignment service, which is responsible for controlling the monitor services.
#. The monitor start process cycles through a list of monitors designated in the file
   called /services/monitor/etc/monitors.cfg, executing a call to /services/monitor/bin/poll,
   with the start argument, as shown. Each monitor process has an associated log file located
   in /services/monitor/log.

.. code-block:: bash

	Starting assign
	Starting assignment...
	Started 0.
	Starting monitors.
	/services/monitor/bin/poll start Address 1
	/services/monitor/bin/poll start AutoScaling 1
	/services/monitor/bin/poll start Backup 1
	/services/monitor/bin/poll start Budget 1
	/services/monitor/bin/poll start Dc 1
	/services/monitor/bin/poll start Deployment 1
	/services/monitor/bin/poll start DeploymentAnalytics 1
	/services/monitor/bin/poll start Distribution 1
	/services/monitor/bin/poll start Dns 1
	/services/monitor/bin/poll start ExchangeRate 1
	/services/monitor/bin/poll start ForwardingRule 1
	/services/monitor/bin/poll start Image 1
	/services/monitor/bin/poll start Invoice 1
	/services/monitor/bin/poll start KeyValue 1
	/services/monitor/bin/poll start LoadBalancer 1
	/services/monitor/bin/poll start Maintenance 1
	/services/monitor/bin/poll start Notifications 1
	/services/monitor/bin/poll start Prepayment 1
	/services/monitor/bin/poll start Rdbms 1
	/services/monitor/bin/poll start ScalingEvent 1
	/services/monitor/bin/poll start ScalingEventProcess 1
	/services/monitor/bin/poll start Server 1
	/services/monitor/bin/poll start ServerAnalytics 1
	/services/monitor/bin/poll start Snapshot 1
	/services/monitor/bin/poll start Ssl 1
	/services/monitor/bin/poll start Subscription 1
	/services/monitor/bin/poll start TierAnalytics 1
	/services/monitor/bin/poll start Volume 1
	/services/monitor/bin/poll start VPNGateway 1

Stopping Monitor
~~~~~~~~~~~~~~~~
To stop the monitor services:

.. code-block:: bash

	/etc/init.d/enstratus-monitor stop

Monitor Stop Process
^^^^^^^^^^^^^^^^^^^^
The monitor init script performs the following actions:

#. Executes /services/dispatcher/bin/assign, passing the stop argument. This stops the assignment service.
#. The monitor start process cycles through a list of monitors designated in the file
   called /services/monitor/etc/monitors.cfg, executing a call to /services/monitor/bin/poll,
   with the stop argument, as shown. Each monitor process has an associated log file located
   in /services/monitor/log.

.. note:: The monitor stop process is slow and not terribly reliable. A less elegant, yet faster method for
	 terminating the monitor processes is to issue the command:

	 ps -ef | grep onit | awk '{print $2}' | while read line; do kill -9 $line; done
