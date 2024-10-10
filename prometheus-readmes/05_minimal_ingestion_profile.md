# Prometheus Minimal Ingestion Profile

This README explains how to use the **minimal ingestion profile** in Prometheus with **Azure Monitor** to reduce the amount of data collected from your Kubernetes cluster. The minimal ingestion profile collects only essential metrics, which helps lower storage costs while ensuring key metrics are available for monitoring and alerts.

For more detailed information, please refer to the official documentation [here](https://learn.microsoft.com/en-us/azure/azure-monitor/containers/prometheus-metrics-scrape-configuration-minimal).

---

## What is the Minimal Ingestion Profile?

The **minimal ingestion profile** limits Prometheus to collect only the most critical metrics from your Kubernetes cluster. This option is useful for reducing the amount of data ingested into Azure Monitor, which can help you save on storage costs.

It focuses on collecting the most essential metrics necessary for basic monitoring, dashboards, and alerts, without including unnecessary or detailed metrics.

---

## Metrics Collected in Minimal Ingestion

When the minimal ingestion profile is enabled, only important metrics like the following are collected:
- **Control plane metrics**: Metrics from key components like `kube-apiserver` and `etcd`.
- **Node and pod metrics**: Critical performance data such as CPU and memory usage.

Less important metrics, such as detailed container metrics, are excluded unless explicitly enabled.

---

## Enabling the Minimal Ingestion Profile

To enable the minimal ingestion profile, you need to configure the **ConfigMap** file in your Kubernetes cluster. The key setting is `minimalIngestionProfile = true`, which ensures that only the minimal set of metrics is scraped by Prometheus.

---

## Cost Savings

By reducing the amount of data collected, the minimal ingestion profile helps you save on storage costs in **Azure Monitor**. It limits the data to only what’s essential for monitoring and alerting, avoiding unnecessary data collection and storage.

---

## Customizing the Minimal Ingestion Profile

If you need a few additional metrics beyond the minimal set, you can modify the **ConfigMap** file to specify which extra metrics to include. You can also disable the minimal profile by setting `minimalIngestionProfile = false` to return to full data collection.

---

## Use Cases

The minimal ingestion profile is ideal for:
- **Cost optimization**: When you need basic monitoring but want to save on storage costs.
- **Test or development environments**: Where detailed metrics are not required.
- **Basic monitoring setups**: Where only key metrics for dashboards and alerts are needed.

---

## Summary

The **minimal ingestion profile** helps reduce the amount of metrics data collected by Prometheus, ensuring that only essential metrics are ingested. This setup is perfect for reducing costs while still maintaining critical monitoring and alerting capabilities.

For more detailed information, check out the official documentation [here](https://learn.microsoft.com/en-us/azure/azure-monitor/containers/prometheus-metrics-scrape-configuration-minimal).
