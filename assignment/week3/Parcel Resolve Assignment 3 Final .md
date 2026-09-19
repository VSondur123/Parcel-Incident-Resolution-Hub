# Requirements Engineering Assignment 3
## ParcelResolve — Requirements Specification

**Group:** Varun & Thanh  
**Project:** Lost or Delayed Parcel Resolution System

---

# A. Functional Requirements

This section identifies the main functional requirements of ParcelResolve. The requirements are derived from the product vision, scope, stakeholders, and resolution lifecycle established in Assignment 2.

The main functional requirement areas are:

### A.1 Incident Initiation
- **FR-01:** System-initiated incident creation
- **FR-02:** Customer-initiated incident creation
- **FR-03:** Incident standardization

### A.2 Incident Assessment and Classification
- **FR-04:** Incident classification

Initial incident types:
- delayed parcel
- potentially lost parcel
- misdelivered parcel
- failed delivery
- delivery dispute

### A.3 Incident Information and Status
- **FR-05:** Incident information retrieval
- **FR-06:** Incident information management
- **FR-07:** Incident status management
- **FR-08:** Incident history

### A.4 Resolution Workflow
- **FR-09:** Workflow selection
- **FR-10:** Workflow progression

### A.5 Action and Responsibility Management
- **FR-11:** Action creation
- **FR-12:** Action assignment
- **FR-13:** Action tracking

### A.6 Evidence Management
- **FR-14:** Evidence capture
- **FR-15:** Evidence retrieval
- **FR-16:** Evidence source information

### A.7 Monitoring and Follow-Up
- **FR-17:** Incident monitoring
- **FR-18:** Follow-up notification

### A.8 Escalation
- **FR-19:** Incident escalation
- **FR-20:** Escalation record

### A.9 Customer Communication
- **FR-21:** Customer notification
- **FR-22:** Additional information request
- **FR-23:** Communication history

### A.10 Resolution Verification and Closure
- **FR-24:** Resolution verification
- **FR-25:** Incident closure
- **FR-26:** Closure record

### A.11 Operational Insights
- **FR-27:** Incident overview
- **FR-28:** Resolution information

---

# B. Non-Functional Requirements

This section identifies the main non-functional requirements and quality attributes relevant to ParcelResolve.

### B.1 Performance and Capacity
- **NFR-01:** Performance under expected workload
- **NFR-02:** Operational capacity

### B.2 Availability and Reliability
- **NFR-03:** Availability
- **NFR-04:** Data integrity
- **NFR-05:** Recovery of incident data

### B.3 Security and Access Control
- **NFR-06:** Authentication
- **NFR-07:** Authorization and access control
- **NFR-08:** Protection against excessive requests
- **NFR-09:** Personal data protection

### B.4 Auditability
- **NFR-10:** Audit trail

### B.5 Usability and Consistency
- **NFR-11:** Operational usability
- **NFR-12:** Terminology consistency

### B.6 Maintainability and Integration
- **NFR-13:** Configurable resolution rules
- **NFR-14:** Integration interfaces
- **NFR-15:** Integration failure handling

At this stage, numerical thresholds such as response time, availability percentage, incident volume, and recovery targets are not fixed because Assignment 2 does not provide sufficient operational baseline information to justify specific values. These values are reviewed further in Section D.

---

# C. Requirements Specification

In this section, the identified functional and non-functional requirements are written as formal requirements. The requirements use **“shall”** to express mandatory system behaviour or constraints.

## C.1 Functional Requirements

### FR-01 — System-Initiated Incident Creation
The system shall create an incident when an integrated operational system provides information that satisfies a configured incident-detection condition.

### FR-02 — Customer-Initiated Incident Creation
The system shall allow a customer-initiated parcel problem to be registered as an incident through a supported customer or customer-service channel.

### FR-03 — Incident Standardization
The system shall convert information received from different incident sources into a common incident structure containing the information required for further processing.

### FR-04 — Incident Classification
The system shall classify each incident into one of the supported incident types based on the information available at the time of assessment.

The initial supported incident types are delayed parcel, potentially lost parcel, misdelivered parcel, failed delivery, and delivery dispute.

