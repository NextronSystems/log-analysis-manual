WMIStartup
==========

The **WMIStartup** module uses different WMI queries to retrieve information on elements that could be used for persistence. It is very likely that findings by this module also appear in other modules (e.g. **Autoruns**) in a different form, because it just uses a different method to look at the same elements.  

Samples
-------

.. code::

	Aug 23 02:03:12 server55.local.net/10.16.1.44 THOR: Warning: MODULE: WMIStartup MESSAGE: Suspicious startup program WMI Run Key Evaluation LOCATION: C:\Users\user1\AppData\Local\Temp\1\RarSFX1\OlympUpgrade.exe zInstalu true 0 C:\OLYMP\ SCORE: 75

.. code::

	May 20 11:14:52 wks10021/10.1.7.60 THOR: Warning: MODULE: WMIStartup MESSAGE: Suspicious startup program WMI Run Key Evaluation LOCATION: "C:\Users\user1\AppData\Local\Akamai\netsession_win.exe" SCORE: 75

Typical False Positives
-----------------------

* Legitimate software that uses suspicious startup locations

Attribute Evaluation
--------------------

.. csv-table::
     :file: ../csv/wmistartup.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1