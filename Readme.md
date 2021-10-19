# Kubernetes Ingress

Simple task for using Kubernetes nginx ingress.

## Project 
We have two files:

1- deployment.yml: include deploument with service. 

- image from dockerhub: https://hub.docker.com/r/yanivomc/spring-music
- Expose the deploy using type = ClusterIP
-  port 8090:8080

2- Ingress.yml : 
- Install the nginx ingress-controller in your cluster, follow
instructions in this link: https://kubernetes.github.io/ingress-nginx/deploy/#docker-desktop
- Ingress can access the service using http://127.0.0.1/music.

## Running the deployment
```
$ git clone https://github.com/AHMADSK1997/Kubernetes-Ingress.git
$ cd Kubernetes-Ingress
$ kubectl apply -f deployment.yml
$ kubectl port-forward deployments/spring-music-deployment 8080
```

You can then access MyBitcoin here: http://localhost:8080/

<img width="1042" alt="spring-music-screenshot" src="https://imgur.com/DBGBePj.png">

## Scale your pods 
```
kubectl scale deployments spring-music-deployment --replicas 2
```
you can check your pods using: `$ kubectl get po`
you can check your deployments using: `$ kubectl get deployment`

<img width="1042" alt="git bash screenshot" src="https://imgur.com/Mi7RCCY.png">

## Runing the ingress
```
$ kubectl apply -f Ingress.yml
```
you can check your deployments using: `$ kubectl get Ingress`
<img width="1042" alt="git bash screenshot" src="https://imgur.com/Gp8u832.png">

Now ypu can run the application using http://127.0.0.1/music URL