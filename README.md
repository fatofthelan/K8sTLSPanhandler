# K8sTLSPanhandler
Kubernetes version of the Panhandler over TLS

This is a quick way to add TLS for the panhandler docker image.

To use SecurePanHandler, create a TLS keypair in the ./conf.d/ directory named `server.key` and `server.crt`.
```openssl req -x509 -newkey rsa:2048 -nodes -keyout conf.d/server.key -out conf.d/server.crt -days 365```

Edit the `app\nginx-deployment.yaml` file, chaning the `conf.d` path to your actual path.

Enter `kubectl apply -f app` and access panhandler on the K8s host via the LoadBalancer port (will be unique each time run) https://yourhost:31000/

Login with the username and password specified in the panhandler-deployment.yaml file.
