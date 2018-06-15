## DockerCon 2018 Talk: Demystifying Application Connectivity with Kubernetes in the Docker Platform

This is the app we used for the demo:

- `stars.yml` is the applicaiton deployment manifest
- `ingress.yml` is the ingress rule for accessing the management UI ( requires that you have already deployed an Ingress Controller)
- `security-policy.yml` is the security policy configruation.


Note that you need to specify the proper hostname in the the ingress yamll file based on your application name. Othersise, you can access the UI via a configurable nodeport (default is `32768`)

