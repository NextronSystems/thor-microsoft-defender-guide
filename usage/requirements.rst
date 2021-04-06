.. role:: raw-html-m2r(raw)
   :format: html

Requirements
============

Supported Operating Systems
---------------------------

The operating systems are limited to the set that supports the Microsoft
Defender ATP “Live Response” feature. As of the date of this guide it is
limited to Windows 10 workstations and Windows 2019 server systems.

**Windows 10**

* Version 1909 or later
* Version 1903 with KB4515384
* Version 1809 (RS 5) with KB4537818
* Version 1803 (RS 4) with KB4537795
* Version 1709 (RS 3) with KB4537816

**Windows Server 2019 - Only applicable for Public preview**

* Version 1903 or (with KB4515384) later
* Version 1809 (with KB4537818)

For a current version of the list of supported operating systems, check
the following page:

https://docs.microsoft.com/en-us/windows/security/threat-protection/microsoft-defender-atp/live-response

Enable „Live Response“ Feature
------------------------------

You need to enable the live response capability in the “Advanced
Features” settings page for Workstations and Servers.

https://docs.microsoft.com/en-us/windows/security/threat-protection/microsoft-defender-atp/advanced-features

Hardware Requirements
---------------------

The hardware requirements reflect the scan settings of a default scan.

+---------------------------------+-----------------------+
| Minimum                         | Recommended           |
+=================================+=======================+
| 1 CPU Cores                     | 2 CPU cores or more   |
|                                 |                       |
| 1 GB of RAM                     | 8 GB of RAM or more   |
|                                 |                       |
| 100MB of temporary disk space   |                       |
+---------------------------------+-----------------------+

Table 1 - Hardware Requirements

Note: THOR uses between 160 and 300 MB of main memory during the
investigation, but there are conditions in which the memory usage can
exceed this range for a short time. On very weak end systems, enable
“soft” mode in THOR Seeds config section.

Network Connections
-------------------

On Investigated Workstation
^^^^^^^^^^^^^^^^^^^^^^^^^^^

cloud.nextron-systems.com 443/tcp

(note: this FQDN resolves to multiple IP addresses)

Web Proxies
^^^^^^^^^^^

Web proxies are supported albeit not fully tested. THOR Seed, the script
that retrieves a license and the temporary THOR scanner package is proxy
aware and should use the local proxy configuration.
