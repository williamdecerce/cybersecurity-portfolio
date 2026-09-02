# Incident Response / SOC Investigation Report

## 1. Overview

This project simulates a SOC investigation involving a suspected account compromise and malicious activity.

The objective was to reconstruct the incident timeline, identify Indicators of Compromise (IoCs), assess the severity, and define appropriate incident response actions.

## 2. Incident Timeline

| Time | Event |
|---|---|
| 09:45:01 | Failed login — `admin` |
| 09:45:03 | Failed login — `admin` |
| 09:45:05 | Failed login — `admin` |
| 09:45:07 | Successful login — `admin` |
| 09:45:12 | `whoami` executed |
| 09:45:18 | Payload requested from external IP |
| 09:45:25 | `/tmp/update.sh` created |
| 09:45:31 | Script permissions modified |
| 09:45:35 | `/tmp/update.sh` executed |
| 09:46:02 | Outbound connection to `185.23.45.10:443` |
| 09:46:15 | `backup-admin` account created |
| 09:46:30 | Successful login using `backup-admin` |

## 3. Investigation Findings

The investigation identified a sequence of events consistent with a possible successful account compromise.

The activity began with repeated failed authentication attempts against the `admin` account, followed by a successful login from the same IP address.

After authentication, commands were executed, a payload was requested, and a script named `/tmp/update.sh` was created and executed.

An outbound connection to `185.23.45.10:443` was subsequently observed.

A new account named `backup-admin` was also created and successfully used to authenticate from the same external IP address.

## 4. Indicators of Compromise

| Type | Value |
|---|---|
| Source IP | `185.23.45.10` |
| Compromised Account | `
