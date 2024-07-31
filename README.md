# X-RTC
A supplemental Real Time Clock for the Original Xbox 

The Original Xbox does not keep time when unplugged for an extended period of time. While some homebew apps have NTP functionality built in, not everyone plugs the console into their home network every time they play. 

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

Copy the X-RTC.xbe into your console's App directory. There you can set the time for the X-RTC. 

The next release of PrometheOS will have the ability to set the time on X-RTC.

Once the time is set and Cerbios is configured to look for the RTC chip. The time on the console will set automatically on boot.


# Credits & Thanks
1.6 LPC rebuild portion by Kekule. -> https://github.com/Kekule-OXC/OXC_LPCorrectr

Team Resurgent for the idea, PrometheOS, and the XBE.

Cerbios team for including functionality into their BIOS.
