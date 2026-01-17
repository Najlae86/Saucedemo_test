# 🛒 SauceDemo E-Commerce QA Project
### Manual Testing & Defect Lifecycle Management

## 📄 Project Overview
This repository contains the full QA documentation suite for a manual testing cycle performed on the **SauceDemo E-Commerce Application** (Swag Labs). 

The project follows a rigorous **STLC (Software Testing Life Cycle)** approach, covering Test Planning, Test Design, Execution, Defect Reporting, and Final Sign-off. The testing strategy focused on **Persona-Based Testing**, utilizing specific user profiles to uncover functional, visual, and performance defects.

---

## 👥 The QA Team
* **Oumnia:** QA Lead & Strategy Owner
    * *Role:* Strategy, Planning, and Final Release Decision (Go/No-Go).
* **Najlae:** Test Designer & Functional Analyst
    * *Role:* **Documentation Lead** (Created Test Scenarios & Charters) & Executor for Edge Cases (`problem_user`).
* **Hajar:** Test Analyst
    * *Role:* Execution of Standard Flows (Happy Path) & Security Testing.
* **Mohammed (Med):** Test Analyst
    * *Role:* UI/UX Audit, Performance Testing, and Critical Path Execution.

---
## 📂 Repository Structure
The documentation is organized according to the Agile QA workflow:

```
📦 SauceDemo_QA_Project
 ┣ 📂 01_Strategie_Planification
 ┃ ┣ 📄 Test_Strategy.pdf                # Approach, Tools, & Environment
 ┃ ┣ 📄 Test_Plan_Sprint.pdf             # Scope, Objectives, & Resources
 ┃ ┣ 📄 Test_Environment_Spec.pdf        # Spec: Chrome/Edge, Windows 11
 ┃ ┣ 📄 Risk_Analysis.xlsx               # Product Risk Assessment
 ┃ ┣ 📄 Definition_of_Done.pdf           # QA Exit Criteria
 ┃ ┗ 📄 Review_Report.docx               # Peer Review Logs
 ┃
 ┣ 📂 02_Conception_Design
 ┃ ┣ 📄 Test_Scenarios.xlsx              # High-Level Scenarios (Auth, Cart, etc.)
 ┃ ┣ 📄 RTM_Traceability_Matrix.xlsx     # Req ID mapped to Test Case ID
 ┃ ┣ 📄 Test_Data.xlsx                   # User Credentials & Test Inputs
 ┃ ┣ 📄 Acceptance_Criteria.docx         # User Story constraints
 ┃ ┗ 📂 04_Test_Cases_Suites
 ┃ ┃ ┣ 📄 TC_01_Standard_User.xlsx
 ┃ ┃ ┣ 📄 TC_02_Locked_Out_User.xlsx
 ┃ ┃ ┣ 📄 TC_03_Problem_User.xlsx
 ┃ ┃ ┣ 📄 TC_04_Performance_Glitch_User.xlsx
 ┃ ┃ ┣ 📄 TC_05_Error_User.xlsx
 ┃ ┃ ┗ 📄 TC_06_Visual_User.xlsx
 ┃
 ┣ 📂 03_Execution_Agile
 ┃ ┣ 📄 Test_Checklist.xlsx              # Daily Readiness & Sanity Check
 ┃ ┣ 📄 Test_Charter.pdf                 # Exploratory Testing Session Notes
 ┃ ┗ 📄 Test_Execution_Schedule.xlsx     # Daily Planning & Assignments
 ┃
 ┗ 📂 04_Reporting_Anomalies
   ┣ 📄 Bug_Reports_Global.xlsx          # Detailed Defect Tracking (Jira Export)
   ┣ 📄 Test_Execution_Report.xlsx       # Full Execution Logs (Pass/Fail)
   ┗ 📄 Test_Summary_Report.docx         # Final Executive Summary (GO/NO-GO)
```
---

## 🎯 Testing Strategy: Persona-Based Approach

We utilized the unique data sets provided by the application to simulate different real-world risks:

| Persona | Focus Area | Key Outcome |
| --- | --- | --- |
| **Standard User** | Happy Path, E2E Flow | ✅ Mostly Stable |
| **Problem User** | Broken Assets, Logic Errors | ❌ Critical Failures |
| **Performance User** | Latency, Session Timeout | ⚠️ High Latency (>5s) |
| **Visual User** | UI Alignment, Responsive Design | ❌ Severe UI Distortion |
| **Error User** | Logic Gates, Dead Links | ❌ Checkout Blocked |
| **Locked Out User** | Security Protocols | ✅ Secure |

---

## 📊 Execution Metrics

* **Total Tests Executed:** 99
* **Passed:** 60 (60.6%)
* **Failed:** 36 (36.4%)
* **Blocked:** 3 (3.0%)

### Critical Defects Found (Sample)

| ID | Title | Severity | Impact |
| --- | --- | --- | --- |
| **BUG-CHK-01** | Checkout "Continue" Button Unresponsive | **Critical** | Prevents users from entering shipping info (100% Revenue Loss). |
| **BUG-CART-01** | "Add to Cart" Buttons Dead | **Critical** | Specific items cannot be purchased. |
| **BUG-CHK-03** | "Finish" Button Event Listener Failure | **Critical** | Order completion fails at the final step. |
| **BUG-AUTH-01** | Forced 5s Latency on Login | **High** | Degrades user experience significantly. |

---

## 🚀 Final Verdict: NO-GO 🔴

Despite the successful validation of the "Standard User" path, the project is **rejected for release**.

**Reasoning:**

1. **Critical Functionality Blocked:** The Checkout process is completely broken for specific user segments due to unresponsive buttons (`BUG-CHK-01`).
2. **Revenue Risk:** Users cannot add specific high-value items to the cart (`BUG-CART-01`).
3. **Quality Standards:** A failure rate of **36%** exceeds the acceptable threshold for production deployment.

**Recommendation:** Immediate hotfix required for the Checkout Module followed by a full regression cycle.

---
