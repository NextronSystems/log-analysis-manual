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

.. csv-table::
     :file: ../csv/command.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1