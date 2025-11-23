# Grafana Dashboard for Prometheus Monitoring

A comprehensive Grafana dashboard designed to monitor Prometheus itself, providing visibility into Prometheus performance, resource usage, and operational metrics.

## Overview

This dashboard helps you monitor the health and performance of your Prometheus instance(s), including:

- **Uptime Status**: Track Prometheus availability
- **Scrape Metrics**: Monitor scrape duration, samples scraped, and scrape errors
- **TSDB Performance**: View time-series database head series and chunks
- **Resource Usage**: Track memory consumption and CPU time
- **Rule Evaluation**: Monitor rule evaluation duration
- **Active Targets**: Keep track of active scrape targets

### Features

- **Instance Filtering**: Filter metrics by specific Prometheus instance or view all instances together
- **Real-time Updates**: 10-second refresh interval
- **3-Hour Default Time Range**: Configurable time window for historical data

## Panels Included

1. **Prometheus Up** - Shows if Prometheus is running
2. **Scrape Duration (seconds)** - Tracks how long scrapes take
3. **Scrape Samples Scraped** - Number of samples collected per scrape
4. **Scrape Errors** - Monitors scraping errors
5. **TSDB: Head Series** - Time-series database head series count
6. **TSDB: Chunks** - Number of chunks in the TSDB
7. **Prometheus Memory Usage** - Memory consumption metrics
8. **Prometheus CPU Time** - CPU usage tracking
9. **Rule Evaluation Duration** - Time taken to evaluate rules
10. **Prometheus Active Targets** - Number of active scrape targets

## Installation

1. Log into your Grafana instance
2. Navigate to **Dashboards** → **Import**
3. Upload the `grafana-dashboard.json` file or paste its contents
4. Select your Prometheus datasource
5. Click **Import**

## Requirements

- Grafana 7.0 or higher
- A configured Prometheus datasource in Grafana
- Prometheus server exposing its own metrics (default endpoint: `/metrics`)

## Configuration

Ensure your Prometheus instance is configured to scrape its own metrics by adding this to your `prometheus.yml`:

```yaml
scrape_configs:
  - job_name: 'prometheus'
    static_configs:
      - targets: ['localhost:9090']
```

## Usage

Once imported, the dashboard provides real-time monitoring of your Prometheus instance. Use it to:

- **Filter by instance**: Use the dropdown at the top to select a specific Prometheus instance or view "All" instances
- Detect performance issues or degradation
- Monitor resource consumption trends
- Identify scraping problems
- Track TSDB growth and efficiency
- Ensure rule evaluation is performant

The instance selector allows you to monitor multiple Prometheus instances from a single dashboard, making it ideal for federated or highly available Prometheus setups.

## License

See [LICENSE](LICENSE) file for details.

