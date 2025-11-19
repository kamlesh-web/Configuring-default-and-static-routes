	# Configuring-default-and-static-routes
	
	Router>
	Router>enable
	Router#
	Router#
	Router#show ip route
	Codes: L - local, C - connected, S - static, R - RIP, M - mobile, B - BGP
	       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
	       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
	       E1 - OSPF external type 1, E2 - OSPF external type 2, E - EGP
	       i - IS-IS, L1 - IS-IS level-1, L2 - IS-IS level-2, ia - IS-IS inter area
	       * - candidate default, U - per-user static route, o - ODR
	       P - periodic downloaded static route
	
	Gateway of last resort is not set
	
	
	Router#
	Router#
	Router#configure terminal
	Enter configuration commands, one per line.  End with CNTL/Z.
	Router(config)#
	Router(config)#
	Router(config)#
	Router(config)#interface g0/0/0
	Router(config-if)#
	Router(config-if)#ip address 192.168.100.1 255.255.255.252
	Router(config-if)#
	Router(config-if)#no shutdown
	
	Router(config-if)#
	%LINK-5-CHANGED: Interface GigabitEthernet0/0/0, changed state to up
	
	Router(config-if)#
	%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0/0, changed state to up
	
	Router>enable 
	Router#
	Router#
	Router#show ip route
	Codes: L - local, C - connected, S - static, R - RIP, M - mobile, B - BGP
	       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
	       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
	       E1 - OSPF external type 1, E2 - OSPF external type 2, E - EGP
	       i - IS-IS, L1 - IS-IS level-1, L2 - IS-IS level-2, ia - IS-IS inter area
	       * - candidate default, U - per-user static route, o - ODR
	       P - periodic downloaded static route
	
	Gateway of last resort is not set
	
	     192.168.100.0/24 is variably subnetted, 2 subnets, 2 masks
	C       192.168.100.0/30 is directly connected, GigabitEthernet0/0/0
	L       192.168.100.1/32 is directly connected, GigabitEthernet0/0/0
	
	Router#configure terminal
	Enter configuration commands, one per line.  End with CNTL/Z.
	Router(config)#
	Router(config)#enable secret CCNA
	Router(config)#
	Router(config)#ip route 192.168.101.0 255.255.255.252 g0/0/0 192.168.100.2
	Router(config)#
	Router(config)#do show ip route
	Codes: L - local, C - connected, S - static, R - RIP, M - mobile, B - BGP
	       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
	       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
	       E1 - OSPF external type 1, E2 - OSPF external type 2, E - EGP
	       i - IS-IS, L1 - IS-IS level-1, L2 - IS-IS level-2, ia - IS-IS inter area
	       * - candidate default, U - per-user static route, o - ODR
	       P - periodic downloaded static route
	
	Gateway of last resort is not set
	
	     192.168.100.0/24 is variably subnetted, 2 subnets, 2 masks
	C       192.168.100.0/30 is directly connected, GigabitEthernet0/0/0
	L       192.168.100.1/32 is directly connected, GigabitEthernet0/0/0
	     192.168.101.0/30 is subnetted, 1 subnets
	S       192.168.101.0/30 [1/0] via 192.168.100.2, GigabitEthernet0/0/0
		
	Router(config)#do write
	Building configuration...
	[OK]
	Router(config)#
	Router(config)#do ping 192.168.101.2
	
	Type escape sequence to abort.
	Sending 5, 100-byte ICMP Echos to 192.168.101.2, timeout is 2 seconds:
	!!!!!
	Success rate is 100 percent (5/5), round-trip min/avg/max = 8/14/20 ms
	
	Router(config)#
