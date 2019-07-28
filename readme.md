# Kubernetes with Traefik as Ingress Controller #

Configuration of Kubernetes Traefik Ingress Controller.

In the example_service there is a simple Nodejs httpserver that we can use as test.

## Download the Configuration File ##

If you are using Kubernetes managed by Digital Ocean we can use the `doctl` command to retrieve the kubeconfig:
`doctl kubernetes cluster kubeconfig save k8s-1-14-4-fra1-1564234695696`
