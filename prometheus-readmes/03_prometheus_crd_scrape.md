# Customizing Prometheus Metrics Collection Using CRDs

This README provides an overview of how to use **Custom Resource Definitions (CRDs)** to configure **Prometheus metrics scraping** in **Azure Monitor**. It explains how to customize metrics collection for pods and services using Kubernetes-native configurations.

For more detailed information, please refer to the official documentation [here](https://learn.microsoft.com/en-us/azure/azure-monitor/containers/prometheus-metrics-scrape-crd).

---

## What are CRDs?

**Custom Resource Definitions (CRDs)** allow you to extend Kubernetes by creating custom resources that can be used to control and manage various applications. In the context of Prometheus, CRDs are used to configure **metrics scraping** for specific resources like pods and services.

---

## Pod and Service Monitors

- **PodMonitor**: Used to scrape metrics from individual pods. It defines the endpoints and intervals for scraping metrics.
- **ServiceMonitor**: Used to scrape metrics from services in your Kubernetes cluster. Similar to PodMonitor, it allows customization of scraping targets.

Both types of monitors allow you to:
- **Specify endpoints** for scraping.
- **Adjust scrape intervals** based on your needs.
- **Add labels** to categorize metrics.

---

## Using CRDs in Azure Monitor

**Azure Monitor** supports the use of **PodMonitor** and **ServiceMonitor** CRDs to manage Prometheus metrics scraping. By defining these resources in your cluster, you can:
- **Customize which metrics are collected**.
- **Control the scraping frequency**.
- **Target specific endpoints** for data collection.

---

## Key Customization Options

- **Scrape Intervals**: Define how often metrics should be scraped.
- **Endpoints**: Specify the URLs or services to scrape metrics from.
- **Labels**: Add labels to organize and filter metrics more easily.

---

## Applying CRDs

Once you’ve defined your **PodMonitor** or **ServiceMonitor**, apply them to your cluster using `kubectl`. Prometheus will automatically start collecting metrics based on the defined configuration.

---

## Best Practices

- **Limit the scope**: Use CRDs to focus on the pods and services that matter, avoiding unnecessary data collection.
- **Optimize intervals**: Set scrape intervals that balance real-time insights with storage and cost efficiency.

---

## Summary

Using **CRDs** such as **PodMonitor** and **ServiceMonitor** gives you fine-grained control over which metrics are collected from your Kubernetes clusters. This allows you to customize Prometheus scraping based on your needs, ensuring efficient and effective monitoring.

For more detailed instructions and examples, check the official documentation [here](https://learn.microsoft.com/en-us/azure/azure-monitor/containers/prometheus-metrics-scrape-crd).
