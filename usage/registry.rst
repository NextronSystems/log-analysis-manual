Registry
========

**Registry** matches can be caused by different signature types: File name IOCs, keywords or YARA signatures matches.

Samples
-------

.. code::

	Aug 29 08:13:37 system123.local.net/10.6.2.10 THOR: Warning: MODULE: Registry MESSAGE: YARA Rule Match KEY: Registry Key CMI-CreateHive{D43B12C1-09B5-40DB-AFF6-F6DFEB78DAEC}\Software\Microsoft\Windows\CurrentVersion\Run with 1 values and 0 subkeys NAME: Suspicious_Startup_Loc_RegistryKey SCORE: 70 DESCRIPTION: Detects suspicious registry values often used by malware REF: - MATCHED_STRINGS: Str1: CurrentVersion\Run;Google Update;"C:\Users\MSchmitz\AppData\Local\Google\Update\GoogleUpdate.exe

.. code::

	Aug 28 08:17:46 system123.local.net/10.10.1.8 THOR: Warning: MODULE: Registry MESSAGE: YARA Rule Match KEY: Registry Key CMI-CreateHive{6A1C4018-97AB-4291-A7DC-7AED1C76667C}\Keyboard Layout\Preload with 3 values and 0 subkeys NAME: Chinese_Keyboard_Layout_RDP_Preload SCORE: 70 DESCRIPTION: Chinese Keyboard Layout settings detected - this hive's user used the chinese keyboard layout REF: http://www.welivesecurity.com/2014/05/20/miniduke-still-duking/ MATCHED_STRINGS: Str1: Keyboard Layout\Preload;2;00000804

Typical False Positives
-----------------------

* Values with system files in rare locations (e.g. backup locations: ``\\backupserv\sysbackup20171119\Windows\system32``)
* Keyboard layout preloads that are typical for the region of the system (e.g. "Chinese keyboard layout" on a system in Shanghai)
* Values that start with ``4d5a`` by pure chance

Attribute Evaluation
--------------------

.. csv-table::
     :file: ../csv/registry.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1