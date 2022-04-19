Headless Service
Sometimes you dont need load-balancing and a signle service IP or we need to interact with individual PODs. in this case, you can create what are termed "headless" services, by explicitly specifiying "None" for the cluster IP

For headless Services, a cluster IP is not allocated, kube-proxy does not handle theese Services, and there is no load balancing or proxying done by the platform for them(note: although PODs are not load balalced throough kube-proxy(iptables), you get load balancing through DNS round robin mechanism).


