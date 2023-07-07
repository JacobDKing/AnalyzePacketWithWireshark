# Analyzing a Packet Capture With Wireshark
This project is meant to exemplify my aptitude and comfortability with conducting various search queries and analyzing packet data from within Wireshark.
<br />

Network packet capture files that contain traffic data related to a user connecting to an internet site will be used for analysis. The ability to filter network traffic using packet sniffers to gather relevant information is an essential skill as a security analyst.
<br />
<br />
Data must be filtered in order to:
<br />
  ●   identify the source and destination IP addresses involved in this web browsing session, <br />
  ●   examine the protocols that are used when the user makes the connection to the website, and <br />
  ●   analyze some of the data packets to identify the type of information sent and received by the systems that connect to each other when the network data is captured. <br />

<h2>Explore Data With Wireshark</h2>
  In this step, a network packet capture file that contains data captured from a system that made web requests to a site must be opened. This will be done with Wireshark to get an overview of how the data is presented in the application.
[insert picture]

<br />
<br />

<h2>Apply a Wireshark Filter and Inspect a Packet</h2>
In this step, Wireshark is used to open a packet for more detailed exploration and filter the data to inspect the network layers and protocols contained in the packet.
[insert picture]
In this scenario, we will analyze the first packet that lists TCP as the protocol. Each subtree listed is
opened and viewed to gain different information in regards to the packet.
[insert picture]
After analyzing this packet, we return to the main tree.

<br />
<br />

<h2>Use Filters to Select Packets</h2>
In this step, filters will be used to analyze specific network packets based on where the
packets came from or where they were sent to. Packets will be selected using either
their physical Ethernet Media Access Control (MAC) address or their Internet Protocol
(IP) address. <br />
Examples of used filters and their results may be seen below:
[insert picture]
[insert]
[inse]

<br />
<br />

<h2>Use Filters to Explore DNS Packets</h2>
In this step, filters will be used to select and examine DNS traffic. Once sample DNS
traffic has been selected, commands will be used to drill down into the protocol to
examine how the DNS packet data contains both queries (names of internet sites that
are being looked up) and answers (IP addresses that are being sent back by a DNS
server when a name is successfully resolved). <br />
DNS traffic uses UDP port 53, so we will use this port to list traffic related only to DNS
queries and responses. 
[insert picture]
We then view and confirm the queried website of the first packet listed.
[insert picture]
Here we see that the website queried was (opensource.google.com).

<br />
<br />

<h2>Use Filters to Explore TCP Packets</h2>
In this step, additional filters must be used to select and examine TCP packets. Text that
is present in payload data contained inside network packets will be used to search. This
will locate packets based on something such as a name or some other text that is of
interest. <br />
In this case, we’ll search for the web traffic port 80.
[insert picture]
We will select the first packet in the list to analyze. The destination IP of this packet is
169.254.169.254 
<br />
Conducting a quick analysis, you can see that the Frame Length (as specified in the Frame
subtree) is 54 bytes. The Time to Live, Frame Length, and Destination Address (all found within
the IPV4 subtree) are ‘64’, ‘54 bytes’, and ‘169.254.1.139’ respectively.
[insert picture]
Finally, we conduct one last search filter to select TCP packet data that contains specific text
data.
[insert picture]