The classification shall not imply certainty where the available evidence does not support it.

### FR-05 — Incident Information Retrieval
The system shall retrieve relevant incident information from connected organizational systems using the parcel identifier and relevant order reference.

### FR-06 — Incident Information Management
The system shall maintain the information required to manage an incident, including its type, source, status, responsibility, actions, deadlines, evidence, resolution information, and relevant history.

### FR-07 — Incident Status Management
The system shall maintain the current status of each incident throughout its resolution lifecycle.

### FR-08 — Incident History
The system shall maintain a chronological history of significant changes and activities associated with each incident.

### FR-09 — Workflow Selection
The system shall select a resolution workflow based on the incident type and applicable business rules.

### FR-10 — Workflow Progression
The system shall track the progress of an incident through the applicable resolution workflow.

### FR-11 — Action Creation
The system shall create actions required to progress an incident toward resolution.

### FR-12 — Action Assignment
The system shall assign each actionable task to a responsible operational role or user.

### FR-13 — Action Tracking
The system shall track the status and deadline of each action until the action is completed, cancelled, or otherwise resolved.

### FR-14 — Evidence Capture
The system shall allow relevant evidence associated with an incident to be recorded or referenced.

Supported evidence may include delivery photographs, signature records, GPS coordinates, timestamps, event logs, and other relevant supporting information.

### FR-15 — Evidence Retrieval
The system shall allow authorized users to retrieve relevant evidence associated with an incident.

### FR-16 — Evidence Source Information
The system shall retain sufficient information to identify the source and context of evidence used during incident resolution.

### FR-17 — Incident Monitoring
The system shall monitor open incidents and their associated actions for configured deadlines, overdue conditions, status changes, and relevant new information from integrated systems.

### FR-18 — Follow-Up Notification
The system shall generate follow-up notifications when configured monitoring conditions require attention.

### FR-19 — Incident Escalation
The system shall escalate an incident when a configured escalation condition is satisfied.

Escalation may include reassignment, priority changes, notifications, or transition to another resolution workflow.

### FR-20 — Escalation Record
The system shall record the reason, time, and resulting action for each escalation.

### FR-21 — Customer Notification
The system shall support communication with the customer regarding incident confirmation, progress, next steps, and resolution.

### FR-22 — Additional Information Request
The system shall allow the resolution process to request additional information from the customer when the information is required to continue the investigation or resolution.

### FR-23 — Communication History
The system shall maintain a record of relevant customer communications associated with an incident.

### FR-24 — Resolution Verification
The system shall verify that the applicable resolution conditions have been satisfied before an incident can be closed.

### FR-25 — Incident Closure
The system shall close an incident only when the required resolution conditions have been verified.

### FR-26 — Closure Record
The system shall record the resolution outcome, closure time, and relevant information supporting the closure decision.

### FR-27 — Incident Overview
The system shall provide authorized operational users with an overview of open incidents, including their type, status, responsibility, deadlines, and escalation state.

### FR-28 — Resolution Information
The system shall provide operational information about incident volumes, resolution times, overdue incidents, escalations, recurring patterns, and resolution outcomes.

The exact analytics and reporting definitions remain subject to later detailed requirements.

---

## C.2 Non-Functional Requirements

### NFR-01 — Performance Under Expected Workload
The system shall provide incident-management operations within response-time thresholds defined for the expected operational workload.

The response-time targets shall be specified together with the workload assumptions used to evaluate them.

### NFR-02 — Operational Capacity
The system shall support the expected volume of incidents, concurrent operational users, and integration events defined for the target operational environment.

The capacity baseline shall be established before final performance thresholds are fixed.

### NFR-03 — Availability
The system shall be available during the operational periods required by the host organization, excluding planned maintenance periods agreed with the organization.

The availability target shall be defined based on the operational requirements of the host organization rather than assumed in advance.

### NFR-04 — Data Integrity
The system shall preserve the integrity and consistency of confirmed incident, action, status, evidence, communication, and resolution information following recoverable system failures.

