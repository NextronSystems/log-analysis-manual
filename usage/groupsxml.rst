GroupsXML
=========

The ``GroupsXML`` module is a module that reports on critical security
issues related to decryptable passwords in group policy files, that
are readable for anyone within a Windows Domain. 

References
----------

`Active Directory Security <https://adsecurity.org/?p=2288>`_
`Network Intelligence <http://niiconsulting.com/checkmate/2016/02/hunting-passwords-in-sysvol/>`_

Samples
-------

.. code::

	Aug 28 11:07:24 System32.local.net/10.2.0.7 THOR: Warning: MODULE: GroupsXML MESSAGE: Found decryptable password in Groups.xml FILE: D:\SYSVOL_DFSR\sysvol\win55.local.net\Policies\{FFABF4BC-8A98-4B3F-AD7D-D65A5F4C26C1}\Machine\Preferences\Groups\Groups.xml USER: Administrator (built-in) PASSWORD: win***removed*** SCORE: 75

Typical False Positives
-----------------------

* Old ``groups.xml`` files in backup locations that are not active anymore

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
     :file: ../csv/groupsxml.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1