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

.. csv-table::
     :file: ../csv/scheduled.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1