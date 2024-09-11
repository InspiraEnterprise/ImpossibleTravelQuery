# Impossible-Travel-Custom-Query
ANALYZING ANOMALOUS SIGN-IN ACTIVITIES  WITH KUSTO QUERY LANGUAGE (KQL)

# Description
Impossible Travel Kusto Query Language (KQL) script is designed to analyze sign-in logs to detect potential anomalous activity by calculating the speed of travel between login locations. It filters out logs at excessively high speeds, which may indicate suspicious behavior.

# Business Requirements
•	Identify Potential Compromises: Detect anomalous user sign-ins that may indicate an account compromise, such as logins from geographically distant locations within an unfeasibly short time frame.

•	Enhance Incident Response: Provide security teams with actionable insights to quickly investigate and respond to potential threats. Detecting impossible travel can help in initiating prompt investigations into compromised accounts.

•	Mitigate Insider and External Threats: Protect against both internal (e.g., account misuse) and external threats (e.g., credential theft) by flagging suspicious activities that could indicate unauthorized access to corporate resources.

# Prerequisites
•	An active Azure subscription

•	Sentinel Contributor RBAC role assigned to a resource group

•	An active Sentinel workspace

•	A Log Analytics workspace linked to Sentinel

•	Azure Active Directory (Azure AD) Sign-In Logs.

•	Adequate log retention policies must be in place to store sign-in data for a period sufficient to perform meaningful analysis.

•	Determine appropriate threshold values for travel distance (in kilometers) and timeframe (in hours) based on the organization’s risk tolerance and normal user behavior.

# MITRE ATT&CK

The following are the MITRE ATT&CK tactics and techniques associated with the analytical rule:

Initial Access

•	T1078 - Valid Accounts

If an account is used from multiple geographically distant locations in a short period, it may indicate that an adversary has obtained valid credentials and is using them from a different location.

Command and Control 

•	T1071 - Application Layer Protocol

Adversaries might use remote access tools that leverage common application layer protocols to hide their activities, which could be indicated by logins from unusual locations.

Defense Evasion 

•	T1036 – Masquerading

An adversary might use techniques to make their activity appear normal, such as using VPNs or proxies to mimic legitimate user access patterns, which could involve impossible travel scenarios.

# Query Scheduling
•	Query Frequency: - Run query every 6 hours 

•	Query Lookup data: - Lookup data from the last 24 hours.



