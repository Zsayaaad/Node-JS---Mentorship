# Manage Time Use Case — Vacation Tracking System (VTS)

This folder contains the design artifacts for the **Manage Time** use case of the Vacation Tracking System, including the entity-relationship model, the end-to-end workflow flowchart, and the system sequence diagram.

---

## Entity Relationship Diagram (ERD)

The ERD below models the data structure of the Manage Time use case. It shows the core entities — Employee, VacationRequest, VacationRequestDay, VacationCategory, VacationBalance, ApprovalDecision, and Calendar — along with their attributes and the relationships between them (e.g., an Employee _submits_ VacationRequests, a Manager _decides_ on them via ApprovalDecision, and each request _contains_ one or more VacationRequestDays).

![Entity Relationship Diagram for the VTS Manage Time use case](diagrams/ERD_VTS_ManageTime_usecase.png)

---

## Flowchart

### Simplified Flowcharts

The following two diagrams are simplified, role-specific views of the main flowchart below, isolating each actor's perspective for easier readability.

#### Employee Flow

The Employee Flow focuses on the employee's journey: selecting VTS from the portal, viewing vacation balances, choosing a vacation type and filling the form, submitting the request, handling validation errors, and — if approval is required — notifying the manager by email before saving the request to the database.

![Simplified flowchart — Employee Flow](diagrams/manageTime_useCase_EmployeeFlow.drawio.png)

#### Manager Flow

The Manager Flow focuses on the manager's journey: receiving the leave-request email notification, logging in, deciding to approve or reject (with an explanation on rejection), saving the decision and status to the database, and notifying the employee by email.

![Simplified flowchart — Manager Flow](diagrams/manageTime_useCase_ManagerFlow.drawio.png)

### Complete Flowchart

The flowchart below illustrates the complete workflow of the Manage Time use case across three swimlanes — Employee, VTS, and Manager. It covers the employee selecting a vacation type with a positive balance, entering and submitting request details, the system validating the data (with errors highlighted for correction or cancellation), and the manager reviewing, approving, or rejecting the request, including email notifications and post-decision navigation.

![Flowchart of the VTS Manage Time use case workflow](diagrams/Flowchart_VTS_ManageTime_useCase.png)

---

## Sequence Diagram

The sequence diagram below details the message flow over time between the Employee, Manager, Intranet Portal, VTS, and Email Notification components. It shows the employee opening VTS via the intranet portal, submitting a vacation request, the alternative paths for data validation (valid vs. invalid/incomplete data), whether manager approval is required, the manager's credential check, the approve/disapprove decision, and the resulting email notification to the employee.

![Sequence diagram for the VTS time management use case](diagrams/sequenceDiagram_VTS_timeManagement_usecase.png)
