```bash
stat -c %b /var/lib/otelcol/storage/exporter_otlp__traces
ls -lh /var/lib/otelcol/storage/exporter_otlp__traces


kubectl delete pods -l app=opentelemetry-collector -n opentelemetry --force --grace-period=0
stat -c %b /var/lib/otelcol/storage/exporter_otlphttp__traces


k scale --replicas=0 deployment collector-contrib-telemetrygen -n opentelemetry-demo



while true; do \
stat -c %b /var/lib/otelcol/storage/exporter_otlp__traces && sleep 1s ; \
done

while true; do \
cat /proc/7/status | grep -E 'Name|VmRSS|VmSize' && sleep 1s ; \
done
```