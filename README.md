# ipfire-scripts #

## dns_blocker.sh ##

Will download hosts that are labeled as malicious from multiple sources and create a file that will cause unbound or dnsmasq to block them via DNS queries. 

To install, ssh to your ipfire machine and use the following commands.
- cd ~
- mkdir -p bin
- cd bin
- wget https://raw.githubusercontent.com/sfeakes/ipfire-scripts/master/dns_blocklist.sh
- chmod 755 dns_blocklist.sh

Then simply run the script every time you want to update the blocklist. (use fcrontab to run it a regular intervals with cron)

### If you are using dnsmasq and not unbount, there is one further step ###
(dnsmasq is default on IPFire 2.19 - Core Update 105 and below)
(unbound is default on IPFire 2.19 - Core Update 106 and above)

- create a file /etc/sysconfig/dnsmasq with following the contents
- CUSTOM_ARGS="--addn-hosts=/var/ipfire/dhcp/blocked.hosts"


### Below are a list of the sources that can be configured (turned on or off) in the script ###

| URL                                                                              | Details                                                 | License |
| -------                                                                          | -------                                                 | ------- |
|[Adaway list](https://adaway.org/hosts.txt)                                       | Infrequent updates, approx. 500 entries                 | CC Attribution 3.0 |
|[Malware domain list] (http://www.malwaredomainlist.com/hostslist/hosts.txt)      | Daily updates, aprox 1,300                                            | non-commercial community project |
|[MVPS Hosts](http://winhelp2002.mvps.org/hosts.htm)                               | Infrequent updates, approx. 500 entries              | CC Attribution-NonCommercial-ShareAlike 4.0 |
|[Peter Lowe’s Ad server list](http://pgl.yoyo.org/adservers/)                     | Weekly updates, approx. 2,500 entries                   | ? |
|[StevenBlack - hosts](https://github.com/StevenBlack/hosts/)                      | Weekly updates, aprox. 34,000                                                        | ? |
|[Dan Pollock’s hosts file](http://someonewhocares.org/hosts/)                     | Weekly updates, approx. 12.000 entries                  | non-commercial |
|[CAMELEON](http://sysctl.org/cameleon/)                                           | Weekly updates, approx. 21.000 entries                  | ? |
|[hpHosts‎](http://www.hosts-file.net/)                                             | Daily updates, approx. 500,000 and error prone               | *Read [Terms of Use](http://www.hosts-file.net/)* |
|[Hostfile project](http://hostsfile.org/hosts.html)                               | Weekls updates                                          | LGPL as GPLv2 |
|[The Hosts File Project](http://hostsfile.mine.nu)                                | Infrequent updates                                      | LGPL |
|[notracking - hosts-blocklists](https://github.com/notracking/hosts-blocklists)   | Daily updates, (Includes most of above and others)      | ? |
|[Airelle's host file](http://rlwpx.free.fr/WPFF/hosts.htm)                        | NOT SUPPORTED YET                                       | CC Attribution 3.0 |
|[Shalla's Blacklists ](http://www.shallalist.de/)                                 | NOT SUPPORTED YET                                       | ? |

