Prerequsites
------------

Automation is often a task with many moving parts, here are some things to consider before
attempting automation.

Cloud
~~~~~
Your cloud provider must be reliable enough to start VM in a timely fashion. A scalable
application stack will typically require the starting and stopping of many vm
simultaneously.

Storage
~~~~~~~
enStratus considers two types of cloud storage: Block and File. File storage is also known
as object storage. enStratus automation depends heavily on cloud files storage. 

Block storage is sometimes referred to as a "data" disk offering. This type of storage can
also be quite useful during automation, although it is not required.

Application
~~~~~~~~~~~
Attempting to do automation (scaling, recovery, cross-cloud) requires intimate application
knowledge. The biggest challenge when it comes to automation is at the application layer. 

Being able to handle a dynamically provisioned infrastructure on an application is the
first step to being able to leverage dynamically provisioned resources. 

Best Practices
~~~~~~~~~~~~~~

#. IP Addresses. Often, IP addresses change with every newly provisioned instance. A cloudy application will be able to leverage this for scalability.
#. Storage. Storing data on ephemeral storage is risky, putting application/database data on more persistent data storage is preferable.
#. Backups. enStratus considers two types of backups: Snapshots and Service. Used in combination, these backups provide a very reliable and customizable solution.

  * Snapshots: Backups accomplished by taking a snapshot of a data volume. The result of this operation is a snapshot.
  * Services: Backups accomplished by calling a user defined script. The result of this operation is a file, which can be stored in cloud files storage.

#. Disaster Recovery. Disaster recovery for enStratus means storing the files resulting
   from service backups in a geographically distinct cloud region (EC2 East, West, etc...) or
   a separate cloud altogether. 
