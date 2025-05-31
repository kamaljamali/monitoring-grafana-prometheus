# 📊 Monitoring Stack with Prometheus, Grafana, and Exporters

This project sets up a full monitoring stack using Docker Compose. It includes:

- Prometheus for collecting metrics
- Grafana for visualization
- Exporters for monitoring various services:
  - Node (host) metrics
  - Redis
  - MongoDB
  - RabbitMQ
  - Custom LoopBack app

---

## 🚀 Stack Components

### 🔹 Prometheus
Collects metrics from exporters and services.

- **Port**: `9090`
- **Config path**: `./prometheus/prometheus.yml`

### 🔹 Grafana
Visualizes data from Prometheus.

- **Port**: `8585` (default Grafana port `3000` mapped to `8585`)
- **Data volume**: `grafana-storage:/var/lib/grafana`

### 🔹 Node Exporter
Exports hardware and OS metrics.

- **Port**: `9100`
- **Grafana Dashboard**: [ID 1860](https://grafana.com/grafana/dashboards/1860)

### 🔹 Redis Exporter
Exports Redis metrics.

- **Port**: `9121`
- **Credentials**: Redis connection string in `REDIS_ADDR`
- **Grafana Dashboard**: [ID 11835](https://grafana.com/grafana/dashboards/11835)

### 🔹 MongoDB Exporter
Exports MongoDB metrics with multiple collectors enabled.

- **Port**: `9216`
- **URI**: `MONGODB_URI` (with authentication)
- **Grafana Dashboard**: [ID 2583](https://grafana.com/grafana/dashboards/2583)

### 🔹 RabbitMQ Exporter
Exports RabbitMQ metrics.

- **Port**: `9419`
- **Credentials**: Provided via `RABBIT_URL`
- **Grafana Dashboard**: [ID 4279](https://grafana.com/grafana/dashboards/4279)

### 🔹 Custom LoopBack App
Monitored via custom metrics endpoint.

- **Metrics Path**: `/api/v1/reservation-service/metrics`
- **Scheme**: `https`
- **Target**: `metop.ir`
- **Grafana Dashboard**: Custom (user-defined)

---

## 🧰 How to Use

1. **Clone the repository**
   ```bash
   git clone https://your-repo-url.git
   cd your-repo
