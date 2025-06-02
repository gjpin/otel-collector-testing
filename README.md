# How to
```bash
# Install OTEL Collector
kubectl kustomize ./opentelemetry-collector/resources | kubectl apply -f -

# Install OTEL telemetry generator
kubectl kustomize ./telemetrygen/resources | kubectl apply -f -
```

# References
- [telemetrygen](https://github.com/open-telemetry/opentelemetry-collector-contrib/tree/main/cmd/telemetrygen)