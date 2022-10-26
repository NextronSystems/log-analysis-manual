SHIMcache
=========

The **SHIM Cache** or AppCompatCache (Application Compatibility Cache) is a special Registry cache containing valuable information, because the cache tracks metadata for binary files that were executed.

It includes the full path to the executable file image and a timestamp, which could be the date of the last execution or the creation time stamp of the file, depending on the Windows version.

In cases where the executed file is still present on disk, THOR calculates hashes and includes them in the log message (message enrichment). If you can’t find a hash in the log line, this means that THOR wasn’t able to find the file on disk anymore.

References
----------
`Count Upon Security <https://countuponsecurity.com/2016/05/18/digital-forensics-shimcache-artifacts//>`__

Samples
-------

.. code::

	Aug 26 13:10:21 SRV2345/10.2.0.22 THOR: Warning: MODULE: SHIMCache MESSAGE: Suspicious file name in Shim Cache Entry detected ELEMENT: SYSVOL\Temp\1.exe PATTERN: \ [01]\.exe AND \[A-Za-z0-9]\.(exe|com|dll|bat|scr|vbs)$ AND \[Tt]emp\[0-9a-zA-Z]\.(exe|dll) SCORE: 60 DESC: Typical attacker scheme FILE: SYSVOL\Temp\1.exe DATE: 02/21/17 15:44:32 TYPE: system HIVEFILE: None EXTRAS: N/A N/A True MD5: - SHA1: - SHA256: -

.. code::

	Aug 26 12:02:59 SRV1123.internal.net/10.0.0.112 THOR: Warning: MODULE: SHIMCache MESSAGE: Suspicious file name in Shim Cache Entry detected ELEMENT: D:\Temp\test\ client.exe PATTERN: \client.exe SCORE: 60 DESC: Typical Malware Names FILE: D:\Temp\test\ client.exe DATE: 01/23/17 08:03:37 TYPE: system HIVEFILE: None EXTRAS: N/A N/A False MD5: 099120aca1c34e7a529b3b390cfdbc1e SHA1: 4ece72b9fa13019a4ce8b4229ca7b6aee09d6982 SHA256: c3c336a23021b68b026bdf1642b220d88037039aa6d7f8e7d4d576cc38063088

Typical False Positives
-----------------------

* Legitimate software that uses strange executable locations
* THOR's own scans if administrators chose a suspicious working directory (e.g. ``C:\Temp\``, ``C:\thor\``)

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
  :file: ../csv/shimcache.csv
  :widths: 20, 50, 10, 10, 10
  :delim: ;
  :header-rows: 1