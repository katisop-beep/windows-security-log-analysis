# Windows Security Log Analysis

## Project Overview

This project demonstrates practical Windows security log analysis using Microsoft Windows Event Viewer. The objective was to investigate failed authentication attempts recorded in the Windows Security log and interpret the information contained within Event ID 4625.

During the investigation, multiple failed logon events were identified and analysed to determine the attempted account, authentication method, logon type, failure reason, source IP address, and originating process.

## Objectives

- Navigate and analyse Windows Security logs using Event Viewer.
- Filter security events using Windows Event IDs.
- Investigate failed authentication attempts using Event ID 4625.
- Interpret logon types and authentication packages.
- Identify the source of authentication attempts using IP address information.
- Analyse Windows authentication failure codes.
- Distinguish between local and network-based failed logon attempts.
- Document findings using screenshots and technical observations.

## Tools Used

- Microsoft Windows
- Windows Event Viewer
- Windows Security Logs
- Command Prompt
- `ipconfig`

## Security Event Investigated

### Event ID 4625 — An Account Failed to Log On

Windows Event ID 4625 records failed account logon attempts.

The Security log was filtered for Event ID `4625`, revealing multiple authentication failures that could then be examined individually.

The investigation included analysis of:

- Target user account
- Logon type
- Authentication package
- Failure reason
- Status and sub-status codes
- Source IP address
- Source port
- Process information

## Key Findings

Multiple Event ID 4625 records were identified during the investigation.

Examples included:

- Failed interactive/local authentication attempts using **Logon Type 2**.
- Failed network authentication attempts using **Logon Type 3**.
- Authentication using **NTLM** and **Negotiate**.
- Failure status `0xC000006D`, indicating unsuccessful authentication.
- Sub-status `0xC000006A`, associated with an incorrect password for the attempted account.
- A network logon failure associated with the source IP address `192.168.18.123`.
- A separate event associated with the loopback address `127.0.0.1`, indicating activity originating from the local computer.

## Initial Security Assessment

The investigation demonstrates why a single failed logon event should not automatically be classified as malicious activity.

Security analysts should examine the surrounding context, including the source address, account name, logon type, authentication method, timing, frequency, and related events before determining whether authentication failures represent normal user activity, a configuration issue, or potentially suspicious behaviour.

## Skills Demonstrated

- Windows Security Log Analysis
- Windows Event Viewer
- Event ID Investigation
- Authentication Analysis
- Failed Logon Investigation
- IP Address Analysis
- Windows Authentication
- Basic SOC Investigation
- Security Event Documentation
