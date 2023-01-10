LogScan
===========

The ``LogScan`` module processes ``*.log`` files found on disk line by
line (It performs some checks to avoid scanning files that are not ASCII
log files, but something else that uses the ``*.log`` extension).
Each log line is checked with all file name and keyword IOCs and
scanned with the "keyword" and "log" type YARA rules. 

Samples
-------

.. code-block:: none

	Aug 26 18:58:32 System23.local.net/10.2.2.14
        THOR: Warning: MODULE: LogScan
        MESSAGE: Suspicious file name in Log Entry detected
        ELEMENT: Deleted file - E:\TEAM-TRANSFER\4Helmut\Tools\PortScan.exe
        PATTERN: \PortScan.exe
        SCORE: 65
        DESC: PortScanner Names
        FILE: D:\ scripts\log\TEAM-TRANSFER.CLEANUP.cmd.2015-09-27.log
        LINE: 320

.. code-block:: none

	Aug 27 10:40:30 System23.local.net/10.2.2.14
        THOR: Warning: MODULE: LogScan
        MESSAGE: Suspicious file name in Log Entry detected
        ELEMENT: /EN/cmd.exe /c+dir "C:\data\inetpub\wwwroot\EN\cmd.exe" 404 "SW0123" - -2147024864 - - 0 10.10.9.24 443 - "gi.webshop.com" - 09:48:18.024 "HTTP/1.1" "https" 1405 102
        PATTERN: ([C-Zc-z]:|\\).{1,40}\

Typical False Positives
-----------------------

- Web vulnerability scans trying to access files that do not exist (HTTP Error 404)
- RoboCopy logs that list hack tools like ``nmap.exe`` or ``ncat.exe``

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
     :file: ../csv/logscan.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1