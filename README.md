**BGP Community Guide![](kerfuffle.png)**

Below are the BGP communities set by or accepted by Kerfuffle AS35008. Action communities are only accepted from customers and all of our communities are stripped from peers and transits by default.

**Providers**

|**Provider Name**|**Type**|**Provider ID**|**Default Local Pref**|**Default MED**|
| - | - | - | - | - |
|Hurricane Electric|Transit [50]|6939|90|5|
|Edgoo|Transit [50]|47787|90|0|
|FCIX - IXP|IXP [51]|33495|95|0|
|SFMIX - IXP|IXP [51]|12276|95|5|
|FREMIX - IXP|IXP [51]|57369|95|5|
|LAMBDA - IXP|IXP [51]|51930|95|5|

**Default Local Preferences**

90 De-pref 2 - Standard Transit

95 De-pref 1 - Standard Peering

100 Normal / Customer

105 Elevated 1

110 Elevated 2

**Blackhole Communities**

35008:666 Global RTBH

35008:888 Local RTBH

Prefixes of /32 IPv4 and /128 IPv6 tagged with these communities will perform RTBH actions. Tagging with 35008:666 will also send blackhole communities to AS35008 transit providers and select peers where RTBH has been negotiated. 35008:888 will only blackhole inside AS35008.

**Informational Communities**

*Route Type*

35008:50 Transit

35008:51 Peering

35008:52 Customer

35008:53 Originated

*Provider Origin*

35008:nnn Where nnn is the Provider ID

*Originating/Learning Device*

35008:11 r1.fmt2

35008:12 gw1.fmt2

35008:17 vrr01.fmt2

35008:18 vrr02.fmt2

**Action Communities**

Below are communities which can be used by customers, when announcing your prefixes to AS35008. Controls include prepending toward a specific transit provider, specific IXP, or by provider type e.g. all peers, all transits, all customers.

*By default you can perform prepend or do not announce actions toward a specific provider or set of peers at an IXP*

65101:nnn Prepend 35008 x1 toward <providerid>

65102:nnn Prepend 35008 x2 toward <providerid>

65103:nnn Prepend 35008 x3 toward <providerid>

65104:nnn Do not announce toward <providerid>

*You can also choose to affect announcements toward all networks within a specific type - e.g. prepend x1 toward all transits, or prepend x1 toward all peering exchanges*

65101:nn Prepend 35008 x1 toward <type>

65102:nn Prepend 35008 x2 toward <type>

65103:nn Prepend 35008 x3 toward <type>

65104:nn Do not announce toward <type>

Where types are;

50 Transit
51 Peer
52 Customer
