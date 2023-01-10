FileScan
========

Events reported by the ``FileScan`` module typically originate
from the file system scan. But due to the "Message Enrichment"
feature, other modules that include events with full "file path"
strings may also produce events of this type (e.g. module ``SHIMCache``, ``Eventlog``).

Filescan events are rich in attributes and extra information.

Sample
------

.. code-block:: none

    Dec 2 19:29:43 PROMETHEUS/10.0.2.4
    THOR: Notice: MODULE: Filescan
    MESSAGE: Suspicious file found
    FILE: C:\Program Files (x86)\HaoZip\HaoZipExt64.dll
    SCORE: 54
    MD5: 60873d6560b29bdb30235e05eda97539
    SHA1: d312157d7c890a68eed85c5a2fd17fdfe6defa87
    OWNER: BUILTIN\Administrators
    SIZE: 513800
    TYPE: EXE
    FIRSTBYTES: 4d5a90000300000004000000ffff0000b8000000 / MZ
    COMPANY: ACME
    DESC: 2345-Windows
    CREATED: Thu Jul 26 05:20:04 2012
    MODIFIED: Thu Jul 26 05:20:04 2012
    ACCESSED: Fri Sep 20 12:47:39 2013
    REASON_1: Haozip_SFX / Haozip SFX Compressed Executable
      Score: +50
      Trigger: Specific Rule Value:
        Str1: release\pdb\HaoZip

Typical False Positives
-----------------------

- Legitimate files matching a filename regular expression IOC
- YARA rules matching THOR reports or clear-text signatures from former scans have been left on the system
- Dual use tools used by administration (e.g. ``nmap.exe``, ``ncat.exe``)
- Legitimate tools moved to the Recycle Bin and therefore detected with wrong name (e.g. ``Psexec`` as ``$IR4HB6A.exe``)
- Legitimate but very old files that trigger the file size anomaly
- Old and rare versions of legitimate programs that trigger the file signature anomalies (that often happens with ``javaw.exe`` / ``java.exe``)

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
  :file: ../csv/filescan1.csv
  :widths: 20, 50, 10, 10, 10
  :delim: ;
  :header-rows: 1

Typical REASONs
---------------

.. csv-table::
  :file: ../csv/filescan2.csv
  :widths: 20, 50, 10, 10, 10
  :delim: ;
  :header-rows: 1