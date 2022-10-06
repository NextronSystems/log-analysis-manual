Rescontrol
==========

The **Rescontrol** (Resource Control) module generates "Warning" level messages in cases a resource limit has been reached. In most of the cases, this is caused by very low free main memory levels or false positives that generated many SYSLOG messages.
Resource control is active by default and can be deactivated with (``--norescontrol``).

| Resource control
| 	* Stops the THOR scan if the available free main memory drops below 50MB
|    * Switches to ``reduced syslog mode`` (Warnings and Alerts only) if more than 5MB of data has been sent via Syslog 

Samples
-------

.. code::

	Aug 2 14:37:48 server44/192.168.2.4 THOR: Warning: MODULE: Rescontrol MESSAGE: Stopping THOR scan in order to avoid a memory outage (use --norescontrol to avoid this) SCORE: 75

.. code::

	Aug 2 14:37:48 server44/192.168.2.4 THOR: Warning: MODULE: Rescontrol MESSAGE: Logged more than 5000000 bytes via SYSLOG. This seems odd. Resource control activates 'reduced syslog' mode. SCORE: 75