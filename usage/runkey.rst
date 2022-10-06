RunKeyCheck
===========

The **RunKeyCheck** module processes entries in the RUN Key.  

Samples
-------

.. code::

	Aug 6 11:22:11 server11.local/10.252.8.237 THOR: Warning: MODULE: RunKeyCheck MESSAGE: Suspicious file name in value detected ELEMENT: "C:\Program Files\Microsoft Security Client\msseces.exe" -hide -runkey PATTERN: (?i)\msseces\.exe SCORE: 60 DESC: Executable used by PlugX DLL side-loading in non-standard location Run Key Entry NAME: MSC VALUE: "C:\Program Files\Microsoft Security Client\msseces.exe" -hide -runkey FILE: C:\Program Files\Microsoft Security Client\msseces.exe FIRSTBYTES: 4d5a90000300000004000000ffff0000b8000000 / MZ SHA1: 71fac169a5f04af634d06c367e7d832e72c1cdf2

Typical False Positives
-----------------------

* Elements matching known system files in suspicious locations (see example with ``msseces.exe``)

Attribute Evaluation
--------------------

.. csv-table::
     :file: ../csv/runkey.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1