# Real-time intelligence monitoring

This assignment is to configure alerts in <a href="https://www.greynoise.io/ ">GreyNoise</a> and to monitor real-time intelligence for modern threats, focusing on both malicious and suspicious activity targeting the energy sector, and aligned with adversary groups like APT33 and Dragonfly, here are the tailored alerts. These alerts consider spoofable and non-spoofable threats across all IP ranges and regions and focus on MITRE ATT&CK techniques such as T1499 (Endpoint Denial of Service), T1078 (Valid Accounts), and T1595 (Active Scanning).

# Configure alerts in GreyNoise
These alerts offer comprehensive monitoring, allowing you to catch both obvious and stealthy threats related to energy-focused adversaries and techniques known to impact the sector.

## 1. Endpoint Denial of Service (T1499):

```
metadata.org:"COMPANY" classification:malicious spoofable:false technique_id:T1499

```
Purpose: Detect non-spoofable malicious traffic related to Endpoint Denial of Service attempts, which is a common energy sector attack.

```
metadata.org:"COMPANY" classification:malicious spoofable:true technique_id:T1499
```
Purpose: Capture spoofable DoS activity that may be disguised by attackers (APT33, Dragonfly) attempting to overwhelm endpoints.

## 2. Valid Accounts (T1078):
```
metadata.org:"COMPANY" classification:suspicious spoofable:false technique_id:T1078

```
Purpose: Identify suspicious, non-spoofable access attempts using valid accounts, which could be signs of lateral movement or unauthorized access.

```
metadata.org:"COMPANY" classification:suspicious spoofable:true technique_id:T1078

```
Purpose: Track spoofable access patterns that could indicate an adversary is attempting to evade detection or test valid credentials.

## 3. Active Scanning (T1595):

```
metadata.org:"COMPANY" classification:suspicious spoofable:false technique_id:T1595

```
Purpose: Monitor non-spoofable scanning activity that could be part of an early reconnaissance phase, indicating adversaries like APT33 are mapping your environment.

```
metadata.org:"COMPANY" classification:suspicious spoofable:true technique_id:T1595

```
Purpose: Flag spoofable reconnaissance attempts where attackers are testing network defenses or identifying targets.

## 4. General Energy Sector Targeting (APT33, Dragonfly):

```
classification:malicious spoofable:false metadata.tags:"energy" metadata.adversary:"APT33"

```
Purpose: Focus on known adversary behavior, specifically targeting the energy sector, and track their activity within your IP ranges.

```
classification:malicious spoofable:true metadata.tags:"energy" metadata.adversary:"Dragonfly"
```
Purpose: Capture spoofable activity associated with Dragonfly and similar groups who target critical infrastructure in the energy sector.

## 5. Suspicious Energy Sector Activity:
```
classification:suspicious spoofable:false metadata.tags:"energy"
```

Purpose: Broad alerting for suspicious but non-malicious traffic that could be relevant to energy sector attacks, enabling early detection.

```
classification:suspicious spoofable:true metadata.tags:"energy"
```
Purpose: Detect spoofable, suspicious activity where attackers might be probing defenses while mimicking benign traffic patterns.






