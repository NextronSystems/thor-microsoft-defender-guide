
Requirements
============

Supported Operating Systems
---------------------------

The operating systems are limited to the set that supports the Microsoft
Defender ATP "Live Response" feature.

.. list-table:: 
    :header-rows: 1
    :widths: 30, 70

    * - Operating System
      - Version
    * - **Windows 10 & 11**
      - Version 1909 or later
    * - 
      - Version 1903 with KB4515384
    * - 
      - Version 1809 (RS 5) with with KB4537818
    * - 
      - Version 1803 (RS 4) with KB4537795
    * - 
      - Version 1709 (RS 3) with KB4537816
    * - **macOS**
      - Minimum required version: 101.43.84. Supported for
        Intel-based and ARM-based macOS devices.
    * - **Linux**
      - Minimum required version: 101.45.13
    * - **Windows Server 2012**
      - R2 with KB5005292
    * - **Windows Server 2016**
      - with KB5005292
    * - **Windows Server 2019**
      - Version 1903 or (with KB4515384) later
    * - 
      - Version 1809 (with KB4537818)
    * - **Windows Server 2022**
      - 

For a current version of the list of supported operating systems, check
the following page:

https://docs.microsoft.com/en-us/windows/security/threat-protection/microsoft-defender-atp/live-response

Enable "Live Response" Feature
------------------------------

You need to enable the live response capability in the "Advanced
Features" settings page for Workstations and Servers.

https://docs.microsoft.com/en-us/windows/security/threat-protection/microsoft-defender-atp/advanced-features

Hardware Requirements
---------------------

The hardware requirements reflect the scan settings of a default scan.

.. list-table:: Table 1 - Hardware Requirements
    :header-rows: 1
    :widths: 50, 50

    * - Minimum
      - Recommended
    * - 1 CPU Core
      - 2+ CPU Cores
    * - 1 GB of RAM
      - 8+ GB of RAM
    * - 100 MB of temporary Disk Space
      - 

.. hint:: 
    THOR uses between 160 and 300 MB of main memory during the investigation,
    but there are conditions in which the memory usage can exceed this range
    for a short time. On very weak end systems, enable "soft" mode in THOR
    Seeds config section.

Network Connections
-------------------

For a detailed and up to date list of our update and licensing servers,
please visit https://www.nextron-systems.com/hosts/.

On Investigated Workstation
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::

    * - Remote Host
      - Port
    * - cloud.nextron-systems.com
      - 443/tcp

.. hint:: 
    this FQDN resolves to multiple IP addresses. See https://www.nextron-systems.com/hosts/.

Web Proxies
^^^^^^^^^^^

Web proxies are supported albeit not fully tested. THOR Seed, the script
that retrieves a license and the temporary THOR scanner package is proxy
aware and should use the local proxy configuration.
