WER
=========

The **WER** (Windows Error Reporting) module analyses program crash files and checks for special crashes caused by exploits and filename IOC signature matches in the application path. Software can break, so applications tend to crash, hack tools and exploits crash as well. Even if the attackers completely removed their tools from a system, a crashed exploit code, scanner, password dumper or backdoor will still be visible in the Windows Error Reports.

(Side note: Microsoft's own IR team makes use of the WER file analysis with their own tool named **WOLF**)

Samples
-------

.. code::

	Jun Oct 25 21:01:51 server44.local.net/10.216.2.186 THOR: Notice: MODULE: WER MESSAGE: Error Report - Found AppHang EXE: notepad++.exe DATE: 2011-08-25 07:37:39 FILE: C:\Users\scadmin\AppData\Local\Microsoft\Windows\WER\ReportArchive\AppHang_notepad++.exe_4eafbb67f1329f8691e382b93f71beb6d0fcb99_cfe6cd59_5da093b9\Report.wer APPPATH: C:\Program Files (x86)\Notepad++\notepad++.exe ERROR: - / - FAULT_IN_MODULE: not set

Typical False Positives
-----------------------

* Software is broken so application tend to crash

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
     :file: ../csv/wer.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1