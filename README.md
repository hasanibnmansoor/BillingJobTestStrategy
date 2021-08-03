# BillingJobTestStrategy
Test Strategy for Background Billing Job of a Landline Telephone System

## Introduction & Purpose of this Document
Purpose of this document is to briefly strategize the testing effort for "End-to-End Telecom Billing Scheduler" project. This project is a living document, in the sense, any updates to the project during the timeframe of testing would mean that this document goes through necessary update and should be reviewed with concerned stakeholders for sign-off.

Basis business requirement, following key features would be implemented as part of this project:
* Implementation of a background batch scheduler, that would automatically fetch billing data from Usage Database and send out the bills to the customers every 1st working day of a month.
* Implemenation of a new Admin Front-end Web Portal to manage the schedules of the billing background job.

Details Requirements can be found here: [LINK-TO-BRD].

Brief End-to-End Flow: Telecom Usage across multiple Customers -> Aggregated Data Fed in to Usage Database -> Monthly Billing Calculation & Bill Generation -> Send to Customer. Of the e2e flow briefed, the part that would be tested as part of this project would be limited to the "Monthly Billing Calculation & Bill Generation -> Send to Customer", generally defined as "Background Billing Job" throughout the document, hereon.

## Testing Assumptions & Scope Definition
* In terms of feature implementation, it is assumed (and true for the purpose of this document) that the feature to track Customer Usage and feeding to the database is implemented and test complete.

### In-Scope
* Functional Testing of Background Billing Job.
* Complete End-to-End Regression Cycle.
* Functional/Regression Testing would be carried out in "Staging Environment" as described in "Test Environment & Data Setup" section.

### Out of Scope
* Functional Testing of Usage & Usage DB Verification.
* Functional/Regression Testing in Prod Environment.

## Test Entry & Exit Criteria
### Entry Criteria
* Billing Background Feature is implemented
* Test Data & Environment Setup Complete
* Test Management & Defects Management Setup is Completed in Testrail & Jira respectively.
* Test Coverage for Functional and Regression Test Completed.
### Exit Criteria
* Functional Test & Regression Test Execution Pass Percentage > 90%
* All Critical & Blocker Bugs are Fixed and deployed.
* All Major & Minor Bugs are triaged and addressed for fast follow release cycles.

## Testing Types
### Functional Testing
Functional Testing is to ensure newly implemented functionalities are working as per intended requirements. 
### Regression Testing
Regression Testing is to ensure already implemented features (in this case, Usage DB update based on customer usage) is not broken, or any new bugs introduced as part of background job introduction.
### End-to-End and/or UAT Testing
E2E is to ensure the system works as intended from user perspective after the integration is completed, and would be treated for final release sign-off. 
Functional, Regression and E2E Scenarios/Test Cases would be documented as part of Functional Test Plan here: [Functional Test Plan]
### Performance/Load Testing
This is to ensure the background billing job works successfully and able to finish job within intended timeframe under "load". Load is determined by the amount of customers enrolled. This is emulated using tools such as JMeter, Locust, etc by simulating number of users enrolled for billing plan. This is also used to calculate KPI/metrics for background job performance long-term.
Performance/KPI Test Scenarios/Cases is documented in [Performance-Test-Plan] here.

## Testing Tools
* Test Management Tool: Testrail
* Defect Management & Sprint Backlog Tool: JIRA
* Automation Tools: Selenium (Front-end Web Portal Testing) & Locust (Performance/Load Testing Tools)

## Automation Strategy
Automation Testing would be onboarded during Regression Testing Cycle, and functional tests would go predominantly manual route. To start, sanity suite identified would be prime candidates for initial set of automation.
* First Category: Admin Web Portal. Cases considered for initial automation would be to verify successful login to admin portal using valid credentials, successful scheduling of bills and schedule modification. Negative scenarios like invalid login, scheduling with invalid dates, etc. also will be considered for automation.
* Second Category: Background Scheduler. Will be considered for automation once feature is stabilized. 

Detailed Automation Plan for this project can be found here: [LINK-TO-AUTOMATION-PLAN]

## Test Environment & Data Setup
* Staging Environment
- Batch Schedules would be mocked to run every one hour (and customizable as per testing needs), instead of every month (in Production)
- Database with pre-existing data setup in place, as per DB Schema & Usage Table Format.

## Release Strategy, Risks and Mitigation
* For successful sign-off, Exit Criteria must be met 100%.
* In case of any risks to the release, each risk should be dealt case-by-case basis and tracked in JIRA for closure. Based on the release sign-off meeting, QA would provide a "conditional" sign-off on case-by-case basis.

