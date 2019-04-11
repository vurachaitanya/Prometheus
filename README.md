# Prometheus
Prometheus setup and configuration 
- Download it from :https://github.com/prometheus/prometheus/releases/download/v2.8.0-rc.0/prometheus-2.8.0-rc.0.linux-amd64.tar.gz
- mkdir prometheus ; cd prometheus ; weget https://github.com/prometheus/prometheus/releases/download/v2.8.0-rc.0/prometheus-2.8.0-rc.0.linux-amd64.tar.gz ; tar xvfz prometheus-*.tar.gz
- Sample Kubernetes yml configuration : https://raw.githubusercontent.com/prometheus/prometheus/master/documentation/examples/prometheus-kubernetes.yml
- Start the service with ./prometheus --config.file="prometheus.yml" so as to start the service at localhost:9090 and localhost:9090/metrics has the metrics of the service started.
- Node exporter link : https://prometheus.io/download/#node_exporter

# Prometheus Docker version:
```
docker run -d -p 9090:9090 prom/prometheus 
docker run -d -p 9100:9100 prom/node-exporter

```
