AmCache
=======

The **AmCache** module processes entries in the AmCache of the system. In contrast to the SHIMCache entries, AmCache entries contain a SHA1 hash value that can be used to determine the exact program that was executed on the end system. 

References
----------

| `www.swiftforensics.com <http://www.swiftforensics.com/2013/12/amcachehve-in-windows-8-goldmine-for.html>`_
| `windowsir.blogspot.de <https://windowsir.blogspot.de/2017/03/incorporating-amcache-data-into.html>`_

Samples
-------

.. code::

	Aug 26 16:14:22 server33.local/10.1.2.31 THOR: Warning: MODULE: Amcache MESSAGE: Suspicious file name in Amcache entry detected ELEMENT: C:\temp\1.exe PATTERN: \(tmp|temp)\[a-zA-Z0-1]\.(exe|com) AND \[01]\.exe AND \[A-Za-z0-9]\.(exe|com|dll|bat|scr|vbs)$ AND (temp|tmp)\[0-9]{1,50}\.exe$ AND \[Tt]emp\[0-9a-zA-Z]\.(exe|dll) SCORE: 60 DESC: Typical attacker scheme FILE: C:\temp\1.exe SHA1: 9cf9c57b0927c45d6712387871dd435053d912b6 SIZE: None DESC: None FIRST_RUN: 2017-05-22 15:41:00.021779 CREATED: 0001-01-01

.. code::

	Aug 19 13:08:49 server4448.local.net/10.0.10.1 THOR: Warning: MODULE: Amcache MESSAGE: Suspicious file name in Amcache entry detected ELEMENT: C:\Users\blueprism\FPipe.exe PATTERN: FPipe.exe AND \(Users|Documents and Settings)\[^\]{1,20}\[^\]{1,20}\.(exe|dll|vbs|bat|ps1) SCORE: 75 DESC: Pattern in Amcache entry FILE: C:\Users\Public\FPipe.exe SHA1: 41d57d356098ff55fe0e1f0bcaa9317df5a2a45c SIZE: 13312 DESC: FPipe FIRST_RUN: 2017-07-12 14:13:32.823776 CREATED: 2017-07-12 14:13:26.886278 PRODUCT: FPipe COMPANY: Foundstone

Typical False Positives
-----------------------

* Legitimate files in suspicious locations
* Elements matching known system files in suspicious locations

Attribute Evaluation
--------------------

.. csv-table::
     :file: ../csv/amcache.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1