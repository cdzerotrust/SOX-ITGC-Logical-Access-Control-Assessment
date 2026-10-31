# SOX ITGC Logical Access Control Assessment

### Simulated Technology Audit | Active Directory | PowerShell | GRC

**Project Author:** Christopher Davis, CISA
**Project Type:** Independent Cybersecurity & GRC Portfolio Project
**Control ID:** ITGC-01
**Assessment Period:** October 30–31, 2026
**Final Status:** Remediated — Retest Passed (Simulated)

---

## Project Overview

This project demonstrates a simulated Sarbanes-Oxley (SOX) IT General Controls assessment focused on logical access management.

Using an independent Microsoft Active Directory lab, I performed an access-control assessment for a fictional financial reporting application called **FinanceLedger**.

The objective was to determine whether actual Active Directory security group membership aligned with a simulated management-approved access register.

The assessment followed a structured technology audit process:

**Control Assessment → Evidence Collection → Access Testing → Exception Identification → Remediation → Retesting**

The project demonstrates how technical identity and access management skills can support IT audit, governance, risk, and compliance activities.

> **Disclaimer:** This is an educational simulation conducted in an independent lab. It is not an audit of a real financial reporting system, a formal SOX compliance assessment, or an opinion on internal control over financial reporting.

---

## Executive Summary

The initial control test identified one simulated unauthorized group membership.

The exception was documented, corrected, and independently retested using a new PowerShell export.

| Assessment Metric        | Result                                 |
| ------------------------ | -------------------------------------- |
| Control Tested           | ITGC-01 — Logical Access Management    |
| Initial Group Members    | 4                                      |
| Authorized Members       | 3                                      |
| Exceptions Identified    | 1                                      |
| Initial Result           | EXCEPTION                              |
| Remediation              | Unauthorized membership removed        |
| Post-Remediation Members | 3                                      |
| Remaining Discrepancies  | 0                                      |
| Retest Result            | PASS                                   |
| Final Status             | Remediated — Retest Passed (Simulated) |

**Conclusion:** The post-remediation test found no discrepancies between the three remaining direct group memberships and the simulated approved-access register.

---

## Business Risk

Logical access controls help organizations restrict sensitive systems and information to authorized personnel.

For financial reporting environments, inappropriate access may create risks involving unauthorized data access or modification.

This assessment evaluated whether a designated Active Directory group contained only users with documented simulated authorization.

### Control Objective

Ensure membership in `GG_FinanceLedger_Users` is restricted to users authorized to access the fictional FinanceLedger application.

---

## Lab Environment

| Component             | Description                 |
| --------------------- | --------------------------- |
| Directory Service     | Microsoft Active Directory  |
| Domain                | `lab.local`                 |
| Organizational Unit   | `Corp/Groups`               |
| Security Group        | `GG_FinanceLedger_Users`    |
| Application           | FinanceLedger (Fictional)   |
| Evidence Collection   | Windows PowerShell          |
| Testing Documentation | Spreadsheet Audit Workpaper |
| Assessment Type       | Simulated SOX ITGC          |

---

## Assessment Methodology

### 1. Establish Authorization Criteria

Created a simulated approved-access register identifying the users authorized to access FinanceLedger.

### 2. Collect Actual Group Membership

Inspected the Active Directory security group and exported its membership using PowerShell.

```powershell
Get-ADGroupMember -Identity "GG_FinanceLedger_Users" |
    Select-Object Name, SamAccountName, ObjectClass |
    Export-Csv "C:\Users\Public\SOX_ITGC-01_E04_FinanceLedger_Actual_Group_Membership.csv" -NoTypeInformation
```

### 3. Compare Approved and Actual Access

Compared actual direct group membership against the simulated authorization register.

### 4. Document the Exception

Identified one deliberately introduced unauthorized group membership.

Created a structured finding documenting the condition, criteria, risk, recommendation, and supporting evidence.

### 5. Perform Remediation

Removed the unauthorized account from the Active Directory security group.

### 6. Retest the Control

Generated a new membership export and compared it against the approved-access register.

The retest identified no remaining discrepancies among the three direct group members.

---

## Control Testing Results

### Initial Assessment

