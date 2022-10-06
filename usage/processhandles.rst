ProcessHandles
==============

The **ProcessHandles** module is a sub module of the **ProcessCheck** module that analyses the handles of each process. The module makes use of the SysInternals ``handle.exe`` tool that can be placed in the ``./tools`` sub folder.    

Samples
-------

.. code::

	Jun 24 11:52:08 server77.local.net/10.1.90.18 THOR: Warning: MODULE: ProcessHandles MESSAGE: Suspicious file name in Process Handle detected VALUE: D:\Lotus\Domino\data\mail\htrang.nsf PATTERN: \htran SCORE: 75 DESC: Diverse PID: 1068 COMMAND: D:\Lotus\Domino\nserver.exe =D:\Lotus\Domino\notes.ini -j HANDLEID: EF0 HANDLE: File (RW-)

.. code::

	Aug  4 11:44:08 serv55123/10.2.47.43 THOR: Alert: MODULE: ProcessHandles MESSAGE: Malware file name in Process Handle detected VALUE: G:\Documents\InfoStream\mimikatz-master PATTERN: \mimikatz AND mimikatz SCORE: 145 DESC: Allgemein PID: 4 COMMAND: N/A HANDLEID: 11698 HANDLE: File  (RWD)

Typical False Positives
-----------------------

* Legitimate administrative activity that looks suspicious

Attribute Evaluation
--------------------

.. csv-table::
     :file: ../csv/processhandles.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1