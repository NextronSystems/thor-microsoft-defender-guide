THOR Cloud
==========

This section focuses on our online platform ``THOR Cloud``.

THOR Cloud eliminates the need for on-premise systems for
licensing and scanner package downloads. With THOR Cloud,
all you need is a small yet powerful tool known as the THOR
Cloud launcher. Simply bring it to your endpoint or allow
end users to download and execute it themselves.

Download THOR Cloud Launcher Script
-----------------------------------

Once you logged into your THOR Cloud account, create a new Campaign
or use an existing one. In the Campaign details, download the Launcher
in the top right corner. You need to download the Script for your Operating
System, as the Live Response feature only allows the execution of scripts.

.. figure:: ../images/thor-cloud-launcher-download.png
   :alt: Download the THOR Cloud Launcher Script

   Download the THOR Cloud Launcher Script

Start a Live Response Session
-----------------------------

You find different locations in Microsoft Defender Security Center that
allow you to initiate a Live Response session.

.. figure:: ../images/initiate-live-response-session.png
   :alt: Initiate Live Response Session

   Initiate Live Response Session

Upload THOR Cloud Launcher
--------------------------

Use the button in the upper right corner of the window to upload
the THOR Cloud Launcher script into the Live Response script library.

.. figure:: ../images/live-response-upload-script.png
   :alt: Upload Button

   Upload Button

Make sure to check "Overwrite file" to replace an older version of THOR
Seed in your library if needed. Make sure you are using the correct script
for your target OS.

.. figure:: ../images/upload-thor-cloud-launcher.png
   :alt: Upload THOR Seed

   Upload THOR Seed

Run THOR Cloud Launcher
-----------------------

After uploading THOR Seed to the Live Response script library, you can
start the script with the "run" command.

.. figure:: ../images/run_thor-launcher1.png
   :alt: Run thor-launcher.sh in Live Response session

   Run thor-seed.sh in Live Response session on Linux

.. figure:: ../images/run_thor-launcher2.png
   :alt: Run thor-launcher.ps1 in Live Response session on Windows

   Run thor-seed.ps1 in Live Response session on Windows

You can see the status of the running scan in your Campaign View:

.. figure:: ../images/thor_cloud-running.png
   :alt: Running THOR via Live Response on Linux

   Running THOR via Live Response on Linux


You can close the Live Response Session if you want to, since the THOR
process will continue to run in the background.

You can reuse the Thor-Launcher scripts for other systems, as the only
unique part is the Campaign ID. If you want to scan hosts within another campaign,
make sure to use the script from the other campaign.