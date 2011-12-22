==========================
ZenPacks.ZenSystems.ApcAts
==========================


Description
===========

Provides support for APC Automatic Transfer Switch (ATS) devices with component and performance information for power inputs.

This ZenPack is Zenoss 3 compliant.

Components
==========

The ZenPack has the following new Device Class

    * /Devices/Power/ApcAtsDevice :

    * Components are:
        * ApcAtsInput  which has details for:
            * Input name, type, frequency, voltage and currently selected source

    * Modeler plugins are:
        * ApcAtsDeviceMap 
            * Gathers Hardware and Software manufacturer and product
            * Serial number
            * Status of both sources
        * ApcAtsInputMap 
            * Gathers the selected status source
            * For each input, gathers:
                * Input name, type, frequency and voltage

    * Device template AtsPowerOutput provides device-level performance information: 
        * Data Sources 
            * Input frequency for both sources
            * Output frequency 
        * Thresholds 
            * No thresholds are provided
        * Graph Definitions 
            * Input frequency for both sources
            * Output frequency 

    * Component template ApcAtsInput provides specific input performance information: 
        * Data Sources 
            * Input voltage
            * Output voltage and current 
        * Thresholds 
            * No thresholds are provided
        * Graph Definitions 
            * Input voltage
            * Output voltage and current 

    * A separate APC ATS Information menu delivers tabular and graphical information for the overall device

 

Requirements & Dependencies
===========================

    * Zenoss Versions Supported: 3.0
    * External Dependencies: The APC ATS MIB needs to be available on target devices
    * ZenPack Dependencies:
    * Installation Notes: zenhub and zopectl restart after installing this ZenPack.
    * Configuration: 

Download
========
Download the appropriate package for your Zenoss version from the list
below.

* Zenoss 3.0+ `Latest Package for Python 2.6`_

Installation
============
Normal Installation (packaged egg)
----------------------------------
Copy the downloaded .egg to your Zenoss server and run the following commands as the zenoss
user::

   zenpack --install <package.egg>
   zenhub restart
   zopectl restart

Developer Installation (link mode)
----------------------------------
If you wish to further develop and possibly contribute back to this 
ZenPack you should clone the git repository, then install the ZenPack in
developer mode::

   zenpack --link --install <package>
   zenhub restart
   zopectl restart

Configuration
=============

This ZenPack was tested with Zenoss 3.1 against APC AP7723 01devices.

Change History
==============
* 1.0
   * Initial Release
* 1.1
   * Some updates for extra debug
* 1.2
   * Transferred to new github methods

Screenshots
===========
|ApcAtsInformation|
|ApcAtsInput|


.. External References Below. Nothing Below This Line Should Be Rendered

.. _Latest Package for Python 2.6: https://github.com/jcurry/ZenPacks.ZenSystems.ApcAts/blob/master/dist/ZenPacks.ZenSystems.ApcAts-1.2-py2.6.egg?raw=true

.. |ApcAtsInformation| image:: http://github.com/jcurry/ZenPacks.ZenSystems.ApcAts/raw/master/screenshots/ApcAtsInformation.jpg
.. |ApcAtsInput| image:: http://github.com/jcurry/ZenPacks.ZenSystems.ApcAts/raw/master/screenshots/ApcAtsInput.jpg

                                                                        

