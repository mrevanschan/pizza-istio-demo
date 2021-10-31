# pizza-istio-demo

First prepare the image on docker hub for the follow microservices: <br>
https://github.com/mrevanschan/order-service <br>
https://github.com/mrevanschan/order-generator <br>

If you are using your own docker hub account please change the image in spec.template.spec.containers.image for both order-service.yaml & order-generator.yaml,to point to your own docker hub repository.

## Prerequisites
Make sure you have installed all of the following prerequisites on your development machine:
* Docker Desktop - please also have kubenetues enabled and set at least 6 cpu cores and 8GB memory
* Istio - please run "export PATH=$PWD/bin:$PATH" in installation directory so you can use istioctl

## Install Steps
Run the following lines
```
istioctl install
kubectl label namespace default istio-injection=enabled
kubectl apply -f order-service.yaml -f order-generator.yaml
```
