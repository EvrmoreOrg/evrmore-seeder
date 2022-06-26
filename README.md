# evrmore-seeder

This code was forked from https://github.com/team-exor/generic-seeder

This seeder is a spider which crawls the Evrmore peer-to-peer network, maintaining a list of Evrmore full nodes.

Features:
- Regularly revisits known nodes to check their availability
- Block explorer integration (including support for a 2nd failover explorer)
- Keep a running list of all nodes in the network or only show nodes that are above a certain version
- Bans/Unlists nodes after enough failures, or bad behaviour
- Keeps statistics over (exponential) windows of 2 hours, 8 hours, 1 day and 1 week, to base decisions on
- Very low memory (a few tens of megabytes) and cpu requirements
- Run multiple crawlers at the same time (96 threads simultaneously by default)
- Force connections to IPv4 or IPv6 only if desired
- Customizable options via configuration file

evrmore-seeder is used by the Evrmore Foundation for the benefit of the Evrmore blockchain network.
The list of seeders are uploaded to the Cloudflare DNS servers using the included python utility.
Cloudflare then provides lists of active nodes at "seeder-mainnet.evrmorecoin.org" and "seeder-testnet.evrmorecoin.org".
By checking those sites, the Evrmore core code (evrmored & evrmore-qt) can be assured of always finding peers to connect to.

You can also use this code to set up a private instance of evrmore-seeder, for instance to connect together all the Evrmore 
nodes running inside your corporate firewall.

evrmore-seeder has the ability to act as a standalone DNS server. You may find that capability useful, but it is not used by
the Evrmore Foundation.

Much more detail is available about the capabilities, customization, and installation at
[The original README](/READMETOO.md) and
[Setup Guide](/SETUP.md)
