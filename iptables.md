#20. September 2017
iptables -I INPUT -s 129.13.252.47/32 -j DROP
iptables -I INPUT -s 129.13.252.36/32 -j DROP
ip6tables -I INPUT -s 2a00:1398:4:2a00::a5 -j DROP
ip6tables -I INPUT -s 2a00:1398:4:2a00::a1 -j DROP