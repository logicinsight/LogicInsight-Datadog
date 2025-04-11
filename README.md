# Summary  

The **Logic Insight Appliance** is the next-generation **Nutanix monitoring platform**, designed to provide **deep visibility, near-time analytics, and proactive insights** into Nutanix environments. It offers **advanced metrics collection, improved anomaly detection, and intelligent alerting** to optimize infrastructure performance and ensure operational efficiency.  

Seamlessly integrating with **Nutanix Prism Central** and **Prism Element**, Logic Insight enhances observability by gathering **granular system data** across compute, storage, and networking layers. Powered by **Datadog’s AI-driven analytics engine**, it enables IT teams to **predict potential failures, optimize workloads, and automate issue resolution** before business operations are affected.  

With a focus on **scalability, security, and efficiency**, the **Logic Insight Appliance** empowers organizations to **maximize the value of their Nutanix deployments** through data-driven insights and predictive intelligence.  

## Prerequisites  

This solution has the minimum following **requirements**:  

- **Nutanix Prism AOS** (AOS 6.5+)  
- **Nutanix Prism Central** (2024.+)  
- **Logic App** subnet needs access to **Prism Central** and **Prism Element** on port **9440** (See diagram below)
- **DataDog** is required for this integration to work.
    - **Required** DataDog Api Key.
    - **Optional** DataDog Integration Key.
        - The Integration Key is used for automatic deployments of dashboards and monitors.
- **Dedicated User** for Prism Element is recommended.
    - While not required, a dedicated user for **LogicApp** is recommended.
- **Optional** Dedicated user for IPMI Monitoring.
    - While not required, a dedicated user for **LogicApp** is recommended when monitoring IPMI hardware data.

## Minimun Requirements

| CPU | vCPU | RAM | Disk |
|-----|------|-----|------|
|  4  |  1   | 8GB | 50GB |


## Logic Insight Appliance Port Breakdown  

