ScheduledTasks
==============

The **ScheduledTasks** module analyses the local user at jobs and just lists them in "Info" level messages and applies the global string check on the command line. 

Samples
-------

.. code::

	Aug 2 14:37:48 server44/192.168.2.4 THOR: Notice: MODULE: ScheduledTasks MESSAGE: Noticeable file name in command detected ELEMENT: C:\start1.bat PATTERN: \start1\.bat$ SCORE: 50 DESC: Indian Cyber Attack Task NAME: kpistart1 sabato COMMAND: C:\start1.bat USER: Webload LASTRUN: 15/05/2010 14:02:00 NEXTRUN: 30/11/1999 00:00:00 MD5: 666081523aeff8d40d53b4f6aeedd851 SHA1:

Typical False Positives
-----------------------

* Software updaters
* Administrative jobs

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
     :file: ../csv/scheduled.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1