### NFR-05 — Recovery of Incident Data
The system shall support recovery of incident data from the most recent valid recovery point following a recoverable system failure.

The required recovery point and recovery time targets shall be defined according to the host organization's operational needs.

### NFR-06 — Authentication
The system shall authenticate users and integrated system clients before allowing access to protected functionality or incident information.

### NFR-07 — Authorization and Access Control
The system shall restrict access to incident information and operations according to the authenticated user's or system client's assigned roles and permissions.

Access-control rules shall follow the principle of least privilege and shall prevent unauthorized users from viewing or modifying protected incident information.

### NFR-08 — Protection Against Excessive Requests
The system shall apply appropriate request-rate controls to protect protected interfaces from excessive or abusive requests.

Possible implementation mechanisms may include rate limiting, throttling, and other abuse-prevention controls. The final mechanism shall be selected during system design.

### NFR-09 — Personal Data Protection
The system shall process personal data only for purposes necessary for the incident-resolution process and shall apply appropriate technical and organizational measures for protecting such data in accordance with applicable data-protection requirements.

The requirement is intended to align with applicable regulatory obligations and relevant information-security and privacy practices, including GDPR and, where adopted by the host organization, ISO/IEC 27001 and ISO/IEC 27701.

### NFR-10 — Audit Trail
The system shall maintain an audit trail of significant changes and operations affecting incidents, actions, assignments, statuses, escalations, evidence, communications, and resolution information.

Each audit record shall contain sufficient information to identify the affected incident or resource, the operation performed, the time of the operation, and the responsible user or system component.

The implementation technology for audit storage is not prescribed at the requirements level. A data platform such as Databricks may be considered during architecture and implementation if it satisfies the required auditability, integrity, retention, and access requirements.

### NFR-11 — Operational Usability
The system shall present the information required to understand and act on an incident in a consistent and structured manner for authorized operational users.

### NFR-12 — Terminology Consistency
The system shall use consistent terminology for incident types, statuses, actions, responsibilities, escalations, and resolution states across supported interfaces and workflows.

### NFR-13 — Configurable Resolution Rules
The system shall allow applicable business rules, workflow conditions, monitoring thresholds, and escalation conditions to be maintained without requiring changes to the core application source code where technically feasible.

### NFR-14 — Integration Interfaces
The system shall provide defined interfaces for exchanging the information required to support integrations with relevant order-management, tracking, warehouse, delivery, and customer-service systems.

### NFR-15 — Integration Failure Handling
The system shall detect and appropriately handle failures or unavailable responses from integrated systems without silently losing incident-related information.

The system shall preserve sufficient information about integration failures to support investigation and recovery.

---

# D. Review of Requirements Against Product Vision and Scope

The requirements were reviewed against the product vision, product scope, stakeholder analysis, and lifecycle established in Assignment 2.

## D.1 Consistency with Product Vision

The central product value established in Assignment 2 is:

> **Turn a detected parcel problem into an actionable and trackable resolution process.**

The functional requirements support the complete resolution lifecycle:

| Product lifecycle | Related requirements |
|---|---|
| Detect | FR-01, FR-02, FR-03 |
| Understand | FR-04, FR-05, FR-06, FR-07, FR-08 |
| Act | FR-09, FR-10, FR-11, FR-12, FR-13 |
| Monitor | FR-17, FR-18, FR-19, FR-20 |
| Verify Resolution | FR-24 |
| Close | FR-25, FR-26 |

Evidence management, customer communication, and operational insights provide supporting capabilities for the resolution process.

## D.2 Consistency with Product Scope

The requirements remain within the scope established in Assignment 2.

Included areas are:

- incident initiation;
- incident classification;
- information retrieval and management;
- resolution workflows;
- action and responsibility management;
- evidence capture and retrieval;
- monitoring and escalation;
- customer communication;
- resolution verification and closure;
- operational insights;
- integration with existing organizational systems.

The requirements do not introduce functionality for:

- order creation or order management;
- core parcel-tracking infrastructure;
- warehouse management;
- route optimization or driver navigation;
- shipment creation or label generation;
- physical transportation or parcel recovery;
- payment or compensation processing;
- damaged-parcel handling as a current incident type;
- replacing existing operational staff;
- providing a generic multi-company resolution platform.

