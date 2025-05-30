# Dependencies
```bash
helm repo add open-telemetry https://open-telemetry.github.io/opentelemetry-helm-charts
```

# Running
```bash
# valkey
helm upgrade --install valkey oci://registry-1.docker.io/bitnamicharts/valkey \
    --namespace valkey \
    --create-namespace \
    -f values/valkey.yaml

# otel inbound
helm upgrade --install otel-inbound open-telemetry/opentelemetry-collector \
    --namespace otel-inbound \
    --create-namespace \
    -f values/otel-inbound.yaml

# otel outbound
helm upgrade --install otel-outbound open-telemetry/opentelemetry-collector \
    --namespace otel-outbound \
    --create-namespace \
    -f values/otel-outbound.yaml

# other resources
kubectl apply -f resources/
```

# Destroying
```bash
kubectl delete namespace valkey
kubectl delete namespace otel-inbound
kubectl delete namespace otel-outbound
kubectl delete namespace otel-debug
kubectl delete -f resources/
```

# Access Redis
`kubectl port-forward -n valkey-primary svc/valkey 6379:6379`

# References
[Telemetry Gen](https://github.com/open-telemetry/opentelemetry-collector-contrib/tree/main/cmd/telemetrygen)