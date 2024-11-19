FAQs
====

THOR Seed
---------

Scan is terminating
^^^^^^^^^^^^^^^^^^^

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

If ``thor64.exe`` is still running when you start THOR seed, you will
get information regarding the current scan.

.. figure:: ../images/thor-seed1.png
   :alt: THOR Seed after timeout

   THOR Seed after timeout

If ``thor64.exe`` is finished, you will get some example commands to
retrieve your files and clean up the reports of the previous scan.

.. figure:: ../images/thor-seed2.png
   :alt: THOR Seed after finished scan

   THOR Seed after finished scan

No Progress Indicator
^^^^^^^^^^^^^^^^^^^^^

The scripting environment doesn't give us the opportunity to report back
any status information before the script terminates. All output written
to STDOUT and STDERR will be returned at the end of the script execution
although it appears earlier.

Unfortunately, it is not possible to return information before the scan
terminates.

Old log files prevent new scan
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Simply run a cleanup before starting a new scan.

.. code-block:: doscon
   
   C:\> run thor-seed.ps1 -parameters "-Cleanup"


THOR alreay running error
^^^^^^^^^^^^^^^^^^^^^^^^^

It is possible that you've interrupted a previous script run with CTRL+C
and got back to the shell. In Live Response, sub processes started by
scripts running from the script library don't get killed on CTRL+C.

It is highly likely that a THOR scan is still running in the background
without you knowing.

Since version 0.18 of THOR Seed, this situation gets handled
automatically. Just run thor-seed.ps1 another time to get information on
the thor64.exe process that still runs in the background. It will show
you information on the log file and print commands that you can use to
download the log file and HTML report once THOR finished its work.

THOR Seed is using multiple Licenses
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

In certain configurations, THOR Seed might use multiple licenses, even though
you only issued a scan on one endpoint. This is due to the fact that Defender
for Endpoint might be configured to execute certain files upon detection in
a sandbox. The problem with this is that the sandbox is actually issuing
a license from our portal, which can't be reused by the customer. To circumvent
this, you have a few options:

- Define Exclusions for the ``thor-seed.ps1`` script (When adding exclusions,
  make sure you're excluding the script from both **cloud protection** and **behavioral analysis (sandbox)** .)

- Sign your version of the ``thor-seed.ps1`` script with a code signing certificate

- Make sure your on premise proxy does not use sandboxing, or set an exclusion
