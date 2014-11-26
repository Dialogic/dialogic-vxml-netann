Introduction
------------
This article showcases using the VXML scripting language to record a message and playback the recorded message on Dialogic® PowerMedia™ Extended Media Server (XMS). 


Details
-------
This demo script file was tested on PowerMedia XMS version 2.2.6338 using the Kapanga SIP Softphone as the User Agent (UA). This script can be placed locally on the PowerMedia XMS server location (such as  /var/lib/xms/vxml/www/vxml) or remote on a file server that is accessible to PowerMedia XMS.
 
The SIP Client calling URI to the PowerMedia XMS system should follow this format:
 
(a) If the VXML script is located on the actual PowerMedia XMS system, the SIP URI would look like the following:
 
	dialog@<xms_ipaddess>;voicexml=file:///<script file location>/VoiceMail.vxml
 
(b) If the VXML script is located on a remote file server, the SIP URI would look like the following:
 
	dialog@<xms_ipaddess>;voicexml=http://<remote file server ip_address>/<script file location>/VoiceMail.vxml

 
VXML Script Overview
-------------------- 
This script demo currently has the following functionality

-Plays an introduction menu of choices.
	-If NO INPUT - play noinput.wav and go to introduction message
	-If NO MATCH - play nomtach.wav and go to introduction message
-PRESS 1: Plays an audio greeting file go to MAIN MENU
-PRESS 2: Plays intro-record message and record caller for 10 seconds then plays back voice message 
	-If NO INPUT - play noinput.wav and go to introduction message
	-PRESS 3: Plays a 'goodbye' message and disconnects the caller

Please note that the *.wav files are installed as part of the PowerMedia XMS install process.