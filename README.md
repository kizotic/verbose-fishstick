# Helm Chart: Node.js App Stack
This chart deploys a Node.js application fronted by an Envoy Gateway (L7) and an HAProxy Load Balancer (L4) within a Kubernetes cluster.

# Architecture Overview
Traffic flows from the external network through the L4 Load Balancer into the L7 Gateway, which routes requests to the Node.js application pods.

# Prerequisites
- A purchased domain
- Kubernetes cluster (v1.30+)
- Helm v3.x
- HAProxy Ingress Controller (or equivalent L4 LB) installed
- Envoy Gateway installed
- Metrics Server installed (for Horizontal Pod Autoscaler)

# Installation Guide
- Change values in `values.yaml` according to your setup.
- Put tls and key files in `certs/`
- Run `helm upgrade --install <release-name> . -n <namespace> --create-namespace`
