Autoruns
========

The ``Autoruns`` module makes use of the command line version of SysInternals
Autoruns. It parses the tools output and integrates the output in each log message.

References
----------

- `Microsoft Sysinternals <https://learn.microsoft.com/en-us/sysinternals/downloads/autoruns>`_

Issues
------

The hash generation for the SHA1 hash in Autorunsc.exe is not reliable.
The reason for this is unknown. The issue has been reported but hasn't
been fixed so far. The value is therefore suppressed.

Samples
-------

.. code-block:: none

    Aug 26 18:48:28 system.internal.net/10.1.2.50
    THOR: Warning: MODULE: Autoruns
    MESSAGE: New or changed autoruns element
    LOCATION: HKLM\System\CurrentControlSet\Services
    ENTRY: SymELAM
    ENABLED: enabled
    CATEGORY: Drivers
    PROFILE: System-wide
    DESC: Symantec
    ELAM PUBLISHER: Symantec Corporation
    IMAGE_PATH: c:\windows\system32\drivers\sep\0c011b95\19c8.105\x64\symelam.sys
    LAUNCH_STRING: system32\Drivers\SEP\0C011B95\19C8.105\x64\SymELAM.sys
    MD5: 20f758e6339a16f97dd83389d582e09a
    SHA1: -
    SHA256: 837016154b7952b645b5545aeb8e2a8878efa8674e6b96471c3db5e458b06960
    SCORE: 60

.. code-block:: none

    Aug 26 13:00:55 system.internal.net/10.1.2.50
    THOR: Warning: MODULE: Autoruns
    MESSAGE: Autoruns element located in a suspicious location
    MATCH_STRING: \temp\
    LOCATION: HKLM\System\CurrentControlSet\Services
    ENTRY: inject3526
    ENABLED: enabled
    CATEGORY: Services
    PROFILE: System-wide
    DESC: -
    PUBLISHER: -
    IMAGE_PATH: c:\users\markschmitt\appdata\local\temp\inject23.exe
    LAUNCH_STRING: C:\Users\markschmitt\AppData\Local\Temp\inject23.exe
    MD5: 7f9a4835a7a237d2873901bb73d00e7b
    SHA1: -
    SHA256: d21d4ad73b848488890bf7f846daff7455062801d0d86238d99591219878f36a
    SCORE: 75

Typical False Positives
-----------------------

- New entries that are legitimate
- Legitimate software that uses strange autorun locations

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
     :file: ../csv/autoruns.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1
