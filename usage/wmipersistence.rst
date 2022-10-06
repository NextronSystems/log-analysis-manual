WMIPersistence
==============

It is difficult to detect malicious WMI persistence objects. The detection methods are based on whitelists and a blacklist with keywords from APT reports. The whitelists are extended every time our analysts detect false positives in a customer's environment. The black lists are extended every time an APT report states a certain WMI persistence method with specific event filer or event file name. 

References
----------

`Github <https://github.com/darkquasar/WMI_Persistence>`_

Samples
-------

.. code::

	Aug 26 23:16:41 server44.local.net/10.23.3.1 THOR: Warning: MODULE: WMIPersistence MESSAGE: Suspicious WMI element KEY: Binding 91 FILTERTYPE: HealthDriverEventConsumer EVENTFILTERNAME: HP_TempSensorFailureEvent EVENTCONSUMER: Health Event Consumer EVENTFILTER: select * from HP_TempSensorFailureEvent EVENTCONSUMER: - SCORE: 75

.. code::

	Aug 26 23:16:41 server44.local.net/1.253.103.134 THOR: Warning: MODULE: WMIPersistence MESSAGE: Suspicious WMI element KEY: Binding 93 FILTERTYPE: HealthDriverEventConsumer EVENTFILTERNAME: HP_ASRStateChangeEvent EVENTCONSUMER: Health Event Consumer EVENTFILTER: select * from HP_ASRStateChangeEvent EVENTCONSUMER: - SCORE: 75

Typical False Positives
-----------------------

* Legitimate entries caused by system management software (e.g. HP services)

Attribute Evaluation
--------------------

.. csv-table::
     :file: ../csv/wmipersistence.csv
     :widths: 20, 50, 10, 10, 10
     :delim: ;
     :header-rows: 1