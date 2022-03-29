### 1. Create ns
```
k create ns portainer
```
### 2. Create PVC
```
k apply -f pvc.yaml -n portainer
```
### 3. Create etc...
```
k apply -f portainer.yaml -n portainer
```
