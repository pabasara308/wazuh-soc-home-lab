# wazuh-soc-home-lab
Hands-on SOC lab using Wazuh SIEM for Windows endpoint monitoring, security assessment, and remediation.

# Wazuh SOC Home Lab

## Overview
Hands-on SOC lab using Wazuh SIEM to monitor Windows endpoints, analyze security events, and investigate security configuration findings.

## Lab Environment
- SIEM: Wazuh
- Server: Ubuntu Linux VM
- Endpoint: Windows 11 Home
- Virtualization: VMware Workstation
- Agent: myproject

## Project Objectives
- Deploy and connect a Windows endpoint to Wazuh.
- Monitor and analyze Windows security events.
- Identify security misconfigurations using Wazuh SCA.
- Apply remediation and verify the results.

## Investigation 001: Minimum Password Length
- Wazuh SCA Check ID: 26003
- Initial result: Failed
- Initial minimum password length: 0
- Remediation: Set minimum password length to 14 characters.
- Final result: Passed (verified in Wazuh).

## SCA Results
| Metric | Before | After |
|---|---:|---:|
| Passed | 126 | 127 |
| Failed | 261 | 260 |
| Not applicable | 8 | 8 |

## Skills Demonstrated
- SIEM monitoring
- Windows endpoint security
- Security Configuration Assessment
- Security investigation and remediation
- Verification and documentation

## Note
The endpoint uses Windows 11 Home, while the assessment policy is based on the Windows 11 Enterprise benchmark. Findings require applicability review.
