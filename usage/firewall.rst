Firewall
========

The ``Firewall`` module evaluates all local Windows firewall rules
and tries to detect suspicious entries by using white- and blacklists.

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
  :file: ../csv/firewall.csv
  :widths: 20, 50, 10, 10, 10
  :delim: ;
  :header-rows: 1