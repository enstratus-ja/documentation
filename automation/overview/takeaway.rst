Takeaway Points
---------------
#. A deployment is a logical grouping of tiers, services, and launch configurations. Resources provisioned as part of a deployment are "special" in the sense that they are subject to the governing rules set by the user.
#. Tiers are logical groupings of servers.
#. Services are software packages that are tied to tiers. 
#. Services can have datasources passed to them and can depend on each other, or each other's datasources.
#. Dependencies tell enStratus how to orchestrate service installation and what information is appropriate to pass to each VM.
#. Launch Configurations define the size of the VM, volumes, configuration management, and firewalls for each server.
#. As servers are started, enStratus orchestrates the installation of services and datasources according to their dependency relationships.

