# pizza-istio-demo


## Intro
Here are repository for the docker images that I build the docker image from: <br>
https://github.com/mrevanschan/order-service <br>
https://github.com/mrevanschan/order-generator <br>

I have already pushed the images to my docker hub account, but if you want to use your own docker hub account please change the image in spec.template.spec.containers.image for both order-service.yaml & order-generator.yaml,to point to your own docker hub repository.

## Prerequisites
Make sure you have installed all of the following prerequisites on your development machine:
* Docker Desktop - please set resources to have at least 6 cpu cores and 8GB memory. Also please have kubenetues enabled
* Istio - please run "export PATH=$PWD/bin:$PATH" in installation directory so you can use istioctl in command line

## Install Steps
Run the following from root directory:
```
istioctl install
kubectl label namespace default istio-injection=enabled
kubectl apply -f order-service.yaml -f order-generator.yaml
```

## Verity Orders

To verify orders being passed from one microservice to the other. Run the following:
```
kubectl get pod
```
To get the pod names then run the following is seperate terminals for each pod: 
```
kubectl logs <pod-name> -f
```
