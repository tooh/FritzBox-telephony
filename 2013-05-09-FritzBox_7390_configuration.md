Title: Fritz!Box 7390 configuration
Date: 2013-05-09 12:32
Comments: true
Category: telephony
Tags: telephony, VOIP
Status: 
Summary:

I recently bought a Fritz!Box 7390. Main reason was that I wanted to integrate telephony (POTS) in my daily workflow on my Mac.

In this article I will describe the configuration and add-ons I installed.

<!-- more -->
## Contents

[TOC]

## The Fritz!Box

![Fritz!Box 3790]({static}/images/fritzbox_7390product.jpg)

[The Fritz!Box 7390](http://www.avm.de/en/Produkte/FRITZBox/FRITZ_Box_Fon_WLAN_7390/index.php)

### Options

## Internet access

I have a UPC cable modem 

[CISCO EPC3212](http://192.168.100.1)

[Cisco EPC3212 User manual](http://www.cisco.com/web/consumer/support/userguides2/4021203A.pdf)

![Typical setup]({static}/images/ciscoEPC3212setup.png)

### Using the Internet connection of another router with FRITZ!Box

[Using the Internet connection of another router with FRITZ!Box](http://service.avm.de/support/en/SKB/FRITZ-Box-7390-int/598:Using-the-Internet-connection-of-another-router-with-FRITZ-Box)

## Analog telephony (Cisco EPC3212)

#### Connections for TEL 1 / TEL 2

![TEL 1/TEL 2 connections](/images/EPC3212.png)

#### Fritz!Box connections

![Fritz!Box 3790](/images/fritzbox_7390.jpg)

#### Connection to a cable modem

[Connection to a cable modem](http://service.avm.de/support/en/skb/FRITZ-Box-7390-int/700:Connecting-FRITZ-Box-to-a-cable-modem)

I wanted to use the Fritz!Box as part of my existing network.
I decided not to use the WLAN option of the Fritz!Box, but instead I bought a Fritz! Powerline 520 E set, because I did not have a cabled network connection on the location where the Internet modem was located. In this setup I could connect the Internet modem to the LAN 1/WAN connection of my Fritz!Box.

### DECT telephone device

The Fritz!Box 7390 offers a basestation, upto 6 DECT telephones can be connected. 

Note: For now I do not have any DECT phones connected. 

Update: Some developments here. I bought a DECT Gigaset A420A TRIO. When they are setup I will update my findings.

## VOIP telephony

For OSX there are several softphone apps available:

[Telephone](http://www.tlphn.com/)

[Counterpath X-Lite](http://counterpath.s3.amazonaws.com/downloads/X-Lite_Mac_3520g_70143.dmg)

## Add-ons

### Alfred workflow

I created a simple Alfred 2 workflow that calls the Frizzix dial helper.

Use keyword "Dial" to trigger a little Applescript that contains:

	:::applescript
	on alfred_script(q)
		set TelNumber to q as string
		set Tel to ""
		repeat with each in TelNumber
			if "+1234567890" contains each then set Tel to Tel & each
		end repeat
		tell application "Frizzix"
			dialInstantly Tel
		end tell
	end alfred_script

### Call diversion from script

[Call diversion script](http://www.robbastiaansen.nl/node/51)

### Frizzix Call monitor (MAC)

[Frizzix](http://mac.frizzix.de/en/)

I also installed:

* the Address Book Plugin

* Services plugin

### Fritz!Box browser add-on

[Add-on for Firefox](http://www.avm.de/de/Service/FRITZ_Tools/browser_plugin.html)

Note: it seems that in my setup phone numbers are recognized in webpages, but dialing out does not work.

### dialing scripts

[Dialing from Address book](http://wehavemorefun.de/fritzbox/W%C3%A4hlen_aus_OS_X_Adressbuch)

### POP3 mail checker and alert on Fritz!Box

[POP3-Robot](http://wehavemorefun.de/fritzbox/POP3-Robot)

### fhem

[fhem](http://fhem.de/fritzbox.html)

### Synology Diskstation front-end

[Fritz!Box front-end package](http://spk.q14six.de/)

## References

[1] [POTS](http://http://en.wikipedia.org/wiki/Plain_old_telephone_service)

[2] [AVM](http://www.avm.de)

[3] [AVM Knowledge base](http://http://service.avm.de/support/en/skb/FRITZ-Box-7390-int/page:1)

[4] [Think broadband review](http://http://www.thinkbroadband.com/hardware/reviews/73-fritzbox-7390.html) 

