================
Updating IoT box
================

Due to the complexity of the :abbr:`IoT (Internet of Things)` box, the term 'updating' can mean
several different things. The actual drivers can be updated, the core code on the :abbr:`IoT
(Internet of Things)` box can be updated and lastly a new image can be flashed. This document will
explore the various ways to update the :abbr:`IoT (Internet of Things)` box to ensure smooth
operation of :abbr:`IoT (Internet of Things)` box processes and devices.

Handlers (drivers) update
=========================

There may be some instances where the drivers or interfaces need to be updated for individual
devices. The IoT handlers (drivers and interfaces) code can be modified by syncing them with the
corresponding driver's code. This can be helpful in instances where :abbr:`IoT (Internet of Things)`
devices (e.g. scales, measurement tools, etc.) are not working properly with the :abbr:`IoT
(Internet of Things)` box.

For both the Windows :abbr:`IoT (Internet of Things)` (Odoo 16 and higher) and physical :abbr:`IoT
(Internet of Things)` box, this process can be performed manually from the :abbr:`IoT (Internet of
Things)` box homepage. Go to the :abbr:`IoT (Internet of Things)` box homepage by navigating to
:menuselection:`IoT app --> IoT Boxes` and clicking on the :guilabel:`IP address` of the :abbr:`IoT
(Internet of Things)` box.

Next, click :guilabel:`Handlers list` and then select :guilabel:`Load Handlers` at the bottom of the
page.

.. image:: flash_sdcard/load-handlers.png
   :align: center
   :alt: Handlers list on an IoT box with the load handlers button highlighted.

.. note::
   The handlers update is also performed automatically each time the :abbr:`IoT (Internet of
   Things)` box is restarted. The only exception to this process is if the :guilabel:`Automatic
   drivers update` is unchecked in the form view of the :abbr:`IoT (Internet of Things)` box on the
   Odoo server. This setting can be reached by going to :menuselection:`IoT App --> Select the IoT
   box --> Automatic drivers update`.

Upgrade from the IoT box home page
==================================

In the background, the :abbr:`IoT (Internet of Things)` box uses a version of Odoo code to run and
connect to the Odoo database. This code may need to be updated in order for the :abbr:`IoT (Internet
of Things)` box to operate effectively. This operation should be completed on a routine basis, to
ensure up-to-date :abbr:`IoT (Internet of Things)` processes and device drivers.

Go to the :abbr:`IoT (Internet of Things)` box homepage by navigating to :menuselection:`IoT app -->
IoT Boxes` and clicking on the :guilabel:`IP address` of the :abbr:`IoT (Internet of Things)` box.
Then click on :guilabel:`Update` (next to the version number).

If a new version of the :abbr:`IoT (Internet of Things)` Box image is available, an
:guilabel:`Upgrade to _xx.xx_` button will appear at the bottom of the page. Click this button to
upgrade the unit and the :abbr:`IoT (Internet of Things)` box will then flash itself to the new
version. All of the previous configurations will be saved.

.. note::
   This process can take more than 30 minutes. Do not turn off or unplug the :abbr:`IoT (Internet of
   Things)` box as it would leave it in an inconsistent state. This means that the :abbr:`IoT
   (Internet of Things)` box will need to be re-flashed with a new image. See
   :ref:`flash_sdcard/etcher`.

.. image:: flash_sdcard/flash-upgrade.png
   :align: center
   :alt: IoT box software upgrade in the IoT Box Home Page.

.. _flash_sdcard/etcher:

Flashing the SD card
====================

In some circumstances, the :abbr:`IoT (Internet of Things)` box's micro SD Card may need to be
re-flashed with Etcher software to benefit from Odoo's latest :abbr:`IoT (Internet of Things)` image
update. This means that the Odoo :abbr:`IoT (Internet of Things)` box software may need to be
updated in instances of a new :abbr:`IoT (Internet of Things)` box, or when a handlers update and
update from the :abbr:`IoT (Internet of Things)` box home page doesn't fix issues.

.. note::
   A computer with a micro SD card reader/adapter is required in order to re-flash the micro SD
   card.

Navigate to Balena's website and download `Etcher <https://www.balena.io/>`_. It's a free and
open-source utility used for burning image files onto drives. Click to `download
<https://www.balena.io/etcher#download-etcher>`_. Install and launch the program on the computer.

Then download the version-specific :abbr:`IoT (Internet of Things)` image from `nightly
<http://nightly.odoo.com/master/iotbox/>`_.

The following are image versions on the `nightly <http://nightly.odoo.com/master/iotbox/>`_ website
with their corresponding Odoo database version:

- Odoo Master --> iotbox-latest.zip
- Odoo V17 --> iotboxv23_11.zip
- Odoo V16 --> iotboxv23_09.zip
- Odoo V15 --> iotboxv21_10.zip
- Odoo V14 --> iotboxv21_04.zip
- Odoo V13 --> iotboxv20_10.zip

The images should be downloaded and extracted to a convenient file location.

After this step is complete, insert the :abbr:`IoT (Internet of Things)` box's micro SD card into
the computer or reader. Open *Etcher* and select :guilabel:`Flash from file`, then find and select
the image just downloaded and extracted. Next, select the drive the image should be burned to.
Lastly, click on :guilabel:`Flash` and wait for the process to finish.

.. image:: flash_sdcard/etcher-app.png
   :align: center
   :alt: Balena's Etcher software dashboard.

.. note::
   An alternative software for flashing the micro SD card is *Raspberry Pi Imager*. Download the
   *Raspberry Pi* software `here <https://www.raspberrypi.com/software/>`_.
