CommandCheck
============

The **CommandCheck** module is a meta module that analyses full command lines (path, executable, parameters) in different modules.

Samples
-------

.. code::

	May 20 12:25:49 server55.local.net/10.1.12.2 THOR: Warning: MODULE: CommandCheck MESSAGE: Command in suspicious location PATH: C:\Windows\TEMP\vmw72DE.tmp\guestcustutil.exe SCORE: 75

.. code::

	May 6 11:26:59 server88.local.net/10.10.9.33 THOR: Warning: MODULE: CommandCheck MESSAGE: Command in suspicious location PATH: d:\temp\aaa.cmd SCORE: 75

Typical False Positives
-----------------------

* Legitimate administrative activity that looks suspicious

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
     :file: ../csv/command.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1