HotfixCheck
===========

The **HotFixCheck** module analyses the installed hotfixes on the end system.

Samples
-------

.. code::

	Sep 4 16:33:27 server11.local/192.168.2.2 THOR: Warning: MODULE: HotfixCheck MESSAGE: Outdated System - No hotfixes installed for the last 90 days. Last hotfix DATE: 2015/01/09 SCORE: 75

Typical False Positives
-----------------------

* THOR failed to evaluate the modules on the system and didn't return a single hotfix. In these cases, THOR reports "No Hotfixes installed or no hotfix information available" 