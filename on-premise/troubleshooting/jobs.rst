.. _enstratus_jobs:

enStratus Jobs
--------------

enStratus spawns many jobs, the server jobs will sometimes run interminably, here's how to
fix that:

You can mark any job as complete (or, more likely, just delete them outright) from the
enstratus_job table.

.. note:: The enstratus_job table is in the provisioning database.

Deleting Old Jobs
~~~~~~~~~~~~~~~~~

Run something like this to just get rid of weird old ones:

.. code-block:: mysql

   select *,from_unixtime(start_timestamp/1000) as started from enstratus_job where 
   start_timestamp < ((UNIX_TIMESTAMP() - 100000) * 1000) ;

verify that those are ones to get rid of.  (Ones that are a bit older than 1 day.)  

Then:

.. code-block:: mysql

  delete from enstratus_job where start_timestamp < ((UNIX_TIMESTAMP() - 100000) * 1000) ;

Deleting All Jobs
~~~~~~~~~~~~~~~~~

No harm will come to the system, though it might confuse some users.

.. code-block:: mysql

   delete from enstratus_job where end_timestamp is NULL;
