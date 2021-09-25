# opa-policy

This repo contains information for policies to grant access to a web application accoding to a given role included in a JWT. It works with istio (not envoy) as mesh service. 

# requirements

- A K8S cluster with istio
- The bookinfo (https://istio.io/latest/docs/examples/bookinfo/) example deployed in the cluster. Only follow the instructions to deploy the app but use the bookinfo.yaml file from this repo to try OPA. 

# notes

There is no need to "install" OPA in the cluster. This line deploys OPA as a sidecar: https://github.com/carlosvalarezo/opa-policy/blob/50603a53b9ec5b5ce7df970e29c0e35fe18b827a/bookinfo.yaml#L327

To generate tokens:
- Go to https://jwt.io/ and in the payload section add a key: "role":"admin" -> This token has access. "role":"guest" -> This token does not have access 

# links
OPA: https://www.openpolicyagent.org/
