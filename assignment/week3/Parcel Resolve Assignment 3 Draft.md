# Requirements Engineering Assignment 3
## ParcelResolve — Requirements Specification

**Group:** Varun & Thanh  
**Based on:** Assignment 2 — Product Vision, Scope and Stakeholder Analysis

> **Draft for review:** First proposed version of sections A–D. We will review and refine each section before treating it as final.

---

# A. Main Functional Requirements

The following functional requirements refine the ParcelResolve product vision and scope from Assignment 2. They describe what the system **shall** do.

## A.1 Incident Initiation

**FR-01 — System-initiated incident creation**  
The system shall create an incident when a connected operational system reports a supported parcel incident.

**FR-02 — Customer-initiated incident creation**  
The system shall allow an authorized user to create an incident when a customer reports a parcel problem.

**FR-03 — Incident standardization**  
The system shall convert incoming incident information into a common ParcelResolve incident format before the incident enters the resolution workflow.

## A.2 Incident Assessment and Classification

**FR-04 — Incident classification**  
The system shall classify each incident into one of the supported incident types based on available incident information and configured classification rules.

Supported types:
- delayed parcel;
- potentially lost parcel;
- misdelivered parcel;
- failed delivery; and
- delivery dispute.

**FR-05 — Incident information retrieval**  
The system shall retrieve relevant information about an incident from connected organizational systems when that information is available.

## A.3 Incident Information and Status

**FR-06 — Incident information management**  
The system shall maintain the information required to manage an incident, including the parcel identifier, relevant order reference, incident type, source, current status, responsible party, actions, deadlines, and resolution information.

**FR-07 — Incident status management**  
The system shall maintain the current status of each incident throughout its lifecycle.

**FR-08 — Incident history**  
The system shall maintain a chronological history of significant changes and actions associated with an incident.

## A.4 Resolution Workflow

**FR-09 — Workflow selection**  
The system shall select the applicable resolution workflow based on the incident type and configured business rules.

**FR-10 — Workflow progression**  
The system shall allow an incident to progress through its configured resolution workflow when the required conditions for the next step are satisfied.

## A.5 Action and Responsibility Management

**FR-11 — Action creation**  
The system shall create or record the actions required to resolve an incident.

**FR-12 — Action assignment**  
The system shall assign each required action to a responsible user, team, or organizational role.

**FR-13 — Action tracking**  
The system shall maintain the status, priority, deadline, and completion information of each incident action.

## A.6 Evidence Management

**FR-14 — Evidence capture**  
The system shall allow authorized users and connected systems to associate relevant evidence with an incident.

**FR-15 — Evidence retrieval**  
The system shall allow authorized users to retrieve relevant evidence associated with an incident.

**FR-16 — Evidence source information**  
The system shall record the source and timestamp of evidence when this information is available.

## A.7 Monitoring and Follow-up

**FR-17 — Incident monitoring**  
The system shall monitor open incidents and their associated actions for deadlines, overdue actions, and other configured follow-up conditions.

**FR-18 — Follow-up notification**  
The system shall notify the responsible user or team when a configured follow-up condition is reached.

## A.8 Escalation

**FR-19 — Incident escalation**  
The system shall escalate an incident when a configured escalation condition is satisfied.

**FR-20 — Escalation record**  
The system shall record the escalation action and resulting responsible party, priority, or workflow change.

## A.9 Customer Communication

**FR-21 — Customer notification**  
The system shall support sending incident-related communication to affected customers at configured points in the resolution workflow.

**FR-22 — Additional information request**  
The system shall allow an authorized user or configured workflow to request additional information from a customer when required for incident resolution.

**FR-23 — Communication history**  
The system shall record incident-related customer communications in the incident history.

## A.10 Resolution Verification and Closure

**FR-24 — Resolution verification**  
The system shall verify that the applicable resolution conditions have been satisfied before an incident is closed.

**FR-25 — Incident closure**  
The system shall allow an incident to be closed only when its required resolution conditions have been verified.

**FR-26 — Closure record**  
The system shall record the reason, timestamp, and relevant resolution information when an incident is closed.

## A.11 Operational Insights

**FR-27 — Incident overview**  
The system shall provide authorized users with an overview of open incidents by incident type and status.

**FR-28 — Resolution information**  
The system shall provide authorized users with information about resolution times, overdue incidents, escalated incidents, and recurring incident patterns.

---

# B. Non-Functional Requirements

## B.1 Performance

**NFR-01 — Incident information response time**  
The system shall display the current information of an existing incident within **2 seconds for at least 95% of requests** under normal operating conditions.

**NFR-02 — Incident creation response time**  
The system shall confirm successful creation of an incident within **3 seconds for at least 95% of requests** under normal operating conditions.

## B.2 Availability and Reliability

**NFR-03 — Availability**  
The system shall provide at least **99.5% monthly availability**, excluding planned maintenance announced in advance.

**NFR-04 — Data integrity**  
The system shall preserve confirmed incident, action, status, and evidence records after a recoverable system failure.

## B.3 Security

**NFR-05 — Authentication**  
The system shall require authenticated access for users performing incident-management operations.

**NFR-06 — Authorization**  
The system shall restrict access to incident information and incident-management actions according to the authenticated user's permissions.

## B.4 Data Protection

**NFR-07 — Personal data protection**  
The system shall process personal data only for purposes required by the incident-resolution process and according to the host organization's applicable data-protection requirements.

**NFR-08 — Data access control**  
The system shall prevent unauthorized users from accessing personal information associated with parcel incidents.

