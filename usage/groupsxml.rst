GroupsXML
=========

The GroupsXML module is a module that reports on critical security issues related to decryptable passwords in group policy files, that are readable for anyone within a Windows Domain. 

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

* Old groups.xml files in backup locations that are not active anymore

Attribute Evaluation
--------------------

.. csv-table::
     :file: ../csv/groupsxml.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1