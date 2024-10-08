# X-RTC
A supplemental Real Time Clock for the Original Xbox 

The Original Xbox does not keep time when unplugged for an extended period of time. While some homebew apps have NTP functionality built in, not everyone plugs the console into their home network every time they play. 

Designed so the battery is only used when AC power is removed from the console. A CR2032 in theory should last 6-10 years when constantly being used. 
Should work with any modchip and TSOPed consoles. Have not tested with BFM BIOSes. 

SDA\SDL from the console are also brought to a set of solder pads for ease of installation of any other mod that may require them. 

<img src="https://github.com/Andr-Zero/X-RTC/blob/main/Images/10Install.png" width=50% height=50%><img src="https://github.com/Andr-Zero/X-RTC/blob/main/Images/16Install.png" width=38% height=38%>

# Board Specifications
0.8mm thick, castellated holes on all sides.

# 1.0-1.4 Installation
On the bottom of the Xbox motherboard. If you have a pinheader already installed, remove excessive solder from the pins outlined in purple and any that would interfere with the installation of the X-RTC QSB. Install the QSB onto the LPC port as shown above, make sure the QSB is sitting flush against the board. While keeping the QSB aligned, solder the QSB to the LPC port and the ground point outlined in black. Run a short wire from the console's 3.3v standby outlined in red to the 3v3 StdBy pad on the QSB. Lastly wire a 3v battery to the Positive and Negative solder pads on the QSB.

<img src="https://github.com/Andr-Zero/X-RTC/blob/main/Images/1011Board.png" width=49% height=49%><img src="https://github.com/Andr-Zero/X-RTC/blob/main/Images/1214Board.png" width=51% height=51%>

# 1.6 Installation
On the bottom of the Xbox motherboard. Remove any existing LPC rebuild QSB or wires that maybe installed. If a pinheader is already installed, remove solder from the bottom of the pinheader. No need to remove the pinheader, just enough for the X-RTC QSB can sit flush against the board. Solder the various LAD points first, then the ground connections around the QSB, solder the QSB to the LPC port and pinheader last. Make sure the solder is connecting to the QSB, pinheader, and the main board. All the edge points on the QSB need to contact the board. Since the 1.6 consoles have it’s standby voltage on the LPC, no need to run a wire like the early revisions. Last step is wiring a 3v battery to the Positive and Negative solder pads on the QSB. Your install should look like the 1.6 install at the top of this README

# BOM

| Part | Description | Digikey Link |
| --- | --- | --- |
| `0.1 uF` | Generic 0.1uF Ceramic Cap | https://www.digikey.com/short/408q3vwn |
| `DS3231MZ` | I2C Real Time Clock | https://www.digikey.com/short/m05dd78z |
| `XC6206P332MR` | 3.3v Regulator for 1.6 ONLY | https://www.digikey.com/short/bqdqftzn |


# Software
Cerbios 2.4.0 or higher is required to use X-RTC. 

> ; Enables Automatic Time Sync With Optional RTC Hardware Connected to SMBus
> 
> RtcEnable = True

Using a Chip that can use PrometheOS:
Version 1.4.0 or higher is able to set the time, enable RTC in PrometheOS Settings. (Rebooting recommended) 

TSOP or Other:
Download the X-RTC.xbe into your Apps folder, within you can set the time. 

Once the time is set and Cerbios is configured. The time on the console will set automatically on boot.


# License, Credits, & Thanks
The hardware and it's related files is licensed under CERN-OHL-S v2 or later version.
See License.txt, cern_ohl_s_v2.txt, and cern_ohl_s_v2_user_guide.txt for details.

1.6 LPC rebuild portion by Kekule. -> https://github.com/Kekule-OXC/OXC_LPCorrectr

Team Resurgent for the idea, PrometheOS, and the XBE.

Cerbios team for including functionality into their BIOS.
