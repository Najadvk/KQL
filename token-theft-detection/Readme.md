# Suspicious Token Usage Detection – Entra ID (KQL)

This query detects suspicious OAuth token activity by legitimate Microsoft apps like Visual Studio Code and the Microsoft Authentication Broker. These apps are often implicitly trusted and may be exploited post-compromise using stolen refresh tokens.

##  Why This Matters

Attackers can bypass MFA and Conditional Access policies using refresh tokens with trusted apps, evading detection and accessing sensitive resources like Microsoft Graph or device registration.

## Detection Logic

- Filters only successful sign-ins (`ResultType == 0`)
- Focuses on member accounts (`UserType == "Member"`)
- Flags unusual usage of:
  - Device Registration Service via the Authentication Broker (`adrs_access`)
  - Microsoft Graph access via VS Code

##  Use Case

Use this query in Microsoft Sentinel or Entra ID workbooks to monitor for token misuse patterns that may indicate lateral movement, persistence, or stealthy exfiltration.

