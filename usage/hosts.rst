Hosts
=========

The **Hosts** module evaluates the entries in the local hosts file.

References
----------

`blog.malwarebytes.com <https://blog.malwarebytes.com/cybercrime/2016/09/hosts-file-hijacks/>`_

Samples
-------

.. code::

	Aug 26 11:46:14 server555.local.net/10.7.1.14 THOR: Warning: MODULE: Hosts MESSAGE: New hosts entry - not found during the last run ENTRY: master.comp-a.net IP: 10.7.10.2 SCORE: 75

.. code::

	Jul 29 12:16:18 server99.local.net/10.1.1.55 THOR: Warning: MODULE: Hosts MESSAGE: Suspicious entry found in Hosts file ENTRY: ctldl.windowsupdate.com IP: 127.0.0.1 SCORE: 75

Typical False Positives
-----------------------

* Entries on development systems to simulate future DNS resolution (e.g. ``www.company-intranet.net    10.0.2.28``)
* Some Antivirus tools insert entries into the hosts file to immunize the system (e.g. ``Spybot Search & Destroy``)

Attribute Evaluation
--------------------

.. csv-table::
     :file: ../csv/hosts.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1