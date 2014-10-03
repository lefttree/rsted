.. web_documentation documentation master file, created by
   sphinx-quickstart on Wed Jul  9 12:04:05 2014.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.




IO Module's documentation!
=============================================
:download:`IO Module User Mannual<.build/latex/iom_documentation.pdf>`


Quick Start
====================

All settings here are default settings.

Wifi
----------------------

        Connect Wifi antenna to IO module::

                Wifi Security Mode -- Secure
                Wifi Antenna -- External
                Wifi Channel -- 5Ghz, 40
                Wifi Standard -- 80211a
                Wifi AP Mode -- NAT
                wifi id -- <your wifi id>
                wifi password -- <your wifi password>
                AP IP -- 172.30.254.1 
                AP Netmask -- 255.255.0.0
                AP Gateway -- 172.30.254.1
                leasetime -- 600
                start ip -- 172.30.254.100
                stop ip -- 172.30.254.200

        Click "Apply"/"Save and Apply"

        Use your wifi supported device to connect to this wifi

PTT
---------------------

        Connect headset to IO module::

                Channel 1 -- 239.0.0.190
                Microphone volume -- 70
                Speaker volume -- 85

        | Enable Push to Talk and click "Apply"/"Save and Apply"
        | Make sure Radios are connected(LED light is green)
        | Now you can user push to talk function normally

Video Encoder
--------------------

        | Connect Camera to IO module

        Default settings are as following::

                Video Format -- NTSC
                Codec Combination -- H264
                H264 Profile -- Main Profile
                Resolution(Primary and Secondary) -- 4CIF
                Frame rate(Primary and Secondary) -- 25fps
                Bitrate -- 1Mbps
                Quality factor of MJPEG -- 80
                Brightness/Contrast/Saturation -- 128

        Now you can watch the video in VLC player through the H.264 link

GPS
--------------------


        | Select antenna and enable GPS
        | On **radio's** webinterface, point your GPS server ip to IO Module's ip
        | After GPS is locked, you could see updated GPS locations of radios on Mapoverlay page

Basic
====================
.. figure:: .static/Basic.png
   :align: center
   :width: 90%

- Virtual IP: Enable or Disable the Secondary IP address for the radio.

- Virtual IP Address: Secondary IP address for the radio.

.. note::
        .. container::
           :name: virtual-ip-help

           The user may set this to be on the user’s IP network, e.g., 192.168.2.10. Once this secondary IP address is set, the user may access the radio web page using either the native IP address or the secondary IP address. Please note that the secondary IP address should NOT be on the 172.20.xx.xx subnet. 

.. container::
   :name: virtual-netmask-help

   - Virtual Netmask: Netmask for the Secondary IP address, e.g. 255.255.255.0. 

.. container::
   :name: virtual-gateway-help

   - Virtual Gateway: Gateway for local network to allow radio to connect to the internet



Wifi
=================

.. figure:: .static/Wifi.png
   :align: center
   :width: 90%

- Wifi Mode: AP Mode

.. container::
   :name: 'wifi-security-help'

   - Wifi Security Mode: Select open/secure mode for wifi   
        * Secure: Wifi with encryption(WP2-PSK)
        * Open: No encryption

.. container::
   :name: wifi-essid-help

   - Wifi Essid: Set wifi displayed name

.. container::
   :name: wifi-key-help

   - Wifi Key: Set wifi password if security mode is selected

.. container::
   :name: wifi-antenna-help

   - Wifi Antenna
        * External: Use external antenna for enclosed IO Module
        * Internal: Use internal antenna for openstack IO Module

.. container::
   :name: wifi-channel-help

   - Wifi Channel: Select wifi frequency and channel
        * 5Ghz: wider bandwidth and less interference
        * 2.4Ghz: wider range

.. container::
   :name: wifi-standard-help

   - Wifi Standard
        * 5Ghz: 80211a
        * 2.4Ghz: 80211b, 80211g

.. container::
   :name: wifi-ap-help
        
   - Wifi AP: network configuration for your wifi interface
   - Default Values:
        * AP IP: 172.30.254.1
        * AP Netmask: 255.255.0.0
        * AP Gateway: 172.30.254.1
        

.. container::
   :name: dhcp-server-help

   - Wifi DHCP Server: 
        * Enable/Disable: Enable/Disable DHCP server on IO Module's wifi AP
        * Default DHCP range: 172.30.254.100 - 172.30.254.200; lease time: 600  