| Port(s) | Protocol | Source | Destination | Service | Description |
|---------|----------|----------------|----------------|----------------|--------------------------------------------|
| 443     | TCP      | LogicApp       | Pulsehub Logic Insight | License | License verification |
| 9440    | TCP      | LogicApp       | Nutanix Prism Central | Prism Central Wizard | TCP communication with Prism Central to add Prism Element Clusters |
| 9440    | TCP      | LogicApp       | Nutanix Prism Element | Nutanix Prism Element Collector | SSL communication between LogicApp and Prism Element APIs |
| 443     | TCP      | LogicApp       | Datadog | Datadog Communication | SSL communication between LogicApp and Datadog Data Ingestion API |
| 443     | TCP      | LogicApp       | AWS | Update Server | Default port where LogicApp retrieves updates. [Update Server](https://logicappupdate.s3.us-east-1.amazonaws.com) |

## Deployment Steps

### 👨‍🚀 Initial Deployment

There are two ways to deploy **LogicApp** to Nutanix:
- **Prism Element**
- **Prism Central**

There are also two ways to upload the LogicApp qcow to **Prism Element** or **Prism Central**

- Upload Image through the image service on **Prism Element** or **Prism Central**
- Upload through a local file that was downloaded to a local computer.

LogicApp can be downloaded from AWS directly [download link](https://logicappupdate.s3.us-east-1.amazonaws.com/LogicAPP/latest.qcow2).

---

## ⚙️ Initial Configuration – LogicInsight Appliance

Follow these steps to deploy the **LogicInsight Appliance** on your Nutanix environment:

---

### 1. 🖥️ Create the VM  
- Deploy on either **Prism Central** or **Prism Element**.

---

### 2. 🏷️ Name the VM  
- Suggested name: **LogicInsight Appliance**  
- (You may use your organization’s naming convention.)

---

### 3. 📝 Add a Description  
- Recommended:  
  ```
  LogicInsight Nutanix Monitoring Appliance
  ```

---

### 4. 🌐 Set the Timezone  
- Use **UTC** (recommended) or your local cluster time.

---

### 5. 🧠 Resource Requirements  
- **Minimum CPU:** 4 vCPUs  
- **Cores per vCPU:** At least 1  
- **Minimum RAM:** 4 GB

---

### 6. 💾 Boot Configuration  
- Set to **Legacy BIOS**

---

### 7. 📀 Remove CD-ROM  
- Detach the CD-ROM device from the VM.

---

### 8. 📦 Add a New Disk  
- Clone from **Image Service**  
- Select the LogicInsight appliance image (downloaded or uploaded previously)

---

### 9. 🌐 Add a Network Adapter  
> ℹ️ The appliance can be on any subnet, as long as it can reach:  
> - **Prism Central** and **Prism Element** on **port 9440**  
> - *(Optional)* IPMI systems via **port 443**

---

### 10. 🔋 Save & Power On  
- Finalize configuration and power on the virtual machine.

## 🚀 LogicApp Appliance Deployment Guide

### 1. 🖥️ Open Console  
Access the console of the newly deployed **LogicApp Appliance**.

---

### 2. 🌐 Network Configuration  
- If **DHCP** is enabled, the appliance will boot directly to the login screen.  
- If **DHCP is disabled**, expect a **2-minute timeout** before login appears.

---

### 3. 🔐 Login  
Login to the appliance with the following credentials:  
- **Username:** `logicapp`  
- **Password:** `Support/4u`

---

### 4. ⚙️ First-Time Setup  
Follow the interactive prompts to configure **network settings** and complete the **initial setup**.

---

### 5. 🌍 Web UI Access  
- Use a browser with access to the appliance’s subnet.  
- Navigate to:  
  ```
  https://<ip-address/hostname>
  ```  
- **Login credentials:**  
  - **Username:** `admin`  
  - **Password:** `Support4u`  
- Enter a valid **license key**.  
  > ℹ️ License keys can be obtained by contacting [LogicApp Support](https://logicinsight.io).

---

### 6. ➕ Adding Nutanix Clusters  
To integrate Nutanix clusters with LogicApp for **DataDog monitoring**, choose one of the following:

#### • Prism Central (Recommended for multiple clusters)  
> ℹ️ Best suited for environments with multiple clusters.

#### • Prism Element (Recommended for single clusters)  
> ℹ️ Ideal for monitoring individual clusters.

- Follow on-screen prompts to complete the cluster setup.  
- Look for ✅ **green checkmarks** for:
  - DataDog
  - License
  - Subscription

---

### 7. 📊 Load Dashboards & Monitors  
In the top-right of the Web UI, click:  
**Deploy Dashboards/Monitors** to enable built-in observability.

---

### 8. 📈 View in DataDog  
You're all set!  
Access your new **dashboards and monitors** directly in **DataDog**.

---

Let me know if you want this styled for PDF, web docs, or converted to HTML/React!

## Dashboards Overview  
The **Logic Insight Public Datadog Dashboards** are designed to provide comprehensive monitoring and visualization for Logic Insight LogicApp. These dashboards deliver near-time insights into performance, usage, and error metrics, enabling users to efficiently manage and troubleshoot their Nutanix workflows. 

## Key Features
- **Optimization Insights** Forecasting, resiliency planning, and advanced analytics.
- **Error Monitoring**: Tracks and highlights issues, errors, and failure trends.  
- **Performance Metrics**: Visualizes performance, run latency, and throughput for Nutanix operations.  
- **Usage Insights**: Displays metrics like total resillency, data protection, user actions, and much more!  
- **Alert Integration**: Easily set up alerts for critical metrics directly within Datadog.  

## Prerequisites  
Before using these dashboards, ensure the following are in place:  
1. **Logic Insight LogicApp Deployed**: A functional Logic App Appliance in your environment.  
2. **Datadog Account**: An active Datadog account with proper permissions to create and view dashboards.  


Here's a cleaner and more polished version of your markdown, formatted for readability, clarity, and professional presentation:

---

## 📊 Dashboard Components

### 🔍 VM Insights  
Near-real-time performance metrics you can count on — ideal for post-incident diagnostics and day-to-day monitoring.

**Key Features:**
1. **Monitor the Basics**  
   Track CPU, memory, disk, and network usage per VM in near real-time.

2. **Storage I/O Tracking**  
   Analyze read/write throughput, latency, and disk queue depth.

3. **Network Traffic Analysis**  
   Monitor ingress/egress traffic, dropped packets, and VM-to-VM communications.

4. **Heartbeat & Availability**  
   Ensure each VM is online, healthy, and responsive over time.

5. **Alert Integration**  
   Trigger alerts for CPU spikes, memory leaks, or service failures.

6. **Tag-Based Filtering**  
   Group insights by app, owner, environment, or workload tags.

7. **Historical Trend Analysis**  
   View long-term trends to support capacity planning and optimization.

---

### 📈 Forecasting  
Capacity forecasting is vital for Nutanix monitoring. Predictive analytics help plan for future demands by analyzing historical data.

- **Capacity Utilization Trends**  
  Anticipate when resources will reach defined thresholds.

- **What-If Scenarios**  
  Model the impact of adding new workloads or nodes.

- **Scaling Recommendations**  
  Suggest hardware or configuration changes based on usage projections.

---

## 🛡️ Resiliency Planning  
Ensure infrastructure remains operational during failures with proactive resiliency monitoring.

- **Replication & Snapshot Monitoring**  
  Track replication status and backup integrity.

- **Disaster Recovery Readiness**  
  Verify failover configurations are working as expected.

- **Failure Simulations**  
  Run “chaos tests” to evaluate system behavior under stress.

---

### 📊 Metrics  
Nutanix provides real-time telemetry for performance insight across compute, storage, and network.

- **Cluster Health Dashboards**  
  Visualize system health, utilization, and alert states.

- **Node & VM Performance**  
  Detect bottlenecks and underused resources at a glance.

- **IOPS & Latency**  
  Ensure applications meet performance SLAs.

---

### 📂 Logs  
Detailed logs for troubleshooting and performance analysis.

- **Error Logs**  
  Capture failed runs with error codes and messages.

- **Performance Logs**  
  Record execution durations and trigger latencies.

---

### 🚨 Alerts & Events  
Real-time alerts to detect issues before they escalate.

- **Failure Alerts**  
  Notify on job failures or system errors.

- **Performance Alerts**  
  Triggered by latency, IOPS drops, or threshold breaches.

---

## 🛠️ Maintenance

- Update dashboards regularly to include new metrics or workflows as **LogicApp** evolves.
- Review and adjust alert thresholds periodically to match changing workloads.

---

## 🛟 Support  
For questions, issues, or feature requests, please open an issue in the repository or contact the support team. 

[Click here to email support](mailto:support@logicinsight.io?subject=Help%20with%20logic%20app)