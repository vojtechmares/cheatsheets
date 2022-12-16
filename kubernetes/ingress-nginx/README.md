# ingress-nginx

## On premise considerations

General:

```yaml
controller:
  kind: DaemonSet

  ingressClassResource:
    default: true
```

### Host port

```yaml
controller:
  hostPort:
    enabled: true

  service:
    type: ClusterIP
```

### Service, type: `NodePort`

```yaml
controller:
  service:
    type: NodePort
    nodePorts:
      http: 32080
      https: 32443
```

## Cloud provisioned (public & private)

### Service, type: `LoadBalancer`

Useful with cloud providers or at least with `cloud-controller-manager` (CCM) which can provision load balancer(s) for Services.

```yaml
controller:
  service:
    type: LoadBalancer
```

List of providers I have tried this on:

- AWS
- GCP
- Azure
- DigitalOcean
- Heztner Cloud with it's [CCM](https://github.com/hetznercloud/hcloud-cloud-controller-manager)
