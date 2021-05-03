FAQs
====

Why does my scan suddenly terminate?
------------------------------------

Live response applies a rather disadvantages timeout for PowerShell
scripts run within a Live Response session, which is 30 minutes by
default. If a scan takes longer to complete, it gets terminated.

We recommend

-  using scan settings that allow the scan to terminate within 30
   minutes

-  increasing the timeout to a higher value in future versions of
   Microsoft Defender ATP

Since version 0.18 of THOR Seed, this situation gets handled
automatically. Just run thor-seed.ps1 another time to get information on
the thor64.exe process that still runs in the background. It will show
you information on the log file and print commands that you can use to
download the log file and HTML report once THOR finished its work.

Why can’t I see a progress indicator? 
--------------------------------------

The scripting environment doesn’t give us the opportunity to report back
any status information before the script terminates. All output written
to STDOUT and STDERR will be returned at the end of the script execution
although it appears earlier.

Unfortunately, it is not possible to return information before the scan
terminates.

I cannot start a new THOR scan due to old log files?
----------------------------------------------------

Simply run a cleanup before starting a new scan.

.. code:: bash
   
   run thor-seed.ps1 -parameters "-Cleanup"


I can’t start a scan and get the error “THOR already running”, why?
-------------------------------------------------------------------

It is possible that you’ve interrupted a previous script run with CTRL+C
and got back to the shell. In Live Response, sub processes started by
scripts running from the script library don’t get killed on CTRL+C.

It is highly likely that a THOR scan is still running in the background
without you knowing.

Since version 0.18 of THOR Seed, this situation gets handled
automatically. Just run thor-seed.ps1 another time to get information on
the thor64.exe process that still runs in the background. It will show
you information on the log file and print commands that you can use to
download the log file and HTML report once THOR finished its work.

Does each scan use up one of my licenses? 
------------------------------------------

Once you generate a license for a system, this license has a certain
lifetime (e.g. 48 hours). You can start as many scans within that
lifetime without using a new license from your quota.

THOR doesn’t stop if the scan takes longer than the license lifetime.

If you start a new scan on a system that has be scanned in the past and
the old license is expired, a new license will be generated and count
against the quota.

Can I use my own IOCs and YARA signatures with THOR Seed? 
----------------------------------------------------------

Not yet but we’ll add an option to the THOR Seed PowerShell script to
download and use a ZIP archive with custom IOCs and YARA signatures from
a user defined location.