- Apply: Applies the new values but does not save them to flash
- Save and Apply: Save the new values to flash and apply
- Wifi Status: Show current connected devices

PTT
=================

.. figure:: .static/PTT.png
   :align: center
   :width: 90%

This page configure settings for Push to Talk function(Half duplex communication via Ethernet using push button)

- Push to Talk: Enable/Disable Push to Talk function

.. container::
   :name: multicast-channel-help

   - Multicast Channels: configure multicast groups ip
        * Channel 1:(default is 239.0.0.190)
        * Multicast IP must be in the range of 224.0.0.0 to 239.255.255.255

.. container::
   :name: volume-control-help

   - Volume Control: configure Push to Talk headset volumes(0-100)
        * Microphone: Configure headset input volume (default 70)
        * Speaker: Configure headset Output volume (default 85)

- Apply: Applies the new values but does not save them to flash
- Save and Apply: Save the new values to flash and apply

Video Encoder
=================

* Video

.. figure:: .static/VideoEncoder.png
   :align: center
   :width: 90%

This page configure settings for video encoder function

.. container::
   :name: video-format-help
   
   - Video Format: Support NTSC/PAL video inputs

.. container::
   :name: codec-combination-help
   
   - Codec Combination: Support video output in the following 4 codec combinations:
        * Single H264
        * SIngle MPEG4
        * H264(Primary stream) + MJPEG(Secondary stream)
        * MPEG4(Primary stream) + MJPEG(Secondary stream)
   
   The last 2 codec comb allow 2 different format streaming at the same time 
   
   .. note::
        (latest VLC media player on ubuntu does not support MPEG4)

.. container::
   :name: h264-help
   
   - H264 Profila: H264 standards
        * Base Profile: Primarily for lower-cost applications with limited computing resources
        * Main Profile: Intended as the mainstream consumer profile for broadcast and storage applications
        * High Profile: The primary profile for broadcast and disc storage applications, particularly for high-definition television applications

- Resolution-Primary
        * VGA: 640*480
        * 4CIF: 704*576

.. container::
   :name: resolution-help
   
    - Resolution-Secondary
        * VGA: 640*480
        * 4CIF: 704*576
        * CIF: 352*288

- Frame rate: Set frame rate for primary and secondary stream
- Bitrate-Primary: Set bitrate for primary stream

.. container::
   :name: video-control-help
   
   - Video control: 0 means lowest, 255 means highest
        * Brightness (0-255)
        * Contrast (0-255)
        * Saturation (0-255)

.. container::
   :name: quality-factor-help
 
   - MJPEG Quality Factor - Secondary stream: 2-97 (2 means lowest quality, 97 means highest quality)

- Apply: Applies the new values but does not save them to flash
- Save and Apply: Save the new values to flash and apply

.. container::
   :name: video-streaming-address-help

   - RTSP Links: Video streaming links that you can view in VLC player.(VLC Player -> Open Network Stream)

GPS
=================
.. figure:: .static/GPS.png
   :align: center
   :width: 90%

This Page Configure GPS antenna and disable/enable GPS function

- GPS: Enable/Disable GPS
- Antenna: Select external/internal GPS antenna
- Apply: Applies the new values but does not save them to flash
- Save and Apply: Save the new values to flash and apply

License
======================

.. figure:: .static/License.png
   :align: center
   :width: 90%

This page is for Uploading signed license from Silvus. Your IO Module can have specific functions only with signed licenses.

- License File: Show all license files on your IO Module
- Capability: Show all capabilities for selected license file
- Description: Description for selected capability
- License Upload: Upload Signed License

Build
======================

.. figure:: .static/Build.png
   :align: center
   :width: 90%

This page shows specific information about your IO Module, which can help you determine your IO Module type and firmware version.

.. container::
   :name: timestamp-help
 
   - Build Timestamp: The date this firmware was built

.. container::
   :name: build-tag-help
 
   - Build Tag: Firmware's version

.. container::
   :name: board-type-help
 
   - Board Type: Board type, revision and option code of IO module

- Kernel Image: Kernel Image infomation
- U-boot Version: U-boot version information

- Firmware Upgrade: Upgrade IO Module's firmware
- Factory Reset: Reset IO Module to Factory settings 

