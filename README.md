# Microsoft Sentinel SIEM Implementation & Lessons Learned

## Overview
This project documents the implementation of a cloud-based Security Operations Centre (SOC) lab using Microsoft Sentinel. The objective is to simulate real-world monitoring and detection workflows within an Azure environment by ingesting logs, querying data, and exploring alerting capabilities.

## Objectives
- Deploy Microsoft Sentinel within Azure
- Configure a Log Analytics Workspace
- Enable and validate log ingestion from a virtual machine
- Use Kusto Query Language (KQL) to query and analyse logs
- Explore detection rules and alerting workflows

## Tools & Technologies
- Microsoft Sentinel
- Azure Portal
- Log Analytics Workspace
- Windows Virtual Machine
- Kusto Query Language (KQL)

## Implementation

### Initial Setup
- Deployed Microsoft Sentinel within Azure
- Created and configured a Log Analytics Workspace
- Provisioned a Windows VM to generate security logs

### Data Ingestion Attempt
- Attempted to connect VM logs to Sentinel via data connectors
- Configured initial settings for log collection

## Log Validation (KQL)

To verify whether logs were successfully ingested, the following KQL queries were executed:

	```kql
	Heartbeat
	| take 10```

	```kql
	SecurityEvent
	| take 10```

	```kql
	Event
	| take 10```

## Outcome

No results were returned from the queries, indicating that log ingestion was not successfully configured at this stage.

## Analysis

The lack of results suggests potential issues such as:
- Data connectors not fully configured
- Log Analytics agent not properly installed or connected
- The virtual machine not successfully sending logs to the workspace

### Key Learnings
- Log ingestion is critical for SIEM functionality and must be validated early
- Microsoft Sentinel relies on Log Analytics for all data visibility
- Misconfiguration of connectors or agents can silently prevent data flow
- Troubleshooting cloud SIEM setups requires a structured validation approach

### Next Steps
- Reconfigure data connectors and validate agent installation
- Successfully ingest logs into the Log Analytics Workspace
- Use KQL to query and analyse real log data
- Implement basic detection rules and alerting
- Simulate attack scenarios and investigate alerts

## Future Improvements
- Integrate additional data sources (e.g. Azure Activity Logs, Syslog)
- Develop custom detection rules
- Map findings to MITRE ATT&CK framework
- Build end-to-end SOC investigation workflows

## Project Context

This project is part of my ongoing effort to build hands-on experience in SOC operations and cloud-based threat detection using SIEM tools.
