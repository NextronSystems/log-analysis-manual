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

.. csv-table::
     :file: ../csv/loggedin.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1