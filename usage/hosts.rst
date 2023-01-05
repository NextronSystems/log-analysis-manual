Hosts
=========

The ``Hosts`` module evaluates the entries in the local hosts file.

References
----------

`blog.malwarebytes.com <https://blog.malwarebytes.com/cybercrime/2016/09/hosts-file-hijacks/>`_

Samples
-------

.. code::

	Aug 26 11:46:14 server555.local.net/10.7.1.14 THOR: Warning: MODULE: Hosts MESSAGE: New hosts entry - not found during the last run ENTRY: master.comp-a.net IP: 10.7.10.2 SCORE: 75

.. code::

	Jul 29 12:16:18 server99.local.net/10.1.1.55 THOR: Warning: MODULE: Hosts MESSAGE: Suspicious entry found in Hosts file ENTRY: ctldl.windowsupdate.com IP: 127.0.0.1 SCORE: 75

Typical False Positives
-----------------------

* Entries on development systems to simulate future DNS resolution (e.g. ``www.company-intranet.net    10.0.2.28``)
* Some Antivirus tools insert entries into the hosts file to immunize the system (e.g. ``Spybot Search & Destroy``)

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
     :file: ../csv/hosts.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1