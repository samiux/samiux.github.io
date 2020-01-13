# **Definition of nsm.conf (Host Based)**

## The definition of the items in "nsm.conf" :

### Network interface related :

**EXT_IP :** The external IP address of the network, usually it is called "real" IP address.


## Suricata configure file related :

If you have a very powerful CPU and more than 8GB memory, you can set higher values.

**MAX_PENDING_PACKETS :** The maximum pending packets for Suricata.  The minimum value is "1024" and the maximum value is "65534".  The larger value the more amount of memory used.  The default value is "1024".  The default value is suit for 8GB memory of the system.  The higher the value the higher the CPU loading.

**RUN_MODE :** The run mode of Suricata, it is either "autofp" or "workers".  "autofp" is load balancing.  The default value is "autofp".

**DETECT_PROFILE :** The detect profile for Suricata, it can be "low", "medium" and "high".  The higher the profile, the higher CPU loading.  The default value is "medium".  The higher the value the higher memory usage.  The default value is suit for 8GB memory of the system.


### CPU Affinity related :

**MANAGEMENT_CPU :** The CPU for management purpose.  If 4 threadings, the value is "0,2".  It is the default value.

**RECEIVE_CPU :** The CPU for receive purpose.  If 4 threadings, the value is "1,3".  It is the default value.


### NFQUEUE related :

**NF_IPTABLES :** The total number of cores or threadings.  If 2 threadings, the value is "0:1".  The default is 4 threadings, "0:3".

**NF_YAML :** The total number of cores or threadings.  If 2 threadings, the value is "-q 0 -q1".  The default is 4 threadings, "-q 0 -q 1 -q 2 -q 3".



