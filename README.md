# helloworld-app
A simple NodeJS app for Kubernetes bootcamps

### 1) Download Docker Desktop and install it on your laptop

### 2) Build a container image - replace YOUR_NAME with your name like amithn for example
```
docker build . -t harbor.tanzuworkshop.com/bootcamp/YOUR_NAME-app
```

# 3) Login to the container registry
```
docker login -u bootcamp harbor.tanzuworkshop.com
```

# 4) Push the image to the container registry 
```
docker push harbor.tanzuworkshop.com/bootcamp/YOUR_NAME-app
```

# 5) Deploy the image to Kubernetes (replace all occurence of YOUR_NAME with your name in the file config/pod.yaml)

```
kubectl apply -f config/pod.yaml
```

# 6) Deploy a Service to get traffic to your pod (replace all occurence of YOUR_NAME with your name in the file config/service.yaml)

```
kubectl apply -f config/service.yaml
```

# 7) Accessing your service 
```
➜  helloworld-app git:(main) ✗ kubectl get svc
NAME                 TYPE           CLUSTER-IP     EXTERNAL-IP     PORT(S)        AGE
helloworld-service   LoadBalancer   10.108.235.7   10.213.112.72   80:31866/TCP   4m58s
```

Copy the IP address under EXTERNAL-IP and head to http://EXTERNAL-IP 
if all went well, you should see the page with your name! 

