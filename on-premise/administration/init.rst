Init Scripts
------------

Each service should have installed an associated init script, located in /etc/init.d/

enStratus Init Scripts
~~~~~~~~~~~~~~~~~~~~~~

.. tabularcolumns:: |l|l|l|

+----------------+----------------------------------+-------------+
| Component      | Init Script                      | Usage       |
+================+==================================+=============+
| Key Management | /etc/init.d/enstratus-km         | start, stop |
+----------------+----------------------------------+-------------+
| Dispatcher     | /etc/init.d/enstratus-dispatcher | start, stop |
+----------------+----------------------------------+-------------+
| Monitor        | /etc/init.d/enstratus-monitor    | start, stop |
+----------------+----------------------------------+-------------+
| Worker         | /etc/init.d/enstratus-worker     | start, stop |
+----------------+----------------------------------+-------------+
| Console        | /etc/init.d/enstratus-console    | start, stop |
+----------------+----------------------------------+-------------+
