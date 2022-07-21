# Flux CheatSheet

## Get all not ready helmreleases
```sh
flux get hr -A --status-selector=ready=false
```

## Suspend them one by one (didn't find a way to suspend all non ready helmreleases)
```sh
flux suspend hr -n istio-gateway-system istio-ingress-gateway-vpn
```

## Resume them all for a namespace (didn't find a way to resume all for all namespaces)
```sh
flux resume hr -n istio-gateway-system --all
```