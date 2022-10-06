ProcessConnection
=================

The **ProcessConnections** module checks the network connections of a process and generates alerts and warnings based on C2 signature matches and suspicious GEO IP lookups.

Samples
-------

.. code::

	Oct 25 17:33:17 server66.local.net/147.2.20.16 THOR: Notice: MODULE: ProcessConnections MESSAGE: Established connection PID: 3012 NAME: dfssvc.exe COMMAND: C:\Windows\system32\dfssvc.exe LIP: 147.2.20.16 LPORT: 56513 RIP: 147.2.21.188 RPORT: 53389

.. code::

	Oct 25 17:33:17 server66.local.net/10.1.30.2 THOR: Notice: MODULE: ProcessConnections MESSAGE: Relevant remote region GEO IP lookup PID: 3012 NAME: p.exe COMMAND: C:\Windows\system32\p.exe LIP: 10.1.30.2 LPORT: 56513 RIP: 14.102.172.144 RPORT: 6022 COUNTRY: PK

Typical False Positives
-----------------------

* A Legitimate software updater that receive updates directly from 3rd party systems
* OS or AV telemetry services (often related to Microsoft, Google, Symantec, McAfee, etc.)
* Legitimate connections to service providers or branch office servers 

Attribute Evaluation
--------------------

.. csv-table::
     :file: ../csv/processcon.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1