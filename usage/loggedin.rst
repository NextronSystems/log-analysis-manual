LoggedIn
========

The **LoggedIn** module analyses all currently logged in users and analyses their names.

Samples
-------

.. code::

	Aug 26 12:28:07 server44.local.net/10.7.1.100 THOR: Warning: MODULE: LoggedIn MESSAGE: Suspicious logged in user name KEYWORD: ^[0-9a-z]{1,3}$ USER: abc SCORE: 75

Typical False Positives
-----------------------

* Legitimate user account with three or less characters

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
     :file: ../csv/loggedin.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1