## D.3 Consistency with Incident Coverage

The initial incident coverage remains consistent with Assignment 2:

1. delayed parcel;
2. potentially lost parcel;
3. misdelivered parcel;
4. failed delivery;
5. delivery dispute.

No additional incident type has been introduced into the current requirements baseline.

## D.4 Consistency with Stakeholders

The requirements address the main stakeholder interests identified in Assignment 2.

### Host / Customer Organization
The requirements support consistent resolution, reduced manual coordination, operational visibility, integration, security, and maintainability.

### Product Owner
The requirements provide a structured basis for prioritization, scope control, validation, and later traceability.

### External Delivery Stakeholders
The requirements support customer communication, information requests, evidence, resolution verification, and closure.

### Operational Users
The requirements support incident classification, workflows, action assignment, monitoring, escalation, evidence, and operational overviews.

### IT / Integration Team
The requirements address authentication, authorization, data protection, auditability, integration interfaces, integration failures, maintainability, and reliability.

## D.5 Review of Non-Functional Requirements

The review identified that several numerical values should **not** be fixed yet.

The earlier draft proposed specific values such as response times and availability percentages. These values were removed because Assignment 2 does not provide sufficient information about:

- expected incident volume;
- peak traffic;
- concurrent users;
- integration-event rate;
- required operating hours;
- recovery needs.

Instead, the current requirements establish the measurable categories first and leave the exact thresholds to be defined from a future operational baseline.

This creates a more defensible requirements specification because the eventual numerical thresholds can be traced to workload and stakeholder needs rather than arbitrary assumptions.

## D.6 Security and Privacy Review

The security requirements were separated into different concerns:

- authentication;
- authorization and access control;
- protection against excessive requests;
- personal-data protection;
- auditability.

This avoids treating a specific technical mechanism as the requirement itself.

For example, rate limiting may be used to protect interfaces against excessive requests, while role-based access control may be used to implement authorization. These are implementation decisions that can be evaluated during architecture and design.

For personal-data protection, the requirement is aligned with applicable data-protection obligations and relevant security/privacy standards. GDPR, ISO/IEC 27001, and ISO/IEC 27701 are treated as reference frameworks rather than as sources of arbitrary system thresholds.

## D.7 Requirements and Implementation Separation

The review also confirmed that implementation technologies should not be unnecessarily fixed at the requirements stage.

For example:

- The requirement is to maintain an audit trail.
- Databricks may be considered as one implementation option.
- The requirement is to control excessive requests.
- Rate limiting or throttling may be used as implementation mechanisms.
- A Bloom filter may be considered as an optimization for a specific technical use case, but it is not itself the access-control requirement.

This separation keeps the requirements focused on **what the system shall achieve** while allowing architecture and technology decisions to be evaluated separately.

## D.8 Open Points Identified During Review

The following items require further stakeholder or technical analysis before they can be assigned final measurable thresholds:

- expected daily incident volume;
- peak incident creation/event rate;
- concurrent operational users;
- response-time targets;
- availability target;
- recovery point objective (RPO);
- recovery time objective (RTO);
- detailed escalation thresholds;
- detailed monitoring thresholds;
- analytics definitions;
- supported communication channels;
- detailed integration interfaces and data formats.

These open points can be refined in later requirements work once the necessary operational assumptions and stakeholder expectations are available.

## D.9 Overall Review

The review confirms that the current requirements remain consistent with the product vision and scope from Assignment 2.

The main refinement from the initial requirements draft is that the specification now separates:

**identified requirements → formal requirement statements → review and validation → implementation decisions.**

This keeps the requirements focused on the intended behaviour and quality of ParcelResolve while avoiding unsupported assumptions about workload, performance thresholds, or specific technologies.


### D.1 Product Vision and Requirements Traceability

The requirements were reviewed against the product vision and the resolution lifecycle established in Assignment 2. The following diagram shows how the product vision and scope are translated into stakeholder needs and requirements, and how the functional requirements support the ParcelResolve resolution lifecycle.
