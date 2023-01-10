RunKeyCheck
===========

The ``RunKeyCheck`` module processes entries in the RUN Key.  

Samples
-------

.. code-block:: none

	Aug 6 11:22:11 server11.local/10.252.8.237
        THOR: Warning: MODULE: RunKeyCheck
        MESSAGE: Suspicious file name in value detected
        ELEMENT: "C:\Program Files\Microsoft Security Client\msseces.exe" -hide -runkey
        PATTERN: (?i)\msseces\.exe
        SCORE: 60
        DESC: Executable used by PlugX DLL side-loading in non-standard location Run Key Entry
        NAME: MSC
        VALUE: "C:\Program Files\Microsoft Security Client\msseces.exe" -hide -runkey
        FILE: C:\Program Files\Microsoft Security Client\msseces.exe
        FIRSTBYTES: 4d5a90000300000004000000ffff0000b8000000 / MZ
        SHA1: 71fac169a5f04af634d06c367e7d832e72c1cdf2

Typical False Positives
-----------------------

- Elements matching known system files in suspicious locations (see example with ``msseces.exe``)

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
     :file: ../csv/runkey.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1