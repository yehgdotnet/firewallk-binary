# firewallk-binary

This is a pre-compiled ready-to-run Firewalk for BackTrack Distro.

This is a fixed version for the famous Firewalk tool (http://packetstormsecurity.org/UNIX/audit/firewalk/) that couldn't be compiled on modern nix boxes.

Modified fixed source code included.

For those of you who are new to Firewalk:

Firewalk is an active reconnaissance network security tool that attempts to determine what layer 4 protocols a given IP forwarding device will pass. Firewalk project works by sending out UDP or TCP packets with a TTL one greater than the targeted gateway.

If the gateway allows the traffic, it will forward the packets to the next hop where they will expire and elicit an ICMP_TIME_EXCEEDED message. If the gateway hostdoes not allow the traffic, it will likely drop the packets on the floor and we will see no response.

To get the correct IP TTL that will result in expired packets one beyond the gateway we need to ramp up hop-counts. We do this in the same manner that traceroute works. Once we have the gateway hopcount (at that point the scan is said to be bound) we can begin our scan.

It is significant to note the fact that the ultimate destination host does not have to be reached. It just needs to be somewhere downstream, on the other side of the gateway, from the scanning host.

Src: http://linux.softpedia.com/get/System/Networking/Firewalk-10274.shtml

