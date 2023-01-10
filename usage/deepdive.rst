DeepDive
========

A ``DeepDive`` on memory images or disk space cannot be analyzed
by THOR events alone. You typically need the memory dumps or
restored chunks to evaluate the findings. This typically takes
a lot more time, know-how and effort to complete.

We recommend the analysis of DeepDive module events only in case
other indicators give a sufficient initial suspicion. 

Samples
-------

.. code-block:: none

	Sep 5 17:23:56 server44.local.net/10.16.3.7
	THOR: Alert: MODULE: DeepDive
	MESSAGE: YARA Score Rule Match
	TARGET: C:\WINDOWS\PCHEALTH\ERRORREP\UserDumps\thor.exe.20170904-154909-00.hdmp
	TYPE: file
	NAME: HurricanePanda_C2_Server
	SCORE: 180
	DESCRIPTION: Hurricane Panda C2 Server in file http://goo.gl/Fm00Q8
	OFFSET: 203423744
	MATCHING_STRINGS:
		S1: 203.135.134.243
			IN: 1dns.dubkill.com.in$s2203.135.134.243$s3newss.effers.com$s4
		S2: 202.181.133.237
			IN: upport.proxydns.com$s13202.181.133.237MobileDevicesUsedtoExecu
		S3: 223.29.248.9
			IN: e.authorizeddns.org$s11223.29.248.9$s12googlesupport.proxy
		S4: 61.78.34.179
	...

.. code-block:: none

	Aug 26 22:20:18 server44.local.net/10.10.1.4
	THOR: Alert: MODULE: DeepDive
	MESSAGE: YARA Score Rule Match
	TARGET: C:\Program Files (x86)\Common Files\McAfee\TalkBack\Data\RPCSERV(1).dmp
	TYPE: file
	NAME: WindowsCredentialEditor
	SCORE: 140
	DESCRIPTION: Windows Credential Editor
	OFFSET: 203423744
	MATCHING_STRINGS:
		S1: Windows Credentials Editor
			IN: %.2X%.2XttcaWindows Credentials Editor-- by Hernan Ochoa (herna
	...

Typical False Positives
-----------------------

- Antivirus signatures in pagefile.sys or in disk surface scans
- Findings in ``\McAfee\TalkBack\Data\RPCSERV``
- THOR process dump files