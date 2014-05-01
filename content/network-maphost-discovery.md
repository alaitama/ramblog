Title: Network map/Host Discovery
Date: 2013-06-21 11:50
Author: ramborg
Category: Systems
Tags: network map, network topology map
Slug: network-maphost-discovery

Network mapping for discover hosts and topology in a LAN. Is the
previous step for tapping in the web or attack a host.

There are many tools fot this. I remember two good tools in my times,
[Iris][], [Retina,][] not free and I don't know how are good now. But
with NMAP you can do this.

For view the hosts in company lan:  
`nmap -sL 10.0.0.0/8`  
Too much hosts, I try the next command for less hosts. This limits to
the subhost 10.15.255.255(1+2+4+8) :  
`nmap -sL 10.0.0.0/12`  
Or in a personal LAN we could do:  
`nmap -sL 192.168.1.0/24`

More options for host detection explained in nmap.org:  
<http://nmap.org/book/man-host-discovery.html>

References:

-   [NMap.org Man Host Dicovery][]
-   [Yahoo answer about 10.0.0.0/8][]
-   [Simple explanation Network map][]
-   [Free tools LAN/Network map][]
-   <http://nmap.org/book/zenmap-topology.html>

  [Iris]: http://www.amtsoft.com/iris/index.htm
  [Retina,]: http://www.amtsoft.com/retina/index.htm
  [NMap.org Man Host Dicovery]: http://nmap.org/book/man-host-discovery.html
  [Yahoo answer about 10.0.0.0/8]: http://answers.yahoo.com/question/index?qid=20080529005535AAYjvo0
  [Simple explanation Network map]: http://windows.microsoft.com/en-us/windows7/why-are-computers-missing-from-the-network-map
  [Free tools LAN/Network map]: http://www.nonags.com/nonags/lan.html
