```
[iccadmin@centos-1 ingress]$ k get svc
NAME               TYPE           CLUSTER-IP      EXTERNAL-IP                       PORT(S)          AGE
kubernetes         ClusterIP      10.43.0.1       <none>                            443/TCP          11d
ecsdemo-nodejs     ClusterIP      10.43.49.13     <none>                            80/TCP           7d23h
ecsdemo-crystal    ClusterIP      10.43.68.19     <none>                            80/TCP           7d23h
ecsdemo-frontend   LoadBalancer   10.43.48.5      192.168.219.201,192.168.219.202   8008:32329/TCP   7d22h
ingress-test       LoadBalancer   10.43.190.203   192.168.219.202                   8008:30010/TCP   4d3h
helloweb-default   LoadBalancer   10.43.186.106   192.168.219.201,192.168.219.202   8099:31512/TCP   57m
[iccadmin@centos-1 ingress]$ k describe ingress
Name:             name-virtual-host-ingress
Namespace:        default
Address:          192.168.219.201,192.168.219.202
Default backend:  default-http-backend:80 (<error: endpoints "default-http-backend" not found>)
Rules:
  Host           Path  Backends
  ----           ----  --------
  ecs.k3s.com    
                 /   ecsdemo-frontend:8008 (10.42.0.19:3000)
  hello.k3s.com  
                 /   helloweb-default:8099 (10.42.1.15:8080)
Annotations:     <none>
Events:          <none>


[iccadmin@centos-1 ingress]$ k apply -f ingress.yaml 
ingress.networking.k8s.io/name-virtual-host-ingress configured
```
