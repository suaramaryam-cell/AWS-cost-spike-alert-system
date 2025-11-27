# AWS-cost-spike-alert-system
A system that detects AWS cost anomalies,sends alerts and auto stops non production resources.

Automated monitoring system that detects AWS cost anomalies,sends alerts and AUTOMATICALLY STOPS non production resources.

## Problem Statement

Startups and cloud teams often wake up to unexpected AWS bills. By the time CloudWatch billing alerts trigger, the damage is already done. This system provides proactive monitoring with hourly checks and AUTOMATICALLY STOPS non production resources.

## Features

- **Real time Monitoring**: Checks AWS costs every hour via Cost Explorer API
- **Anomaly Detection**: Compares current spending against 7-day historical average
- **Smart Alerts**: Triggers notifications when costs spike above configurable threshold (default: 20%)
- **Service Breakdown**: Identifies which AWS services are driving cost increases
- **Actionable Insights**: Provides specific recommendations based on cost patterns
- **Historical Tracking**: Stores cost data in DynamoDB for trend analysis
- **Auto stop**: stops non production resources

## Architecture

Cost Explorer API → EventBridge (hourly) → Lambda (Python)
↓
DynamoDB (history)
↓
Analysis Logic
↓
SNS → Email Alerts

<img width="1366" height="768" alt="IMG_3340" src="https://github.com/user-attachments/assets/2fa99cd5-32ac-463a-a053-828611e12f23" />
<img width="1366" height="768" alt="IMG_3339" src="https://github.com/user-attachments/assets/1d2e2ee8-b4db-4f69-a48d-3f788cea20e6" />

## Components

- **Lambda Function**: Python-based cost analysis and alerting logic
- **EventBridge**: Scheduled trigger (runs every hour)
- **DynamoDB**: Historical cost data storage with TTL
- **SNS**: Email notification delivery
- **IAM**: Least-privilege security policies
- **Cost Explorer API**: Real-time cost data retrieval

## Future Enhancements

  •	Detailed cost attribution by tags/projects
	•	Weekly/monthly cost summary reports

 ## Author
 
Maryam Suara
	•	LinkedIn: 
  
Contributing
Contributions welcome! Please open an issue or submit a pull request.
Built to solve real AWS cost management challenges for startups and cloud teams.
