UserAccounts
============

The **UserAccounts** module analyses the local user database. It checks for suspicious user names, suspicious members in the ``Administrators`` group, activated guest accounts, user accounts created on Sundays and reports recently logged in users.
It applies the ``hot time frame`` parameter (``-f``) if given and reports suspicious account activity on a given set of dates. 

Samples
-------

.. code::

	Jun Oct 25 21:01:51 server44.local.net/10.216.2.186 THOR: Notice: MODULE: UserAccounts MESSAGE: Recently logged in USER: sa_backup FULL_NAME: sa_backup PRIV: 2 LAST_LOGON: 24/10/2017 16:08:22 BADPWCOUNT: 0 SERVER: \* NUM_LOGONS: 9 PASS_AGE: 105.00 days ACTIVE: True NO_EXPIRE: True LOCKED: False

.. code::

	Oct 23 15:27:12 server44.local.net/10.216.2.186 THOR: Warning: MODULE: UserAccounts MESSAGE: Last password change of user happened in relevant time frame USER: Administrator FULL_NAME: PRIV: 2 LAST_LOGON: 23/10/2017 08:03:15 BADPWCOUNT: 0 SERVER: \* NUM_LOGONS: 14 PASS_AGE: 3.00 days ACTIVE: True NO_EXPIRE: True LOCKED: False SCORE: 75

.. code::

	Aug 28 12:27:29 PROMETHEUS/10.0.2.4 THOR: Warning: MODULE: UserAccounts MESSAGE: Suspicious user name in Local Administrators group NAME: Guest SCORE: 75

.. code::

	Sep 8 12:32:39 PROMETHEUS/10.0.2.4 THOR: Warning: MODULE: UserAccounts MESSAGE: Suspicious user name KEYWORD: (^[0-9a-z]{1,3}$|^test$|^sa$|hack|exploit|nopw|temp) USER: neo FULL_NAME: PRIV: 2 LAST_LOGON: 30/08/2017 12:43:41 BADPWCOUNT: 0 SERVER: \* NUM_LOGONS: 352 PASS_AGE: 930.00 days ACTIVE: True NO_EXPIRE: True LOCKED: False SCORE: 75

Typical False Positives
-----------------------

* Organizations that use short user names (e.g. ``ska``, ``mba``, ``jmi``)
* User creation on a Sunday creates warning messages in regions in which a Sunday is a normal working day (e.g. Israel)

Attribute Evaluation
--------------------

.. csv-table::
     :file: ../csv/useraccounts.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1