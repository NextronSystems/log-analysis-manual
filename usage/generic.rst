Generic Checks
==============

File Path Checks
----------------

The checks listed in the following table apply to any file path string in many different modules.

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
     :file: ../csv/generic-path.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1

Hash Checks
-----------

We recommend using Virustotal for the analysis of Hash values.

- `www.virustotal.com <https://www.virustotal.com/>`_

The checks listed in the following table apply to any hash value reported in many different modules.

.. csv-table::
     :file: ../csv/generic-hash.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1