| Employee      | Department | Approved | Actual Membership | Result    |
| ------------- | ---------- | -------- | ----------------- | --------- |
| Amelia Green  | Finance    | Yes      | Yes               | PASS      |
| Ava Thompson  | Finance    | Yes      | Yes               | PASS      |
| Benjamin Hall | Finance    | Yes      | Yes               | PASS      |
| Ethan Murphy  | HR         | No       | Yes               | EXCEPTION |

**Initial Result: EXCEPTION IDENTIFIED**

The exception was intentionally introduced for the simulation.

### Post-Remediation Assessment

| Employee      | Approved | Actual Membership | Result |
| ------------- | -------- | ----------------- | ------ |
| Amelia Green  | Yes      | Yes               | PASS   |
| Ava Thompson  | Yes      | Yes               | PASS   |
| Benjamin Hall | Yes      | Yes               | PASS   |
| Ethan Murphy  | No       | No                | PASS   |

**Retest Result: PASS**

The post-remediation evidence confirmed that the identified direct group membership discrepancy was resolved.

---

## Audit Finding

### FIND-ITGC-01 — Simulated Unauthorized FinanceLedger Group Membership

**Condition:** Ethan Murphy was included in `GG_FinanceLedger_Users` without authorization in the simulated access register.

**Criteria:** Group membership should be restricted to users with documented authorization.

**Cause:** The exception was deliberately introduced for testing.

**Risk:** Unauthorized group membership could provide access to financially relevant resources if the group controls those permissions.

**Recommendation:** Investigate the discrepancy, validate authorization, and remove membership when unauthorized.

**Remediation:** Ethan Murphy was removed from the group.

**Retest:** A fresh PowerShell export confirmed that the remaining three direct memberships matched the simulated approved-access register.

**Final Finding Status:** Remediated — Retest Passed (Simulated)

---

## Audit Evidence

The assessment evidence package is organized using the following identifiers:

| Evidence | Description                                  |
| -------- | -------------------------------------------- |
| E01      | Initial Authorized Group Membership          |
| E02      | Simulated Unauthorized Group Membership      |
| E03      | Simulated Approved-Access Register           |
| E04      | Pre-Remediation PowerShell Membership Export |
| E05      | Logical Access Control-Testing Workpaper     |
| E06      | Active Directory Remediation Evidence        |
| E07      | Post-Remediation PowerShell Verification     |

The initial exception evidence was retained after remediation to preserve the testing history.

---

## Full Assessment Report

📄 [View the Full SOX ITGC Assessment Report](reports/Christopher_Davis_CISA_Simulated_SOX_ITGC_Access_Control_Assessment.pdf)

The report includes:

* Executive summary
* Assessment objectives and scope
* Risk and control matrix
* Testing methodology
* Initial control-testing results
* Audit finding
* Remediation activities
* Post-remediation verification
* Evidence register
* Assessment limitations and conclusion

*Note: This link will work once the PDF is uploaded to the `reports` folder using the filename shown above.*

---

## Skills Demonstrated

**Governance, Risk & Compliance**

* IT General Controls assessment
* Logical access-control testing
* Risk identification
* Audit finding documentation
* Evidence collection and traceability
* Remediation tracking
* Control retesting

**Technical**

* Active Directory
* Security group administration
* Identity and access management
* PowerShell
* CSV evidence exports
* Access review procedures

**Professional**

* Audit workpaper preparation
* Technical documentation
* Risk communication
* Evidence-based conclusions

---

## Assessment Limitations

This assessment was limited to a fictional application and direct membership in one Active Directory security group.

The project did not evaluate nested memberships, effective application permissions, historical approvals, or control operation throughout a reporting period.

The successful retest applies only to the defined test scope.

No claim of organizational SOX compliance is made.

---

## About the Author

**Christopher Davis, CISA**

Cybersecurity professional with experience in enterprise IT operations, identity administration, endpoint security, and technical control implementation.

Focused on applying hands-on technical expertise to governance, risk, compliance, technology audit, and identity security.

**GitHub:** [cdzerotrust](https://github.com/cdzerotrust)

---

**Project Status:** Completed — Simulated Assessment
**Final Control Result:** Remediated — Retest Passed
