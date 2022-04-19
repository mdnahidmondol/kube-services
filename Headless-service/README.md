# Headless Service
- Sometimes you dont need load-balancing and a signle service IP or we need to interact with individual PODs. in this case, you can create what are termed "headless" services, by explicitly specifiying "None" for the cluster IP

- For headless Services, a cluster IP is not allocated, kube-proxy does not handle theese Services, and there is no load balancing or proxying done by the platform for them(note: although PODs are not load balalced throough kube-proxy(iptables), you get load balancing through DNS round robin mechanism).



```sh
nslookup headless-hello-world.default.svc.cluster.local
```

```sh Name: headless-hello-world.default.svc.cluster.local
Address 1: 192.168.9.87 192-168-9-87.headless-hello-world.default.svc.cluster.local
Address 2: 192.168.9.86 192-168-9-86.headless-hello-world.default.svc.cluster.local
Address 3: 192.168.233.207 192-168-233-207.headless-hello-world.default.svc.cluster.local
Address 4: 192.168.233.206 192-168-233-206.headless-hello-world.default.svc.cluster.local
```

### From inside a POD
```sh
nslookup hello-world
```

```sh Name: hello-world
Address 1: 10.102.1.248 hello-world.default.svc.cluster.local

```

