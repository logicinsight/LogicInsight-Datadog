# README: Logic Insight Public Datadog Dashboards

## Overview  
The **Logic Insight Public Datadog Dashboards** are designed to provide comprehensive monitoring and visualization for Logic Insight LogicApp. These dashboards deliver near real-time insights into performance, usage, and error metrics, enabling users to efficiently manage and troubleshoot their Nutanix workflows.  

![Host_Overview](https://github.com/user-attachments/assets/db88bd26-10e8-493c-92a2-0bcf45464eff)
![Monitors](https://github.com/user-attachments/assets/1505c12e-5cc7-40d4-bac3-9748ea42b0fd)
![Physical_Disk_Overview](https://github.com/user-attachments/assets/61d3705c-b860-4bd9-9d42-aa0becfb8f76)
![Protection_Domain_Overview](https://github.com/user-attachments/assets/8434a98e-de32-41bc-bbc4-1822017235fd)
![VM_Disk_Overview](https://github.com/user-attachments/assets/834daef8-7b9e-4cd0-976e-f9f870328ef0)
![VM_Inventory](https://github.com/user-attachments/assets/7b71d11b-5388-4c3a-8d70-2bbfc77098a0)
![VM_Single_View](https://github.com/user-attachments/assets/cef76a1c-f277-4b6a-9a00-baf550d1baec)
![Cluster_Overview](https://github.com/user-attachments/assets/137bf619-ae72-4b4d-9d29-6cdfb24bca09)


## Key Features
- **Optimization Insights** Forecasting, resiliency planning, and advanced analytics.
- **Error Monitoring**: Tracks and highlights issues, errors, and failure trends.  
- **Performance Metrics**: Visualizes performance, run latency, and throughput for Nutanix operations.  
- **Usage Insights**: Displays metrics like total resillency, data protection, user actions, and much more!  
- **Alert Integration**: Easily set up alerts for critical metrics directly within Datadog.  

## Prerequisites  
Before using these dashboards, ensure the following are in place:  
1. **Logic Insight LogicApp Deployed**: A functional Logic App in your environment.  
2. **Datadog Account**: An active Datadog account with proper permissions to create and view dashboards.  

## Setup Instructions  

1. **Logic Insight LogicApp **  
   - Navigate to logicinsight.io > Contact Us > Demo.  
   - Configure your virtual appliance.  

2. **Import Dashboards**  
   - Upload all dashboards and monitors directly from LogicApp or manually from this repo.  
   - In Datadog, navigate to **Dashboards > Dashboards**.   

3. **Set Up Alerts (Optional)**  
   - In Datadog, go to **Monitors**.  
   - Create alerts for critical metrics, such as failed runs or high execution latency.  

## Dashboard Components  

### VM Insights

### Forcasting
Capacity forecasting is a cornerstone of effective Nutanix monitoring. Predictive analytics help administrators plan for future demands by analyzing historical trends.  
- **Capacity Utilization Trends**: Anticipate when resources will reach thresholds.  
- **"What-If" Scenarios**: Model the impact of adding workloads or nodes.  
- **Scaling Recommendations**: Suggest hardware or configuration changes to accommodate growth.  

## Resiliency Planning
Resiliency monitoring ensures the infrastructure remains operational even during failures. Tools can assess and enhance resiliency by:  
- **Replication and Snapshot Monitoring**: Track replication statuses and backup integrity.  
- **Disaster Recovery Readiness**: Ensure failover configurations are functioning correctly.  
- **Failure Simulations**: Run "chaos tests" to evaluate system recovery under stress.  

### Metrics  
Nutanix systems generate extensive telemetry data, enabling real-time insights into CPU, memory, storage, and network utilization. Monitoring tools can provide:  
- **Cluster Health Dashboards**: Display overall system status, resource utilization, and alerts.  
- **Node and VM Performance Metrics**: Identify bottlenecks and underutilized resources.  
- **IOPS and Latency Insights**: Ensure applications are meeting performance SLAs.  

### Logs  
- **Error Logs**: Logs for failed runs, including error codes and descriptions.  
- **Performance Logs**: Detailed logs of execution times and trigger latencies.  

### Alerts and Events  
- **Failure Alerts**: Notifications for failed runs or error thresholds.  
- **Performance Alerts**: Notifications for high latency or throughput issues.  

## Maintenance  
- Regularly update the dashboards to include new metrics or workflows as Logic Apps evolve.  
- Periodically review alert thresholds to align with changing workload patterns.  

## Support  
For questions, issues, or feature requests, please open an issue in the repository or contact the support team at [support@logicinsight.io].  

## License  
This project is licensed under the MIT License. See the LICENSE file for details.  
