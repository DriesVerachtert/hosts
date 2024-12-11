* v1.12.0 of the nginx ingress controller for k8s
* https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v1.12.0/deploy/static/provider/cloud/deploy.yaml
* added the hostNetwork: true setting in the deployment => template => spec, as I'm using this on single controller-and-worker-all-in-one-node k0s clusters
* commented out the service of type LoadBalancer
* split in smaller parts as k0s on a raspberry PI gets timeouts => try first with just the namespace to make sure simple resources can be created at least
* TODO: convert Deployment into DaemonSet as it doesn't make sense to have a deployment when using host networking: only 1 pod can use those ports at a time

