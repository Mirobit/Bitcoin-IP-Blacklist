# Bitcoin IP Blacklist

This project maintains a list with IPs that have shown harmful behavior to the Bitcoin network. 
This includes ressource wasting, slot blocking, exploiting and spying.

## Lists

Aside from the original IP list, lists with ban commands for iptables, bitcoin-cli and bitcoin-qt are available. 
Some IPs (peers) tend to ignore the ban and [try constantly](http://imgur.com/5clGbB4) to reconnect. So you 
should consider banning them at OS level (e.g. `iptables`). The ban time for the bitcoin-cli and bitcoin-qt commands is set to 1 year.

* [IPs](ips.txt) - Includes IP, client and ban reason
* [iptables](iptables.txt) - Commands for iptables/ip6tables ([How to make iptables persistent](https://askubuntu.com/questions/66890/how-can-i-make-a-specific-set-of-iptables-rules-permanent))
* [bitcoin-cli](bitcoin-cli.txt) - Commands for bitcoin-cli (`bitcoin-cli listbanned` returns a list of all banned IPs)
* [bitcoin-qt](bitcoin-qt.txt) - Commands for bitcoin-qt (`Help` -> `Debug window` -> `Console` (you need to enter every single line by hand))

## What is malicious behavior?

That is a tricky question. It is not always easy to distinguish malicous behavior from normal behavior. That is why I focused
so far on the most obvious malicious peers. The following lists contains a few suspicius behaviors with no non-malicious use cases.

* Peers that reconnect every few seconds all day long. They [continue](http://imgur.com/5clGbB4) to do so even after a ban (spying?, trolling?)
* Groups of peers from the same subnet (AWS hosted), with SPV agents that stay connected to your node for a long time (slot blocking)

## Contributing

If you noticed any malicious peers please open an `Issue` with the list of IPs including the client and the reason for the ban
or open a `Pull request` with all 4 IP lists updated. Check your `debug.log` file or current peer list for suspicious peers.
