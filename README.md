# README: Logic Insight Public Datadog Dashboards

## Overview  
The **Logic Insight Public Datadog Dashboards** are designed to provide comprehensive monitoring and visualization for Logic Insight LogicApp. These dashboards deliver near real-time insights into performance, usage, and error metrics, enabling users to efficiently manage and troubleshoot their Nutanix workflows.  

## Key Features  
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

### Metrics  
- **Runs Overview**: Total runs, successful runs, failed runs.  
- **Execution Time**: Average and max execution time.  
- **Trigger Metrics**: Counts and success rates for triggers.  

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
