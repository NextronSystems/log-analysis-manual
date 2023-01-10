DNSCache
========

The ``DNSCache`` module evaluates the entries of the local DNS cache.
It compares the entries with known C2 servers and reports suspicious
entries based on some regular expression checks.  

Samples
-------

.. code-block:: none

	Aug 19 11:27:08 system444.local.net/172.27.2.7
        THOR: Alert: MODULE: DNSCache
        MESSAGE: Malware Domain found in DNS Cache
        ENTRY: 60.10.1.183.in-addr.arpa
        IP: 10.252.8.5
        SIGNATURE: 60.10.1.
        DESC: Graphedt Group
        SCORE: 100

.. code-block:: none

	Jul 8 11:30:56 system88.local.net/10.10.9.15
        THOR: Warning: MODULE: DNSCache
        MESSAGE: Entry with dangerous TLD found
        TLD: biz
        ENTRY: altftp.compsys.biz
        IP: 10.11.11.40
        SCORE: 75

Typical False Positives
-----------------------

- Legitimate company domains registered with a black-listed Top Level Domain (TLD) (e.g. ``vpnaccess.companybranch.info``)
- False positives caused by ``in-add.arpa`` reversed strings that match on black-listed IP addresses
- Too short domain names from 3rd party IOC sources (e.g. ``ipv6.com`` matching on ``benign-site-ipv6.com``)

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
     :file: ../csv/dns.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1