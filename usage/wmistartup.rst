WMIStartup
==========

The ``WMIStartup`` module uses different WMI queries to retrieve information
on elements that could be used for persistence. It is very likely that findings
by this module also appear in other modules (e.g. ``Autoruns``) in a different
form, because it just uses a different method to look at the same elements.  

Samples
-------

.. code-block:: none

	Aug 23 02:03:12 server55.local.net/10.16.1.44
        THOR: Warning: MODULE: WMIStartup
        MESSAGE: Suspicious startup program WMI Run Key Evaluation
        LOCATION: "C:\Users\user1\AppData\Local\Temp\1\RarSFX1\OlympUpgrade.exe"
        SCORE: 75

.. code-block:: none

	May 20 11:14:52 wks10021/10.1.7.60
        THOR: Warning: MODULE: WMIStartup
        MESSAGE: Suspicious startup program WMI Run Key Evaluation
        LOCATION: "C:\Users\user1\AppData\Local\Akamai\netsession_win.exe"
        SCORE: 75

Typical False Positives
-----------------------

- Legitimate software that uses suspicious startup locations

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
     :file: ../csv/wmistartup.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1