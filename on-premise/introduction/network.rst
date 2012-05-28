Networking Requirements
-----------------------

enStratus components must have direct communications with each other. To enable enStratus agent communication
on the guest VM, please make the following considerations:

Dispatcher Service 
~~~~~~~~~~~~~~~~~~

The dispatcher service listens on port 3302. Provisioned (guest) virtual machines that have the agent
installed upon them must be able to reach the dispatcher service on this port.

Agent
~~~~~

The enStratus agent listens on port 2003 and can be installed on guest virtual machines. The server(s) upon
which the dispatcher and workers service runs must be able to communicate to the agent on this port.

To summarize:

* Communication from guest virtual machines to the dispatcher server on port 3302

* Communication from the dispatcher service to the guest virtual machines on port 2003

enStratus Communications
~~~~~~~~~~~~~~~~~~~~~~~~

The purpose of this section is to clarify the communication channels required by the individual enStratus
components. Ports listed are default and/or standard service ports and are subject to any customizations made
by the installing engineers.

Example
^^^^^^^
Let's assume that the enStratus installation is using the 4-server model shown above. The worker and
dispatcher servers and their associated services can be moved as necessary to a separate network provided the
communication paths between remain. This principle holds for any of the enstratus components.

enStratus has a very flexible architecture. If you are an administrator of the enStratus software, you should
feel free to move components and architect the most appropriate solution for your cloud environment.

enStratus Internal/External Communications
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. tabularcolumns:: |l|l|p{5cm}|p{5cm}|

+--------------------+-----------------+----------------------------------------------------+---------------------------------------------------------------+
| Component          | Listens IP:Port | Accepts From                                       | Initiates To                                                  | 
+====================+=================+====================================================+===============================================================+
| Console            | $IP:80, $IP:443 | Internet (or equivalent), API, LDAP/AD             | LDAP/AD, Dispatcher, Console (MySQL)                          |
+--------------------+-----------------+----------------------------------------------------+---------------------------------------------------------------+
| Console (MySQL)    | $IP:3306        | Console Service, API, LDAP/AD                      | N/A                                                           |
+--------------------+-----------------+----------------------------------------------------+---------------------------------------------------------------+
| KM                 | $IP:2013        | Dispatcher, Worker, Monitor                        | KM (MySQL)                                                    |
+--------------------+-----------------+----------------------------------------------------+---------------------------------------------------------------+
| Dispatcher         | $IP:3302        | Internet (guest vm), API, Monitor, Worker, Console | Dispatcher (MySQL), Rabbit MQ, KM, Monitor, Worker, Cloud API |
+--------------------+-----------------+----------------------------------------------------+---------------------------------------------------------------+
| Dispatcher (MySQL) | $IP:3306        | Dispatcher, Monitor, Worker                        | N/A                                                           |
+--------------------+-----------------+----------------------------------------------------+---------------------------------------------------------------+
| Monitor/Worker     | N/A             | N/A                                                | Cloud API, Dispatcher, Dispatcher MySQL, Rabbit MQ, KM        |
+--------------------+-----------------+----------------------------------------------------+---------------------------------------------------------------+
| Rabbit MQ          | $IP:5672        | Dispatcher, Monitor, Worker                        | N/A                                                           |
+--------------------+-----------------+----------------------------------------------------+---------------------------------------------------------------+
| API                | $IP:15000       | Internet (or equivalent)                           | Dispatcher, Console MySQL                                     |
+--------------------+-----------------+----------------------------------------------------+---------------------------------------------------------------+
