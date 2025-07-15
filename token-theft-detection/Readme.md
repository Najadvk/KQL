# KQL Queries for Security Monitoring

Welcome to the repository of Kusto Query Language (KQL) scripts designed for detecting and investigating security incidents in Microsoft Entra ID (Azure AD) and related Microsoft 365 environments.

---

## About

This repo contains curated KQL queries that help security analysts and incident responders detect suspicious activities such as token theft, unauthorized OAuth usage, and other identity-related threats.


---

## Current Queries

### Suspicious Token Usage Detection

Detects suspicious OAuth token usage by trusted first-party applications like the Microsoft Authentication Broker and Visual Studio Code.

- Identifies use of refresh tokens with unusual scopes.
- Focuses on successful sign-ins by member accounts.
- Flags potentially malicious token abuse that could indicate lateral movement or persistence.

> See [`Suspicious_Token_Usage_Detection.md`](./Suspicious_Token_Usage_Detection.md) for the full query and explanation.

---

