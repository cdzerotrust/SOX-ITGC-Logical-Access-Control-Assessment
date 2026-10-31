# SOX ITGC Audit Evidence
## Evidence Register

**Project:** Simulated SOX ITGC Logical Access Control Assessment  
**Control ID:** ITGC-01  
**System:** FinanceLedger (Fictional)  
**Environment:** Independent Active Directory Lab

### Control Testing Evidence

| Evidence ID | Description | Purpose |
|---|---|---|
| E01 | [Initial Approved Group Membership](./SOX_ITGC-01_E01_FinanceLedger_Approved_Users_Group.png) | Establishes the initial membership baseline |
| E02 | [Simulated Unauthorized Access Exception](./SOX_ITGC-01_E02_FinanceLedger_Unauthorized_Access_Exception.png) | Documents the simulated exception |
| E03 | [Approved Access Register](./SOX_ITGC-01_E03_FinanceLedger_Approved_Access_Register.png) | Establishes authorization criteria |
| E04 | [Actual Group Membership Export](./SOX_ITGC-01_E04_FinanceLedger_Actual_Group_Membership.png) | Supports the initial access test |
| E05 | [Logical Access Control Testing Workpaper](./SOX_ITGC-01_E05_Logical_Access_Control_Testing_Workpaper.png) | Documents PASS and EXCEPTION results |

### Audit Finding and Remediation Evidence

| Evidence ID | Description | Purpose |
|---|---|---|
| E05-A | [Final Audit Finding and Retest](./SOX_ITGC-01_E05_Final_Audit_Finding_and_Retest.png) | Documents the finding and retest |
| E05-B | [Final Remediation and Retesting](./SOX_ITGC-01_E05_Final_Remediation_and_Retesting.png) | Documents corrective action |
| E06 | [Access Remediation](./SOX_ITGC-01_E06_FinanceLedger_Access_Remediation.png) | Shows removal of unauthorized membership |
| E07 | [Post-Remediation Verification](./SOX_ITGC-01_E07_Post_Remediation_Verification.png) | Confirms the corrected group membership |

## Assessment Results

**Initial Testing:** 3 PASS / 1 EXCEPTION

**Exception:** Ethan Murphy appeared in the FinanceLedger security group without authorization in the simulated approved-access register.

**Remediation:** Ethan Murphy was removed from the security group.

**Retest:** PASS — The three remaining direct group memberships matched the approved-access register.

**Final Status:** Remediated — Retest Passed (Simulated).

## Assessment Limitations

This is an educational simulation, not an actual SOX audit.

Testing was limited to direct membership in one Active Directory security group. Nested group membership, effective application permissions, and historical access approvals were outside the assessment scope.
