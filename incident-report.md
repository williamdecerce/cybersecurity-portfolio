# Incident Report — Brute Force Authentication Analysis

## 1. Overview

This project simulates a Security Operations Center (SOC) investigation of suspicious authentication activity.

The objective was to analyze authentication logs, identify indicators of potentially malicious activity, assess the severity of the incident, and recommend appropriate response actions.

**Environment:** Simulated cybersecurity home lab
**Role:** Junior Security Analyst
**Tools:** Linux Terminal, grep, awk, sort, uniq

---

## 2. Incident Summary

A series of repeated failed authentication attempts was detected against the `admin` account.

The attempts originated from the same IP address:

**185.23.45.10**

Nine consecutive authentication failures occurred within approximately 18 seconds, followed by a successful login from the same IP address.

After the successful authentication, additional suspicious activity was observed, including commands and access to sensitive system files.

---

## 3. Timeline

| Time     | Event                      |
| -------- | -------------------------- |
| 09:12:03 | Failed login — `admin`     |
| 09:12:05 | Failed login — `admin`     |
| 09:12:07 | Failed login — `admin`     |
| 09:12:09 | Failed login — `admin`     |
| 09:12:11 | Failed login — `admin`     |
| 09:12:13 | Failed login — `admin`     |
| 09:12:15 | Failed login — `admin`     |
| 09:12:17 | Failed login — `admin`     |
| 09:12:19 | Failed login — `admin`     |
| 09:12:21 | Successful login — `admin` |
| 09:12:35 | `whoami` executed          |
| 09:12:42 | `/etc/passwd` accessed     |
| 09:13:01 | `/etc/shadow` accessed     |

---

## 4. Investigation Findings

The investigation identified several suspicious indicators:

* 9 consecutive failed authentication attempts.
* All attempts targeted the `admin` account.
* All attempts originated from the same IP address.
* The attempts occurred at a high frequency: approximately one attempt every two seconds.
* A successful authentication occurred immediately after the failed attempts.
* Post-authentication activity included system reconnaissance.
* Access to `/etc/shadow` was detected.

The frequency and repetition of the authentication attempts are consistent with potentially automated brute-force activity.

The successful login following the failed attempts significantly increases the risk of account compromise.

---

## 5. Indicators of Compromise

| Indicator              | Value                          |
| ---------------------- | ------------------------------ |
| Source IP              | `185.23.45.10`                 |
| Target Account         | `admin`                        |
| Authentication Pattern | 9 failures followed by success |
| Sensitive File         | `/etc/passwd`                  |
| Sensitive File         | `/etc/shadow`                  |
| Command                | `whoami`                       |

---

## 6. Severity Assessment

**Severity: Critical**

The severity was assessed as critical because the simulated incident combines repeated authentication failures, a subsequent successful authentication, and suspicious post-authentication activity involving sensitive system files.

The available evidence is consistent with a possible successful brute-force attack and subsequent account compromise.

However, additional evidence would be required to conclusively determine whether the account was actually compromised.

---

## 7. Recommended Response

A SOC analyst should consider the following actions:

1. Temporarily disable or lock the affected `admin` account.
2. Force a password reset.
3. Enable or verify multi-factor authentication.
4. Investigate the source IP address `185.23.45.10`.
5. Review additional authentication and system logs.
6. Check for persistence mechanisms or additional unauthorized activity.
7. Determine whether other accounts or systems were affected.
8. Preserve relevant logs for further investigation.
9. Monitor the environment for additional authentication attempts from the same source.

---

## 8. Conclusion

The investigation demonstrated how authentication logs can be used to identify suspicious login behavior.

The combination of repeated failed authentication attempts, a successful login from the same source, and suspicious activity after authentication represents a strong indicator requiring immediate investigation.

This project demonstrates practical experience with basic log analysis, Linux command-line tools, incident assessment, and SOC investigation methodology.

**Project type:** Personal cybersecurity laboratory / simulated incident


