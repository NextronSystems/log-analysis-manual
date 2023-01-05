ProcessConnection
=================

The ``ProcessConnections`` module checks the network connections of
a process and generates alerts and warnings based on C2 signature
matches and suspicious GEO IP lookups.

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

.. raw:: html

        <script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/1.7.1/jquery.min.js"></script>
        <script>
        $(document).ready(function() {
        $('table p:contains("Yes")').parent().addClass('yes');
        $('table p:contains("No")').parent().addClass('no');
        $('table p:contains("Bad")').parent().addClass('bad');
        $('table p:contains("Good")').parent().addClass('good');
        $('table p:contains("Low")').parent().addClass('low');
        $('table p:contains("Medium")').parent().addClass('medium');
        $('table p:contains("High")').parent().addClass('high');
        });
        </script>
        <style>
        .yes {text-align: center;}
        .no {text-align: center;}
        .good {background-color:#64c864 !important; text-align: center;}
        .bad {background-color:#c86464 !important; text-align: center;}
        .low {background-color:#cccccc !important; text-align: center;}
        .medium {background-color:#aaaaaa !important; text-align: center;}
        .high {background-color:#8a8a8a !important; text-align: center;}
        </style>

.. csv-table::
     :file: ../csv/processcon.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1