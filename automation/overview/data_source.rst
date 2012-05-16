Add Data Source (optional)
--------------------------

In some cases, it may be appropriate to connect a datasource to a service. In our example
deployment, the lower tier is a database tier and the service connected to it is a
database dump file for MySQL.

By connecting a datasource to a service, enStratus knows to first configure the service,
then pass in the datasource to the service. Proper ordering of operations like that is
called *orchestration*.

.. figure:: ./images/deployment4a.png
   :height: 600px
   :width: 600 px
   :scale: 75 %
   :alt: Data Source Added to Service
   :align: center

   Data Source Added to Service
