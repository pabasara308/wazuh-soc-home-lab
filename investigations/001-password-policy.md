# Investigation 001 – Weak Minimum Password Length Policy

## 1. Investigation Summary

**SIEM:** Wazuh  
**Endpoint:** Windows 11 Home  
**Agent:** myproject  
**SCA Check ID:** 26003  
**Alert Rule ID:** 19004  
**Final Status:** Resolved

## 2. Security Finding

Wazuh Security Configuration Assessment identified a weak minimum password length policy.

The CIS Windows 11 Enterprise Benchmark requires a minimum password length of 14 characters.

The Windows endpoint was configured with a minimum password length of 0 characters.

## 3. Investigation

The configuration was verified using PowerShell:

`net accounts`

The output confirmed:

**Minimum password length: 0**

## 4. Remediation

The following command was executed in an elevated PowerShell session:

`net accounts /minpwlen:14`

The password policy was updated successfully.

## 5. Verification

The `net accounts` command confirmed the new minimum password length of 14 characters.

A subsequent Wazuh SCA scan showed that Check ID 26003 changed from **Failed** to **Passed**.

## 6. Before and After Results

| Metric | Before | After |
|---|---:|---:|
| Minimum password length | 0 | 14 |
| SCA passed checks | 126 | 127 |
| SCA failed checks | 261 | 260 |
| Not applicable checks | 8 | 8 |
| Displayed SCA score | 32% | 32% |

## 7. Lessons Learned

- Identifying security configuration weaknesses using Wazuh SCA.
- Verifying Windows password policies using PowerShell.
- Applying security configuration remediation.
- Confirming improvements through a new Wazuh scan.
- Documenting security findings and remediation evidence.

## 8. Limitations

The endpoint uses Windows 11 Home, while the assessment uses a Windows 11 Enterprise benchmark. Other benchmark findings require individual applicability checks.

## 9. Conclusion

The weak minimum password length policy was successfully remediated and verified through Wazuh SCA.

**Investigation Status: Closed – Resolved**
