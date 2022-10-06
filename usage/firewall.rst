Firewall
========

The **Firewall** module evaluates all local Windows firewall rules and tries to detect suspicious entries by using white- and blacklists.

Samples
-------

.. code::

	Aug 26 17:51:25 server23.local.net/10.19.2.17 THOR: Warning: MODULE: Firewall MESSAGE: Zeus Local Port defined in Firewall rule SIGNATURE: ZEUS RULE_NAME: Appsense_Input PORT: 7771 SCORE: 75

.. code::

	Jul 29 11:19:48 serverx-print/10.255.80.56 THOR: Warning: MODULE: Firewall MESSAGE: Suspicious Trojan/Backdoor Local Port defined in Firewal rule SIGNATURE: Strange Value RULE_NAME: XXXCloudProxy.exe PORT: 8080 SCORE: 75

Typical False Positives
-----------------------

* Legitimate rules for non-white-listed programs
* Legitimate rules on suspicious ports (e.g. ``WinSSHd`` on port ``60022/tcp``, ``Apache`` on port ``4443/tcp``) 

Attribute Evaluation
--------------------

.. csv-table::
  :file: ../csv/firewall.csv
  :widths: 20, 50, 10, 10, 10
  :delim: ;
  :header-rows: 1