# Azure AD Sign-In Correlation Query (KQL)

This Kusto Query Language (KQL) script helps analyze Azure AD sign-in events for a specific user and identify sequences of sign-ins that occurred within a short time window (less than 60 minutes apart). It is particularly useful for:

- Detecting potential account misuse or abnormal login patterns
- Correlating sign-ins by location and IP to identify rapid context switching
- Enhancing alert investigation during incident response

---

##  What It Does

- Filters sign-in logs for a single user (UPN)
- Ensures valid geolocation data is present (Country, City)
- Sorts and serializes logins to calculate time gaps between events
- Flags sign-ins that occur within a 60-minute window
- Includes current and previous location/IP metadata for context

---

##  Fields Used

- `Timestamp` – When the sign-in occurred
- `AccountDisplayName` – Name of the user
- `IPAddress`, `Country`, `City`, `State` – Location and origin details
- `ResourceDisplayName` – Target resource
- `Previous*` – Previous sign-in's geo and IP data
- `TimeGapMinutes` – Minutes between current and previous sign-in

---

##  How to Use

1. Replace `<USER_ID>` with email address of the user you want to investigate.
2. If you're using a custom log table, adjust `SignInLogs` to match your environment.
3. Run the query in **Microsoft Sentinel**, **Log Analytics**, or the **Microsoft 365 Defender Advanced Hunting** portal.

---

##  Example Use Cases

- Investigating suspicious login activity
- Tracing geo-location anomalies
- Correlating sign-ins before or after MFA prompts or alert triggers

---

---
