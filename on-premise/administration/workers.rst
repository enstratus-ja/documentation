.. _workers:

Workers
-------

Worker Overview
~~~~~~~~~~~~~~~~
The enStratus worker service consists of two components, a publisher and a subscriber. At a very high level,
these components:

1. Publisher

  - The publisher is responsible for pushing actions onto a queue. 

2. Subscriber

  - The subscriber is responsible for taking actions off of the queue and acting accordingly.

Starting Worker
~~~~~~~~~~~~~~~
To start the worker service:

.. code-block:: bash

	/etc/init.d/enstratus-workers start

Worker Start Process
^^^^^^^^^^^^^^^^^^^^^
The worker init script performs the following actions:

#. Executes /services/worker/bin/publisher, passing it the argument: start. This starts the publisher process.
#. Executes /services/worker/bin/subscriber, passing it the argument: start. This starts the subscriber process.

Stopping Worker
~~~~~~~~~~~~~~~
To stop the worker service:

.. code-block:: bash

	/etc/init.d/enstratus-workers stop
