# Traces Enabled

This example contains the values required to enable receiving traces, and sending them to [Grafana Tempo](https://grafana.com/oss/tempo/).

```yaml
cluster:
  name: traces-enabled-test

externalServices:
  prometheus:
    host: https://prometheus.example.com
    basicAuth:
      username: 12345
      password: "It's a secret to everyone"
  loki:
    host: https://loki.example.com
    basicAuth:
      username: 12345
      password: "It's a secret to everyone"
  tempo:
    host: https://tempo.example.com
    basicAuth:
      username: 12345
      password: "It's a secret to everyone"

traces:
  enabled: true

grafana-agent:
  agent:
    extraPorts:
      - name: "otlp-traces"
        port: 4317
        targetPort: 4317
        protocol: "TCP"
```