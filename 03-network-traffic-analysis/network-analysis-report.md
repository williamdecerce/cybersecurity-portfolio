# Network Traffic Analysis Report

## 1. Overview

This project simulates a SOC investigation of suspicious network traffic.

The objective was to analyze network connections, identify anomalous behavior, extract Indicators of Compromise (IoCs), and assess the potential security risk.

## 2. Traffic Analysis

The analysis identified five SSH connections originating from the same internal host:

Source IP: 192.168.1.25

All five connections targeted:

Destination IP: 185.23.45.10
Destination Port: 22
Protocol: SSH

The connections occurred between 09:30:05 and 09:30:09, resulting in five consecutive SSH connections within approximately five seconds.

## 3. Suspicious Indicators

- Five consecutive SSH connections.
- All connections originated from the same source IP.
- All connections targeted the same external IP address.
- All connections used TCP port 22.
- The connections occurred at approximately one-second intervals.

This pattern is suspicious and may be consistent with automated connection attempts.

However, the available traffic data alone is not sufficient to confirm that an attack or compromise occurred.

## 4. Indicators of Compromise

| Type | Value |
|---|---|
| Source IP | `192.168.1.25` |
| Destination IP | `185.23.45.10` |
| Destination Port | `22` |
| Protocol | `SSH` |
| Connection Count | `5` |
| Time Range | `09:30:05 - 09:30:09` |

## 5. Severity Assessment

Severity: Medium

The activity is considered suspicious because multiple SSH connections were established rapidly between the same source and destination.

Additional investigation would be required to determine whether the connections were legitimate administrative activity or potentially malicious.

## 6. Recommended Response

1. Investigate the source host `192.168.1.25`.
2. Determine whether the SSH connections were authorized.
3. Review authentication logs for the destination system.
4. Check for successful or failed SSH authentication attempts.
5. Investigate the destination IP `185.23.45.10`.
6. Review additional network traffic for related activity.
7. Monitor for repeated connections from the same source.

## 7. Conclusion

The investigation identified a suspicious pattern of repeated SSH connections between the same source and destination.

The activity may indicate automated connection attempts, but additional authentication and system logs would be required to determine whether malicious activity occurred.

This project demonstrates basic network traffic analysis, identification of suspicious connection patterns, IoC extraction, and SOC-style incident assessment.

Project type: Personal cybersecurity laboratory / simulated network investigation.
