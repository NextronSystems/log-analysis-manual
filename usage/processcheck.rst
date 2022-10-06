ProcessCheck
============

Different checks are performed in the **ProcessCheck** module. Some of them check the process characteristics such as parent/child relations, process priorities and executable file locations for anomalies. Other checks evaluate the processes network connections and YARA checks match on the process memory. 

References
----------

`nasbench.medium.com <https://nasbench.medium.com/windows-system-processes-an-overview-for-blue-teams-42fa7a617920>`_

Samples
-------

.. code::

	Aug 26 13:02:27 server22.local.net/10.6.19.8 THOR: Warning: MODULE: ProcessCheck MESSAGE: Process started from a typical attacker / malware location PID: 8336 PPID: 5796 PARENT: C:\temp\ProcessMonitor\Procmon.exe NAME: Procmon64.exe OWNER: server-ABC123 COMMAND: "C:\Users\SERVER~4\AppData\Local\Temp\2\Procmon64.exe" /originalpath "C:\temp\ProcessMonitor\Procmon.exe" PATH: C:\Users\SERVER~4\AppData\Local\Temp\2\Procmon64.exe CREATED: 24.08.2017

.. code::

	Aug 26 13:02:55 server.local.net/10.1.19.2 THOR: Warning: MODULE: ProcessCheck MESSAGE: Yara rule match on process PID: 32980 PPID: 4104 PARENT: C:\Program Files\Internet Explorer\iexplore.exe NAME: iexplore.exe OWNER: SYSTEM COMMAND: "C:\Program Files (x86)\Internet Explorer\IEXPLORE.EXE" SCODEF:4104 CREDAT:275457 /prefetch:2 PATH: C:\Program Files (x86)\Internet Explorer\IEXPLORE.EXE CREATED: 24.08.2017 05:00:02 MD5: e3da77b534d7dff8a2ae6a577a44703b CONNECTION_COUNT: 0 LISTEN_PORTS: - RULE: CN_C2_Domain_HvS_Client_A3 DESCRIPTION: THOR HvS Client A3 - C2 domain in file REFERENCE: - SCORE: 75 STRINGS: Str1: .lookipv6.com

Typical False Positives
-----------------------

* Legitimate software started from strange locations
* Old Windows versions (XP, 2003) show abnormal parent/child relation and process priority warnings
* Process end points in suspicious GEO IP regions of the world (e.g. system in China with process connections to other systems in China)
* Process memory scan alerts in processes that may contain clear-text signatures (AV process memory, VMWare tools (copied THOR to the system), GRR, SearchIndexer) 

Attribute Evaluation
--------------------

.. csv-table::
  :file: ../csv/processcheck.csv
  :widths: 20, 50, 10, 10, 10
  :delim: ;
  :header-rows: 1