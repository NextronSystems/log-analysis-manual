ServiceCheck
============

The **ServiceCheck** module evaluates all registered local Windows services. It detects suspicious service entries by different anomaly checks, blacklisted keywords and reports file path anomalies. 

Samples
-------

.. code::

	Aug 1 15:14:26 server88.localnet/192.168.2.4 THOR: Warning: MODULE: ServiceCheck MESSAGE: Service started from typical attacker location KEY: srvany SERVICE_NAME: srvany IMAGE_PATH: c:\srvany.exe SHA1: 7c5329229042535fe56e74f1f246c6da8cea3be8 START_TYPE: unknown USER: LocalSystem SCORE: 75

.. code::

	Jul 1 11:52:41 server77.local.net/10.10.9.19 THOR: Warning: MODULE: ServiceCheck MESSAGE: Service started from suspected attacker location KEY: cpuz139 SERVICE_NAME: cpuz139 IMAGE_PATH: \??\C:\Users\u23491\AppData\Local\Temp\cpuz139\cpuz139_x64.sys SHA1: 13df48ab4cd412651b2604829ce9b61d39a791bb START_TYPE: ONDEMAND_START USER: SCORE: 75

.. code::

	Nov 20 11:44:52 PROMETHEUS/10.0.2.4 THOR: Warning: MODULE: ServiceCheck MESSAGE: YARA Rule Match in service STRING: loadersvc - {993B4A05-7C9E-4DA7-9052-4192A3B96F21} - C:\Testing\uixvd.exe NAME: Malicious_Keylogger_Service_Driver SCORE: 65 DESCRIPTION: Detects malicious keylogger service driver - loadersvc REF: - MATCHED_STRINGS: Str1: loadersvc KEY: loadersvc SERVICE_NAME: {993B4A05-7C9E-4DA7-9052-4192A3B96F21} IMAGE_PATH: C:\Testing\uixvd.exe MODIFIED: 2017-03-17T10:53:51.143664 SHA1: - START_TYPE: ONDEMAND_START USER: LocalSystem

Typical False Positives
-----------------------

* Legitimate software with service binaries located in suspicious folders (e.g. the user's ``%AppData%`` folder)
* Services with matching regular expression file name IOCs
* Services registered by administrators in suspicious locations (e.g. ``C:\srvany.exe``)

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
  :file: ../csv/servicecheck.csv
  :widths: 20, 50, 10, 10, 10
  :delim: ;
  :header-rows: 1