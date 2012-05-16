Deployment Configuration
========================

.. toctree::
   :maxdepth: 1

   user_interface
   deployment_management
   load_balancers
   tier
   services
   data_sources
   machine_images
   launch_configuration
   ssl
   backups

.. note:: Some of the screenshots may look different than the ones shown here. The
   difference in all cases should be cosmetic and not affect operations.

The purpose of this section is to walk through the deployment configuration options in
enStratus. 

In the `Overview <../introduction/overview.html>`_ section, we covered the concepts
involved with creating an enStratus deployment.

.. note:: 
  Before approaching deployment configuration, you should have in hand the
  following components:

  #. Working machine images/templates with the enStratus agent installed and tested.
  #. Service images for each application/database to be installed.

enStratus knows about is the environment in which your application/database runs and it
will inform your services about that environment. 

enStratus gives you all the tools to deploy and manage a fully automated environment.

