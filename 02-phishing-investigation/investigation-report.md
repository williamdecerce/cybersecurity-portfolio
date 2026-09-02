# Phishing Investigation Report

## 1. Overview

This project simulates a SOC investigation of a suspicious phishing email.

The objective was to identify phishing indicators, extract relevant Indicators of Compromise (IoCs), assess the risk, and recommend appropriate security actions.

## 2. Email Analysis

### Sender

support@micros0ft-security.com

The sender domain appears designed to impersonate Microsoft. The use of "micros0ft" with a zero instead of the letter "o" is a suspicious domain characteristic.

### Subject

Urgent: Your account will be suspended

The subject creates a sense of urgency and attempts to pressure the recipient into taking immediate action.

### Suspicious Link

http://micros0ft-security.com/verify

The link points to the same suspicious domain and requests that the user verify their identity.

The use of HTTP instead of HTTPS is another security concern.

## 3. Phishing Indicators

- Suspicious sender domain
- Typosquatting: "micros0ft" instead of "microsoft"
- Urgent account suspension threat
- Request to verify identity
- Suspicious external link
- Attempt to impersonate Microsoft

## 4. Indicators of Compromise

| Type | Value |
|---|---|
| Sender | support@micros0ft-security.com |
| Domain | micros0ft-security.com |
| URL | http://micros0ft-security.com/verify |

## 5. Severity Assessment

Severity: High

The email has multiple characteristics associated with phishing and impersonation attacks.

The combination of a deceptive domain, urgency, identity verification request, and suspicious link creates a significant risk of credential theft.

## 6. Recommended Response

1. Do not click the link.
2. Do not provide credentials or personal information.
3. Report the email to the security team.
4. Block or investigate the suspicious domain.
5. Search email logs for other recipients of the same message.
6. If a user already entered credentials, reset the password immediately and investigate the account.
7. Enable or verify multi-factor authentication.

## 7. Conclusion

The analyzed email is highly suspicious and should be treated as a phishing attempt.

The investigation demonstrates basic phishing analysis, identification of suspicious domains and links, IoC extraction, risk assessment, and incident response recommendations.

Project type: Personal cybersecurity laboratory / simulated phishing investigation.


