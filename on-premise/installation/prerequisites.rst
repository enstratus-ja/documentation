.. _prerequisites:

Prerequisites
-------------

Before you begin
~~~~~~~~~~~~~~~~

.. note:: When installing MySQL, please set a root password, it will be required during the installation of services that depend on MySQL.

During the installation enStratus will auto-generate mysql users and passwords for the database services it installs. enStratus generates good passwords.

  Example: K0B6KheBDtrANJOEp1LuWpCmjF

If generating your own passwords is something you would like to do. Please do so after
completing the installation by referencing the appropriate configuration files and at your
own risk.  The details of installing this software is dependent on your distribution.
Please have this software installed before attempting an installation of the enStratus
cloud management software.

Key Generation
~~~~~~~~~~~~~~

The purpose of this step is to generate encryption keys and create some bootstrap MySQL
information for the Dispatcher and Console services.

Required Knowledge
~~~~~~~~~~~~~~~~~~

#. enStratus License Key
#. Desired url for the console service. For example, cloud.mycorporation.com 
#. IP address of the server that will run the console server.

Move the keygen bundle to the server that will contain the Key Management service and extract it.
Once extracted, there will be a keygen/ directory containing the following items:

#. classes
#. enstratus-utilities.jar 
#. files
#. keygen.sh
#. setup

Enter the keygen/ directory and, as root, execute the keygen.sh script. You will be
promted for the three pieces of information listed above. The outcome of this script will
be the creation of a file called install.credentials located in the setup/ directory.

For the database-driven services of Key Manager, Dispatcher, and Console, the respective
credentials section of this file are critical. If the installer crashes or is interrupted
after the database installs have run and the credentials have been appended and you want
to start over with the installation of that service, you must first delete the section in
the install.credentials file and the databases that were created.  The requirement to do
this will cease as the installer is improved.

Other Information
~~~~~~~~~~~~~~~~~

Required operating system is Linux. Architecture x86_64. Preferred distribution is
Ubuntu/Debian. While nothing technologically prevents a windows installation, I'll leave
that as an exercise for the reader. :)

The server onto which enStratus is installed can be virtual. They should not, however, be
part of the pool of VMs enStratus is destined to manage.

All machines must have direct, non-vpn network access to each other.

Provisioned/managed VMs must have direct, non-proxied, non-vpn access to the dispatcher
and worker servers.

If an enStratus engineer is performing the installation, we will require shell access with
root privileges to all of the machines onto which enStratus is to be installed.  

enStratus engineers can provide their public SSH key to you for remote access or they can
work through a VPN.  We require port 22, 80, and 443 access externally to our office IP
address: 216.250.165.28.

Requesting installations over a "screenshared" session such as webex is *strongly*
discouraged. It is highly inefficient and greatly increases the possibility of error.

The enStratus software installation process is most suited to a systems administrator with
knowledge of how to install the prerequisites and do basic configuration.


The file (object) storage server will be used for object (file) storage as is essential to
do things like automation and downloading of service images and scripts to running virtual
machines. 

enStratus engineers will also assist on-premise clients with the installation and
configuration of the enStratus agent, a pre-requisite for doing automation.
