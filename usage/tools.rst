Tools for Event Analysis
========================

This list of tools will help you with your event analysis.

VirusTotal
----------

| Used for: File Hashes, Domains, IPs, File Names
| `www.virustotal.com <https://www.virustotal.com/gui/>`_

| Also search for IPs and Domain Names – Examples:
| :samp:`https://www.virustotal.com/en/domain/DOMAIN/information/`
| :samp:`https://www.virustotal.com/en/ip-address/58.158.177.102/information/`

| File Name Search – via Google Search:
| ``inurl:virustotal.com filename``

PEStudio
--------

| Windows tool that helps in the initial and static assessment of a file Sample (if available)
| `www.winitor.com <https://www.winitor.com/>`_


APT Custom Search
-----------------

| Custom Search Engine for APT related Sites
| `cse.google.com <https://cse.google.com/cse?cx=003248445720253387346:turlh5vi4xc>`_

Hybrid Analysis
---------------

| Used for: Samples Upload, search for methods and keywords
| `www.hybrid-analysis.com <https://www.hybrid-analysis.com/>`_

any.run
-------

| Used for Sample Upload and more
| `any.run <https://any.run/>`_

Automatic Hash Checks
---------------------


You can use the Python script ``munin.py`` to batch process lists of Hash values or even complete THOR log files as the script automatically extracts the relevant values from each line. 
The best option is to use the ``*.csv`` files produced after a THOR run and use them as input for the script. 

.. code-block:: console

	user@unix~:$ cat *.csv >> all-hashes.csv
	user@unix~:$ python munin.py –i config.ini –f all-hashes.csv 

`github.com/Neo23x0/munin <https://github.com/Neo23x0/munin>`_
