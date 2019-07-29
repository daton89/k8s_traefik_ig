# Kubernetes with Traefik as Ingress Controller #

Configuration of Kubernetes Traefik Ingress Controller.

In the example_service there is a simple Nodejs httpserver that we can use as test.

## Download the Configuration File ##

If you are using Kubernetes managed by Digital Ocean we can use the `doctl` command to retrieve the kubeconfig:

`doctl kubernetes cluster kubeconfig save k8s-1-14-4-fra1-1564234695696`

Otherwise download the kubeconfig file and store it in `~/.kube/config`

Now test if you can access the cluster running: `kubect get nodes`

## Configure the Ingress Controller ##

Create the traefik configuration:

`kubectl apply -f traefik.yml`

Create the Load Balancer:

`kubectl apply -f traefik-load-balancer.yml`

Check the Load Balancer:

`kubectl -n ingress-traefik get services`

Now set the the ip that return from the external-ip of the ingress-traefik service into the DNS A record of our domain.

So we can now point the DNS record to the external Load Balancer, we can deploy the Ingress.

## Deploy the Ingress ##

Create the Ingress:

`kubectl apply -f ingress.yml`

Create the WebUi service:

`kubectl apply -f traefik-web-ui.yml`

## Deploy the example application ##



## Deploy a load balancer ##

Next, we'll create the Ingress Controller LoadBalancer Service, which will create a DigitalOcean Load Balancer that will load balance and route HTTP and HTTPS traffic to the Ingress Controller Pod deployed in the previous command.