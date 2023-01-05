General Recommendations
=======================

This chapter contains general approaches that apply to all findings regardless
of the module that reported it. For a deeper understanding of our products (e.g.
ASGARD Management Center or Analysis Cockpit), we recommend our online Training
Platform. Please contact us for more information.

High Quantity Reduces Relevance
-------------------------------

In contrast to firewall log analysis, the high number of a particular event
doesn't increase, but rather decrease the relevance of that event. In a
nutshell, if a suspicious file has been detected on a high number of endpoints
within a given network, it is most likely a false positive. Experience showed
that the most relevant findings were reported from 1-5 and sometimes up to 30
endpoints, but suspicious elements reported from 100 endpoints and higher are
most likely false positives, if no strong indicators suggest the opposite.

Analysis by Module or Score
---------------------------

Our analysts prefer two types of approaches that are often combined to
analyze big amounts of log data.

First, we recommend using our Analysis Cockpit or the free Splunk App / Add-on
to sort the log data by score (descending).

This way, analysts are able to see top scoring elements that are often the most
urgent ones. It is recommended to process the top scoring events top down to a
score of 80 and then switch over to an analysis by module. After selecting a
certain module, we recommend selecting the columns (fields) with the most
characteristic features. (e.g. ``FileScan`` module > selected fields **FILE**, **MAIN_REASON**)

    1) Sort by score and analyze events top down to a score of 80
    2) Analyze events by module and process the remaining events with an appropriate set of columns

Filter Clear the View
---------------------

It is crucial to provide a quick and easy way to filter events based on keywords,
especially when analyzing events of hundreds or thousands of endpoints. Log analysis
or SIEM systems that do not offer easy and fast ways to filter information from a
view, make it substantially more difficult to process large amounts of log data.

Typically, false positives are found in great quantities. By providing tools and
log management solutions that allow easy filtering, the time to complete the analysis
of large amounts of log data can be reduced from days to a few hours.

Attribute Evaluation
--------------------

Many evaluation steps that can be automated have already been implemented in the
scanners. This document aims at giving an analyst the best possible support to
complete the remaining evaluations.

There is no easy step by step guide to analyze the logs of our forensic scanners.
The tables named "Attribute Evaluation", which are part of the following chapters,
just support this evaluation process. They do not represent all necessary steps to
complete an analysis.
