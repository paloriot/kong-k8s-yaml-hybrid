# Install Kong Enterprise in Hybrid mode with kubectl apply

## Information
This repo helps you to install Kong in hybrid mode with `kubectl apply` (without Helm).

In this example:
- The Control Plane (CP) and Data Plane (DP) are deployed in the same namespace (called kong). Feel free to change the namespace of CP and DP.
- In hybrid mode, a mutual TLS handshake (mTLS) is used for authentication between DP and CP. The Shared Mode is used in this example. For production, use PKI mode, see: 
https://docs.konghq.com/gateway/latest/production/deployment-topologies/hybrid-mode/setup/
- Adapt the URL (pre-configured in **both** yaml files) to your environment. The URL is for instance http://kong-proxy.client.net or http://kong-manager.client.net

## Prerequisites
- A Kubernetes cluster, v1.19 or later
kubectl v1.19 or later
- (Enterprise only) A license.json file from Kong

## How to install Kong in hybrid mode
1) Create namespace

```kubectl create namespace kong```