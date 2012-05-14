Set Dependencies
----------------

This step is critical. Dependencies let enStratus know how to *orchestrate* the deployment
launch and service configuration.

For this tutorial, we're going to set a dependency for the wordpress service. It's going
to depend on the *data source* installed as part of the MySQL service. What this means is
that at run time, enStratus will ensure:

1. The MySQL service is installed and successfully configured
2. The datasource is successfully installed on the MySQL service.

and then, and only then will

3. The application service be installed, since it *depends* on steps 1 and 2.

To set up a dependency, select the actions menu on the wordpress service.

.. figure:: ./images/dependency0.png
   :height: 500px
   :width: 1900 px
   :scale: 50 %
   :alt: Dependency
   :align: center

   Dependency

.. figure:: ./images/dependency1.png
   :height: 300px
   :width: 850 px
   :scale: 50 %
   :alt: Dependency, Add
   :align: center

   Dependency, Add

Choose Target Type: Data Source, and select the previously created data source from the
menu.

.. figure:: ./images/dependency2.png
   :height: 400px
   :width: 850 px
   :scale: 50 %
   :alt: Dependency, Data Source
   :align: center

   Dependency, Data Source

.. figure:: ./images/dependency3.png
   :height: 400px
   :width: 850 px
   :scale: 50 %
   :alt: Dependency, Saved
   :align: center

   Dependency, Saved
