# SOX ITGC Audit Evidence
## Evidence Register

**Project:** Simulated SOX ITGC Logical Access Control Assessment  
**Control ID:** ITGC-01  
**System:** FinanceLedger (Fictional)  
**Environment:** Independent Active Directory Lab

### Control Testing Evidence

| Evidence ID | Description | Purpose |
|---|---|---|
| E01 | Initial Approved Group Membership | Establishes the authorized group membership baseline. |
| E02 | Simulated Unauthorized Access Exception | Shows the deliberately introduced unauthorized membership. |
| E03 | Approved Access Register | Documents the simulated management-approved users. |
| E04 | Actual Group Membership Export | Demonstrates PowerShell evidence collection before remediation. |
| E05 | Logical Access Control Testing Workpaper | Documents the comparison of approved and actual access. |

### Audit Finding and Remediation Evidence

| Evidence ID | Description | Purpose |
|---|---|---|
| E05-A | Final Audit Finding and Retest | Documents the simulated control exception and outcome. |
| E05-B | Final Remediation and Retesting | Records corrective action and retest results. |
| E06 | Access Remediation | Shows the unauthorized membership was removed. |
| E07 | Post-Remediation Verification | Demonstrates a fresh PowerShell export of the remaining group members. |

## Assessment Results

**Initial Testing:** 3 PASS / 1 EXCEPTION

**Exception:** Ethan Murphy appeared in the FinanceLedger security group without authorization in the simulated approved-access register.

**Remediation:** Ethan Murphy was removed from the security group.

**Retest:** PASS — The three remaining direct group memberships matched the approved-access register.

**Final Status:** Remediated — Retest Passed (Simulated).

## Assessment Limitations

This is an educational simulation, not an actual SOX audit.

Testing was limited to direct membership in one Active Directory security group. Nested group membership, effective application permissions, and historical access approvals were outside the assessment scope.