## B.5 Auditability

**NFR-09 — Audit trail**  
The system shall maintain an auditable record of significant incident changes, including the actor and timestamp when available.

## B.6 Usability

**NFR-10 — Incident overview usability**  
The system shall present the current incident status, responsible party, outstanding actions, and relevant deadlines in a single incident-management view.

**NFR-11 — Consistent terminology**  
The system shall use consistent terminology for incident types, statuses, actions, responsibilities, and resolution states throughout the user interface.

## B.7 Maintainability

**NFR-12 — Configurable rules**  
The system shall allow authorized administrators to modify supported incident-handling and escalation rules without changing the application source code.

## B.8 Integration

**NFR-13 — Integration interfaces**  
The system shall provide interfaces for exchanging relevant incident information with authorized organizational systems.

**NFR-14 — Integration failure handling**  
The system shall record and report failed data exchanges with connected systems so they can be investigated and retried where applicable.

## B.9 Recovery

**NFR-15 — Recovery of incident data**  
The system shall support recovery of incident data from the most recent successful backup following a system failure.

---

# C. Requirements Format and Notation

Each requirement has a unique identifier:

- **FR-XX** — Functional Requirement
- **NFR-XX** — Non-Functional Requirement

The proposed format is:

> **[ID] — [Requirement name]**  
> The system shall + specific behaviour or quality + relevant condition or constraint.

Example:

> **FR-25 — Incident closure**  
> The system shall allow an incident to be closed only when its required resolution conditions have been verified.

The requirements are intended to be:

- **Clear** — each requirement should have a single understandable interpretation.
- **Consistent** — requirements should not contradict one another.
- **Verifiable** — it should be possible to determine whether the requirement has been satisfied.
- **Traceable** — requirements should be connectable to the product vision, scope, stakeholder needs, and later verification activities.
- **Necessary** — each requirement should contribute to the intended product or its quality.
- **Atomic where practical** — one requirement should describe one main system obligation.

The use of **“shall”** indicates a mandatory requirement. Words such as *can*, *should*, *easy*, *fast*, or *appropriate* should be avoided when they make the requirement ambiguous or difficult to verify.

---

# D. Consistency with Assignment 2

The requirements in Sections A and B are derived from the product vision and scope established in Assignment 2.

## D.1 Consistency with the Product Lifecycle

Assignment 2 defined the ParcelResolve lifecycle as:

> **Detect → Understand → Act → Monitor → Verify Resolution → Close**

| Assignment 2 lifecycle | Related requirements |
|---|---|
| Detect | FR-01, FR-02, FR-03 |
| Understand | FR-04, FR-05, FR-06, FR-14–FR-16 |
| Act | FR-09–FR-13 |
| Monitor | FR-17, FR-18 |
| Verify Resolution | FR-24 |
| Close | FR-25, FR-26 |

## D.2 Consistency with In-Scope Capabilities

| Assignment 2 capability | Assignment 3 requirements |
|---|---|
| Incident Initiation | FR-01–FR-03 |
| Incident Assessment and Classification | FR-04–FR-05 |
| Incident Information and Status Management | FR-06–FR-08 |
| Resolution Workflow Management | FR-09–FR-10 |
| Action and Responsibility Management | FR-11–FR-13 |
| Evidence Capture and Retrieval | FR-14–FR-16 |
| Monitoring and Follow-up | FR-17–FR-18 |
| Escalation Management | FR-19–FR-20 |
| Customer Communication | FR-21–FR-23 |
| Resolution Verification and Closure | FR-24–FR-26 |
| Operational Insights | FR-27–FR-28 |

## D.3 Incident Coverage

The requirements remain within the incident coverage defined in Assignment 2:

- delayed parcels;
- potentially lost parcels;
- misdelivered parcels;
- failed deliveries; and
- delivery disputes.

## D.4 Integration Boundary

ParcelResolve remains a coordination and resolution layer rather than a replacement for existing operational systems.

Relevant integrations may include:

- order management systems;
- parcel tracking systems;
- warehouse management systems;
- delivery and driver systems;
- customer service systems; and
- other relevant internal operational platforms.

The requirements do not make ParcelResolve responsible for the core functions of these systems.

## D.5 Out-of-Scope Consistency

No requirements have been introduced for:

- order creation or order management;
- core parcel tracking infrastructure;
- warehouse management;
- route optimization or driver navigation;
- shipment creation or label generation;
- physical parcel transportation or recovery;
- payment processing or compensation workflows;
- damaged-parcel handling;
- replacing customer service or operational staff; or
- operating as a multi-company resolution platform.

This maintains the scope boundary established in Assignment 2.

## D.6 Stakeholder Consistency

The requirements reflect the stakeholder needs identified in Assignment 2:

- **Host / Customer Organization:** resolution efficiency, visibility, cost control, and operational improvement.
- **Product Owner:** manageable scope, product value, and measurable operational improvement.
- **External Delivery Stakeholders:** clear communication, fair and understandable resolution, and reduced repeated information requests.
- **Operational Users:** clear responsibilities, actionable workflows, accurate information, and support for exceptions.
- **IT / Integration Team:** reliable integrations, availability, security, maintainability, and clear system boundaries.

## D.7 Overall Requirements Engineering Trace

The intended refinement from Assignment 2 to Assignment 3 is:

> **Product Vision → Product Scope → Stakeholder Needs → Functional Requirements + Non-Functional Requirements**

Assignment 3 therefore refines the Assignment 2 scope rather than redefining the ParcelResolve product.
