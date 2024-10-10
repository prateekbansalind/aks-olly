# Prometheus Metrics Scraping for Azure Kubernetes Service (AKS)

This README provides an overview of how **Prometheus metrics scraping** works when using **Azure Monitor** to collect metrics from AKS clusters. It explains the default configuration, how metrics are collected, and the options available to customize the process.

For more detailed information, please refer to the official documentation [here](https://learn.microsoft.com/en-us/azure/azure-monitor/containers/prometheus-metrics-scrape-default).

---

## What are Prometheus Metrics?

**Prometheus metrics** are collected from various parts of your AKS cluster, such as containers, pods, and nodes. These metrics provide valuable insights into resource usage like CPU, memory, and network activity.

The **default configuration** in Azure Monitor's managed Prometheus service automatically scrapes key metrics without complex setup, making it easy to start monitoring your cluster.

---

## Default Metrics Scraping

By default, **Azure Managed Prometheus** scrapes the following types of metrics:
- **Container metrics**: Information about each container’s CPU and memory usage.
- **Node metrics**: Data about each node (machine) in the cluster.
- **Kubernetes object metrics**: Metrics for Kubernetes resources like pods, services, and deployments.

These metrics are automatically collected and stored in **Azure Monitor**, where they can be analyzed using **Azure Monitor** or **Grafana**.

---

## Configuration Options

You can adjust **Prometheus** scraping behavior by modifying the **ConfigMap** file in your Kubernetes cluster. Customizations include:
- **Adding new metrics**: Scrape custom metrics from your applications or other resources.
- **Filtering metrics**: Exclude unnecessary metrics to reduce data collection and costs.

---

## How Metrics Are Collected

Prometheus scrapes metrics at regular intervals (e.g., every 30 seconds) from specific **endpoints** in your cluster. The default configuration already knows where to find these metrics, but you can change the settings in the **ConfigMap** if needed.

---

## Prometheus ConfigMap

The **ConfigMap** file controls which metrics Prometheus collects. By default, it scrapes the most commonly used metrics. You can edit this file to:
- Add custom metrics from your applications.
- Change the scraping intervals or remove unused metrics.

---

## Viewing Metrics

Once collected, you can view and analyze these metrics using:
- **Azure Monitor**: For real-time insights and custom dashboards.
- **Grafana**: For customizable operational dashboards and alerts.

---

## Best Practices

- **Optimize metrics collection**: Only collect the metrics you really need to avoid unnecessary storage and costs.
- **Adjust scraping intervals**: Set different scraping frequencies for different types of metrics, depending on their importance.

---

## Summary

The **default Prometheus configuration** in Azure Monitor simplifies metrics collection for AKS clusters. You can customize the setup as needed by modifying the **ConfigMap**. Metrics are visualized using tools like **Azure Monitor** and **Grafana**.

For more information, check out the official documentation [here](https://learn.microsoft.com/en-us/azure/azure-monitor/containers/prometheus-metrics-scrape-default).
