## Approaching Argo Rollouts

I created this lab, back in time, at work as spike once we decide to study Argo and maybe adopt it at work in my current project. \
I have come across with it some days ago and I decided to publish here as well. \
Whatever has been captured here can be definitely be found and better explained on the official [`Argo Rollouts website`](https://argoproj.github.io/argo-rollouts/). \
This repository was meant to be an overview in the form of collection of labs and main concepts around this technology.

### What Argo Rollouts is
`Argo Rollouts` is a [`kubernetes`](https://kubernetes.io/) controller which also brings its own 
[`custom resource definitions`](https://kubernetes.io/docs/concepts/extend-kubernetes/api-extension/custom-resources/) which enables us to experience advanced capabilities such as:
- blue-green
- canary
- canary analysis
- experimentation
- progressive delivery features to `kubernetes`

### Why Argo Rollouts should be adopted especially for large scale k8s environments?
`Argo Rollouts` make your cluster being capable of going further than its only [`RollingUpdate`](https://kubernetes.io/docs/tutorials/kubernetes-basics/update/update-intro/) for handling deployment update. \
`RollingUpdate` in fact provides a basic set of guarantees (based on readiness probes) during the deployments' update. \
Considering that we can tell straight away that `kubernetes` on its own, out of the box, has some limitations in terms of deployment strategy when dealing with large, complex and sensitive deployments.

### Which are the actual Argo Rollouts controller features
Controller Features
- Blue-Green strategy
- Canary strategy
- Weighted traffic shifting
- Capabilities of rollback and promotion
- Customizable metric queries and analysis of business KPIs
- Integration with [`ingress controller`](https://kubernetes.io/docs/concepts/services-networking/ingress-controllers/)
- Service mesh integration (e.g. [`istio`](https://istio.io/))
- Integration with metrics mechanisms such as: 
  - [`Prometheus`](https://prometheus.io/)
  - [`Wavefront`](https://docs.wavefront.com/metric_types.html)
  - [`Kayenta`](https://cloud.google.com/blog/products/gcp/introducing-kayenta-an-open-automated-canary-analysis-tool-from-google-and-netflix)
  - [`Datadog`](https://www.datadoghq.com/)
  - [`New Relic`](https://newrelic.com/)
  - [`Graphite`](https://graphiteapp.org/)
  - [`InfluxDB`](https://www.influxdata.com/products/influxdb/)

### Getting started
Having said that [`let's get started`](01-getting-started/Readme.md#01-getting-started)

### UI Dashboard
Have a look at [`Argo UI Dashboard`](03-argo-ui-dashboard/Readme.md#03-argo-ui-dashboard)

### Deepening Deploy Strategy
Have a look at [`Strategy`](04-argo-deployment-strategy/Readme.md#04-argo-deployment-strategy)

### Argo Rollouts architecture
Have a look at [`Argo Rollouts architecture`](06-argo-rollouts-architecture/Readme.md#06-argo-rollouts-architecture)


