# **Definition of nsm.conf (Network Based)**

## The definition of the items in "nsm.conf" :

### Network interface related :

**INF_INCOMING :** The network interface name that connects to internet service provider or modem.  For example, "eth0".  
**INF_OUTGOING :** The network interface name that connects to the router or switch.  For example, "eth1".  
**INF_MONITORING :** The network interface name that connects to the switch for management purpose.  For example, "eth2".  This interface is also used for update and/or upgrade Ubuntu and Croissants.  

**INF_MONITORING_IP :** The IP address for the monitoring interface.  For example, "192.168.20.180".  
**INF_NETMASK :** The netmask for the intranet.  For example, "255.255.255.0".  
**INF_GATEWAY :** The gateway of the intranet.  For example, "192.168.20.1".  
**INF_NAMESERVER :** The IP address of DNS server.  For example, "9.9.9.9".  

**EXT_IP :** The external IP address of the network, usually it is called "real" IP address.

**INF_MONITORING_NAT :** The last digit of the IP address of the monitoring interface.  For example, 192.168.20.180, the value should be "180".


### Suricata configure file related :

If you have a very powerful CPU and more than 8GB memory, you can set higher values.

**MAX_PENDING_PACKETS :** The maximum pending packets for Suricata.  The minimum value is "1024" and the maximum value is "65534".  The larger value the more amount of memory used.  The default value is "1024".  The default value is suit for 8GB memory of the system.  The higher the value the higher the CPU loading.

**RUN_MODE :** The run mode of Suricata, it is either "autofp" or "workers".  "autofp" is load balancing.  The default value is "autofp".

**DETECT_PROFILE :** The detect profile for Suricata, it can be "low", "medium" and "high".  The higher the profile, the higher CPU loading.  The default value is "medium".  The higher the value the higher memory usage.  The default value is suit for 8GB memory of the system.


### CPU Affinity related :

**MANAGEMENT_CPU :** The CPU for management purpose.  If 4 threadings, the value is "0,2".  It is the default value.

**RECEIVE_CPU :** The CPU for receive purpose.  If 4 threadings, the value is "1,3".  It is the default value.


