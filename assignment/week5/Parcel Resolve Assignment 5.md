# Requirements Engineering Assignment 5 — ParcelResolve

## Requirements Traceability

**Group Name:** Varun & Thanh  
**Students:** Varun Ganesh Sondur, Pham Thanh

---

## A. Meaningful Relationships Between Artefacts

### A.1 Relationships Identified Across Assignments 2–4

This section identifies the principal relationships connecting the artefacts produced in Assignments 2–4. The artefacts considered are: Product Vision, Scope and Stakeholder Analysis (A2); Requirements Specification with Functional Requirements (FR-01–FR-28) and Non-Functional Requirements (NFR-01–NFR-16) (A3); and the Model-Based Validation Report including the behavioural model, scenarios, validation questions, findings and review decisions (A4).

### A.1.1 Stakeholder Needs → Requirements

Stakeholder goals and concerns from A2 map to clusters of functional and non-functional requirements:

- **Host / Customer Organisation (ST-001):** goals of faster, more consistent resolution and reduced manual coordination → FR-09–FR-13, FR-17–FR-20, FR-27–FR-28.
- **Operational User (ST-004):** need for clear responsibility and accurate information → FR-06–FR-08, FR-11–FR-13, NFR-11–NFR-12.
- **External Delivery Stakeholders (ST-003):** need for clear communication and fair, verifiable outcomes → FR-14–FR-16, FR-21–FR-23, FR-24–FR-26.
- **IT / Integration Team (ST-005):** concerns about reliable integrations, security, maintainability and protection of personal data → FR-05, NFR-06–NFR-09, NFR-13–NFR-16.

These links provide the rationale for why the requirements exist and identify which stakeholder needs should be reconsidered if a requirement changes.

### A.1.2 Product Goals / Vision → Requirements

The core value statement, **"Turn a detected parcel problem into an actionable and trackable resolution process,"** and the eleven Main Goals in A2 are realised through the FR and NFR sets. The resolution lifecycle — **Detect → Understand → Act → Monitor → Verify Resolution → Close** — provides the structural backbone against which the requirements are organised in A3 and validated in A4.

A direct StakeholderNeed → ProductGoal link is **not asserted in this assignment**, because the group has not formally documented the derivation of each A2 goal from a particular stakeholder need. The traceability representation therefore avoids inventing that relationship.

### A.1.3 Functional ↔ Non-Functional Requirements

FRs describe what the system shall do; NFRs constrain the quality, security, reliability and operational characteristics under which those behaviours must be delivered. Key cross-links are:

- FR-05, FR-09 and FR-17 ↔ NFR-14 and NFR-15 for integration interfaces and integration-failure handling.
- FR-06–FR-08, FR-20, FR-23 and FR-26 ↔ NFR-04, NFR-05 and NFR-10 for data integrity, recovery and auditability.
- Protected operations ↔ NFR-06 and NFR-07 for authentication and authorisation.
- Customer-facing and personal-data processing in FR-02 and FR-21–FR-23 ↔ NFR-09 for personal-data protection.

### A.1.4 Requirements → Model Elements, Scenarios and Review Findings

A4 maps all 28 FRs to one or more behavioural-model elements such as states, transitions and conditions. However, the A4 scenarios S-01–S-12 do **not** each validate every FR directly. In particular, FR-06–FR-08, FR-14–FR-16 and FR-27–FR-28 are represented in the model and requirement mapping but are not the main requirement of a scenario in S-01–S-12.

The traceability distinction is therefore:

- **All FRs:** mapped to relevant model elements.
- **Scenario-validated requirements:** a subset is exercised explicitly by S-01–S-12.
- **Review findings/decisions:** C-01–C-10 provide additional evidence and refinement history for requirements and model elements.

This avoids overstating the validation coverage of A4.

### A.1.5 Original Requirements → Revised Requirements and Open Refinements

Traceability distinguishes between changes that were actually applied to requirement text and findings that remain open for future refinement.

**Applied requirement changes from A2/A3 include:**

- ST-003 refined to distinguish sender and recipient roles.
- Evidence capture and retrieval added to the scope.
- GDPR/data-protection concerns made explicit.
- FR-09 extended with an unresolved-state fallback when no applicable workflow exists.
- FR-28 given concrete filtering criteria for operational insights.
- NFR-16 added for operational observability.

These are genuine **original → revised** requirement relationships.

**Open A4 refinements are different:** C-03 (terminal outcome for a permanently unmatched workflow) and C-06 (a bound on repeated escalation) identify future changes to the behavioural model and/or requirement specification, but the corresponding FR-09/FR-19/FR-20 wording was not changed because additional host-organisation input is still required. They are therefore recorded as **review finding → future refinement**, not as completed requirement revisions.

### A.1.6 Requirements ↔ Lifecycle Stages / Scenarios

Each lifecycle stage is linked to a set of FRs. For example, Detect covers incident initiation, Understand covers assessment and information/evidence handling, Act covers workflow and action management, Monitor covers monitoring and escalation, and Verify Resolution/Close covers closure conditions and closure records.

Scenarios S-01–S-12 exercise selected requirement/model relationships under normal, alternative and exceptional conditions. This provides a second-order trace from requirement to concrete behavioural path.

### A.1.7 Inter-Requirement Dependencies

The following dependencies are useful for change-impact analysis:

- FR-09 depends on FR-04 because workflow selection uses the incident classification.
- FR-13 depends on FR-11 and FR-12 because an action must exist and have an owner before its progress/deadline can be tracked.
- FR-20 depends on FR-19 because an escalation record corresponds to an escalation event.
- FR-19 depends on FR-17 because escalation is triggered by monitoring conditions.
- FR-24 and FR-25 depend on progression through Act/Monitor before resolution can be verified and closure allowed.
- NFR-07 depends on NFR-06 because authorisation requires an authenticated identity before role/access decisions can be applied.

### A.1.8 Prototype Links and Current Applicability

The assignment brief lists links between features and software components in prototypes as a possible traceability relationship. This relationship is **not applicable to the current project stage** because Assignments 2–4 did not produce a software prototype with implementation components. If a prototype is introduced later, feature/requirement → prototype component links can be added without changing the existing traceability model.

---

## B. Traceability Representation

### B.1 Stakeholder–Requirement–Model Traceability Matrix

The matrix below is a representative subset of the most important forward and backward links. The **Evidence / Origin** column makes the basis for each link explicit and helps distinguish a documented relationship from an inferred one.

| Source Artefact | ID / Element | Target Artefact | Target ID / Element | Link Type | Evidence / Origin |
|---|---|---|---|---|---|
| Stakeholder (A2) | ST-001 Host Org | FR (A3) | FR-09–13, 17–20, 27–28 | satisfies / supports | A2 stakeholder goals and concerns |
| Stakeholder (A2) | ST-004 Operational User | FR / NFR (A3) | FR-06–08, 11–13; NFR-11–12 | satisfies | A2 operational-user needs |
| Stakeholder (A2) | ST-003 External | FR (A3) | FR-14–16, 21–23, 24–26 | satisfies | A2 sender/recipient/provider concerns |
| Stakeholder (A2) | ST-005 IT/Integration | NFR (A3) | NFR-06–09, 13–16 | satisfies | A2 integration/security/maintainability concerns |
| Vision Goal (A2) | Main Goals 1–11 | FR (A3) | FR-01–FR-28 | realises | A2 vision/goals and A3 requirement set |
| Lifecycle (A2/A4) | Detect | FR (A3) | FR-01–FR-03 | covers | A2 lifecycle and A3 requirement grouping |
| Lifecycle (A2/A4) | Understand | FR (A3) | FR-04–FR-08, FR-14–FR-16 | covers | A3 grouping and A4 model |
| Lifecycle (A2/A4) | Act | FR (A3) | FR-09–FR-13 | covers | A3 grouping and A4 model |
| Lifecycle (A2/A4) | Monitor / Escalation | FR (A3) | FR-17–FR-20 | covers | A3 grouping and A4 model |
| Lifecycle (A2/A4) | Verify / Close | FR (A3) | FR-24–FR-26 | covers | A3 grouping and A4 closure rules |
| FR (A3) | FR-09 | Model (A4) | Understand → Act / Unresolved | implemented-by | A4 behavioural model |
| FR (A3) | FR-24 / FR-25 | Model (A4) | Verify Resolution → Close only | implemented-by | A4 closure restriction |
| NFR (A3) | NFR-15 | Model (A4) | Integration-failure path | refined-by | A4 findings C-02 and C-10 |
| FR (A3) | FR-22 | Model (A4) | Waiting-for-Customer state | refined-by | A4 finding C-01 |
| FR (A3) | FR-09 original | FR (A3 revised) | FR-09 + unresolved fallback | evolves-to | A3 revision record T-01 |
| NFR (A3) | NFR-10 | NFR (A3) | NFR-16 | complements | A3 requirement structure |
| FR (A3) | FR-04 | FR (A3) | FR-09 | depends-on | Requirement semantics |
| FR (A3) | FR-11 / FR-12 | FR (A3) | FR-13 | depends-on | Action lifecycle semantics |
| Scenario (A4) | S-03 No workflow | FR (A3) | FR-09 | validates | A4 scenario S-03 |
| Scenario (A4) | S-10 Invalid closure | FR (A3) | FR-24, FR-25 | validates | A4 scenario S-10 |
| Review Decision (A4) | C-03, C-06 | Model / FR | FR-09, FR-19/20 | refines / future refinement | A4 decision record; requirement text unchanged |

*Table 1: Excerpt of multi-artefact traceability matrix for ParcelResolve (Assignments 2–4).*

### B.2 Traceability Information Model (TIM)

The TIM defines the artefact types and directed link types used in the matrix.

#### Artefact Types

| Artefact Type | Origin | Examples |
|---|---|---|
| StakeholderNeed | A2 | ST-001…ST-005 goals and concerns |
| ProductGoal / Vision | A2 | Main Goals 1–11; Vision Statement |
| LifecycleStage | A2 / A4 | Detect, Understand, Act, Monitor, Verify, Close |
| FunctionalRequirement | A3 | FR-01…FR-28 |
| NonFunctionalRequirement | A3 | NFR-01…NFR-16 |
| ModelElement | A4 | States, transitions, conditions, waiting/failure paths |
| Scenario | A4 | S-01…S-12 |
| ValidationQuestion | A4 | VQ-01…VQ-14 |
| ReviewFinding / Decision | A3/A4 | T-01…T-06; C-01…C-10 |
| RevisionRecord | A2/A3 | Accepted, modified, deferred or rejected decisions |

#### Link Types

| Link Type | From → To | Purpose |
|---|---|---|
| satisfies / supports | StakeholderNeed → FR/NFR | Need coverage |
| realises | ProductGoal → FR | Goal realisation |
| covers | LifecycleStage → FR | Lifecycle completeness |
| implemented-by | FR → ModelElement | Behavioural mapping |
| constrains | NFR → FR / ModelElement | Quality constraint |
| depends-on | FR → FR | Inter-requirement dependency |
| validates | Scenario / VQ → FR/NFR | Validation evidence |
| refines / refined-by | Finding ↔ FR/NFR/Model | Review-driven refinement |
| evolves-to | OriginalReq → RevisedReq | Completed requirement change history |
| complements | NFR → NFR | Complementary quality attributes |

The `constrains` direction is deliberately kept as **NFR → FR / ModelElement**. FR-24/FR-25 therefore use only `implemented-by` in the matrix; the previous mixed use of `constrains` has been removed.

The TIM does not define a `motivates` StakeholderNeed → ProductGoal link because the group has not documented that derivation explicitly in A2. This avoids creating a relationship without evidence.

### B.3 Visual Traceability Chain

The main traceability path used in this project can be summarised as:

```text
Stakeholder Need
      ↓ satisfies / supports
Product Goal / Vision
      ↓ realises
Requirement (FR / NFR)
      ↓ implemented-by / constrains / depends-on
Behavioural Model
      ↓ validates
Scenario / Validation Question
      ↓ provides evidence for
Review Finding / Decision
      ↓ refines or evolves-to
Revision / Future Refinement
```

This chain makes the purpose of traceability explicit: every important relationship should be supported by identifiable evidence and should help explain what changes when an artefact evolves.

---

## C. Why the Selected Trace Links Are Useful

### C.1 Requirements Understanding

Linking stakeholder needs and product goals to FRs/NFRs, and linking FRs to lifecycle stages and model elements, makes the rationale for each requirement visible. For example, the reason for FR-24/FR-25 can be followed through the lifecycle principle that **action completion is not necessarily resolution**, to the requirement, and then to the A4 model restriction that closure is permitted only after verification.

### C.2 Change Management and Impact Analysis

Traceability is particularly useful when requirements evolve because it exposes both upstream rationale and downstream impact.

**Forward example:** if FR-04 classification changes, FR-09 workflow selection must be reconsidered. The Unresolved path, scenario S-03 and the open C-03 refinement may then also require review.

**Backward example:** if the integration-failure model path associated with NFR-15 is changed, the links from that model/finding back to NFR-15 and the associated integration-dependent FRs identify which requirements need to be reassessed. This demonstrates that impact analysis can work in both directions rather than only from a changed requirement toward downstream artefacts.

### C.3 Requirements Review and Validation

Scenario and ValidationQuestion links provide explicit evidence that selected requirements have been exercised against expected behaviour. Review decisions such as C-01 and C-02 preserve the relationship between a finding and the requirement/model element it affects. This makes it easier to determine whether a proposed change invalidates previous validation evidence.

### C.4 Maintenance and Evolution

Original → revised links and RevisionRecords preserve the decision trail. When an accepted change is made, the previous version remains identifiable, the reason for change is recorded, and affected model/scenario links can be reassessed.

### C.5 Scope Control

Traceability can also be used to control scope. A proposed requirement that cannot be connected to an existing stakeholder need, product goal, or approved project boundary should receive explicit Product Owner review rather than being added automatically.

A concrete example is the earlier treatment of implementation-specific security detail in A3: a proposal that specified a particular encryption implementation was rejected because the requirement should express the necessary security property rather than unnecessarily prescribe an implementation. The decision record therefore provides evidence for why the proposal did not become part of the requirement baseline.

### C.6 How Trace Links Are Maintained When a Requirement Changes

The project uses the following lightweight maintenance process:

1. **Identify the changed artefact.** Record the requirement ID and what changed in its text or meaning.
2. **Check upstream links.** Revisit the stakeholder need and/or product goal linked to the requirement and confirm that the rationale still holds.
3. **Check inter-requirement dependencies.** Follow `depends-on` links in both directions to identify related requirements.
4. **Check behavioural links.** Reassess affected model elements, states, transitions and conditions.
5. **Check validation evidence.** Identify scenarios and validation questions linked to the changed requirement and determine which must be rerun or reconsidered.
6. **Check review history.** Revisit related findings and decisions to see whether their rationale remains valid.
7. **Record the revision.** Create or update the `evolves-to` / RevisionRecord relationship and preserve the previous requirement version.
8. **Use the LLM as a candidate-link checker.** Provide the changed requirement and current traceability matrix to Claude and ask it to suggest missing or potentially broken links. The LLM does not decide whether a link is valid.
9. **Human validation and baseline update.** The group accepts, modifies or rejects the suggested links, then updates the matrix and evidence column.

**ParcelResolve example — FR-09:** FR-09 was extended in A3 to handle the case where no applicable workflow exists. The change required the group to check the dependency from FR-04 classification, update the model to include the Unresolved / Operational Review path, preserve the original-to-revised relationship, and ensure scenario S-03 covered the no-workflow case. The A4 review then identified a remaining refinement: the terminal outcome for a case that remains permanently unmatched (C-03). That refinement is recorded as an open future change rather than being presented as an already-applied requirement revision.

This process keeps trace links as maintained engineering evidence rather than treating the matrix as a one-time documentation exercise.

---

## D. Tool / Approach Supporting Requirements Traceability

### D.1 LLM-Supported Approach Used in This Project

The actual approach used for ParcelResolve is a lightweight **LLM-assisted traceability maintenance process**. It was chosen because the current artefact set is relatively small but already contains multiple artefact types: stakeholders, goals, 28 FRs, 16 NFRs, lifecycle/model elements, scenarios and review decisions.

The approach consists of five elements:

1. **Stable identifiers.** Artefacts use stable IDs such as ST-00x, FR-xx, NFR-xx, S-xx, C-xx and T-xx.
2. **Central traceability matrix.** The matrix is maintained as a project artefact alongside the requirements documentation so that relationships and evidence remain visible in one place.
3. **LLM candidate-link generation.** After a requirement revision, the changed requirement text and current traceability matrix are supplied to Claude. The model is asked to identify candidate missing links, orphan requirements, potentially broken links and likely impact candidates.
4. **Operational definition of a broken link.** A link is treated as potentially broken when a source or target artefact has changed in a way that may alter the meaning or evidence supporting the relationship. The link is therefore flagged for human reassessment; it is not automatically deleted.
5. **Human decision and revision record.** The group reviews each candidate link and records whether it is accepted, modified, deferred or rejected. Requirement revisions retain an explicit relationship to their previous version where applicable.

The approach is **semi-automated rather than fully automated**: the LLM proposes relationships, while the group validates the evidence and decides the final trace links.

### D.2 Benefits Observed

- The LLM helped identify relationships that were easy to overlook, particularly inter-requirement and FR↔NFR dependencies.
- It helped expose missing behavioural coverage, such as the FR-09 no-workflow case.
- It provided a repeatable review prompt for checking whether a changed requirement might affect other artefacts.
- The stable identifiers made it easier to discuss changes across A2–A5.
- Human review prevented plausible but unsupported LLM-generated relationships from being added automatically.

### D.3 Challenges and Limitations

- Traceability still requires maintenance effort as the number of links grows.
- LLMs can propose links that appear plausible but are not justified by the source artefacts.
- Ambiguous requirement terms such as "relevant", "sufficient" and "appropriate" make automated link checking less reliable.
- Quantitative NFR baselines that remain open reduce the strength of some traces until operational values are defined.
- The same LLM was used across multiple assignments, so there is a risk that later reviews may reinforce earlier suggestions instead of challenging them. Human review is the primary mitigation.

### D.4 Brief Comparison with Commercial Requirements Tools

Commercial requirements-management platforms such as Jama Connect, Siemens Polarion, PTC Codebeamer and IBM DOORS Next provide capabilities such as bidirectional links, suspect-link handling, coverage views and impact analysis. These tools provide a useful reference for what a mature traceability environment can offer, but they are not the approach implemented for this academic project. The ParcelResolve approach focuses instead on stable IDs, a transparent matrix, LLM-assisted candidate generation and human validation.

---

## E. Maintaining Trace Links as Requirements Evolve — Literature Review

### E.1 Literature Argument

The literature reviewed supports a clear progression relevant to ParcelResolve:

**Traceability supports change management → maintaining links is costly → automation can reduce the effort → automated/LLM recovery remains imperfect → human validation is therefore needed.**

Tian et al. (2021) provide the broader evidence base. Their systematic mapping study analysed 63 studies and found that change management was the most frequently supported maintenance/evolution activity. They also identified establishing and maintaining traceability links as the main cost of traceability practice. This directly motivates keeping only high-value links continuously maintained in the current project. citeturn0search1

Alturayeif et al. (2025) reviewed 59 ML-based software traceability studies published from 2014 to June 2024. Their review shows the growth of automated approaches, including deep learning and LLM-based methods, while also identifying challenges such as data scarcity, imbalanced datasets, limited real-world data and missing true links. This supports using automation as assistance rather than assuming that generated links are automatically correct. citeturn0search0

Chen et al. (2026) provide a broader systematic view of software-artifact traceability, covering 22 artefact types and 23 association types. The study highlights the fragmented nature of traceability research and reports continuing challenges around reproducibility and industrial adoption. This supports the use of explicit artefact types, defined link semantics and evidence in the ParcelResolve TIM rather than relying on informal links. citeturn0academia36

Hey et al. (REFSQ 2025) specifically investigate requirements trace-link recovery using retrieval-augmented generation. Their evaluation on six benchmark datasets reports improvements over baseline approaches, while also concluding that the performance is not sufficient for fully automated practical recovery. This provides direct support for the ParcelResolve decision to use LLMs for candidate-link generation while retaining human validation. citeturn0search2

### E.2 Implications for ParcelResolve

The literature suggests four practical principles for this project:

1. **Maintain traceability for change management.** The value of the links becomes especially visible when requirements evolve and impact must be assessed.
2. **Keep maintenance effort proportional.** Because maintaining links is itself costly, the project prioritises high-value relationships such as stakeholder → requirement, requirement → model, requirement → scenario and original → revised.
3. **Use automation to reduce repetitive work.** LLMs can suggest candidate links and potential impact areas more quickly than checking every relationship manually from scratch.
4. **Keep human validation in the loop.** Current research does not justify treating automatically recovered links as universally correct. The group therefore treats LLM output as review input, not as traceability truth.

The resulting approach is consistent with the literature while remaining proportionate to the scale and maturity of ParcelResolve.

### E.3 Verified Literature Sources

The following four sources were checked against their publisher, conference or research-record pages before inclusion:

1. Tian, F., Wang, T., Liang, P., Wang, C., Khan, A. A., & Babar, M. A. (2021). *The impact of traceability on software maintenance and evolution: A mapping study*. Journal of Software: Evolution and Process, 33(10), e2374. DOI: https://doi.org/10.1002/smr.2374. citeturn0search1

2. Alturayeif, N., Hassine, J., & Ahmad, I. (2025). *Machine learning approaches for automated software traceability: A systematic literature review*. Journal of Systems and Software, 230, 112536. DOI: https://doi.org/10.1016/j.jss.2025.112536. citeturn0search0

3. Chen, Z., Yi, L., Nie, L., Zhao, Y., Liu, H., Shi, Y., & Song, W. (2026). *SoK: Systematizing Software Artifacts Traceability via Associations, Techniques, and Applications*. arXiv:2603.16208. https://arxiv.org/abs/2603.16208. citeturn0academia36

4. Hey, T., Fuchß, D., Keim, J., & Koziolek, A. (2025). *Requirements Traceability Link Recovery via Retrieval-Augmented Generation*. REFSQ 2025 Research Track. https://2025.refsq.org/details/refsq-2025-research-papers/8/Requirements-Traceability-Link-Recovery-via-Retrieval-Augmented-Generation. citeturn0search2

---

## F. Observations and Conclusions

Requirements traceability for ParcelResolve can be established with a modest set of high-value relationships connecting stakeholders and product goals (A2) to functional and non-functional requirements (A3), and those requirements to behavioural-model elements, scenarios and review decisions (A4). The matrix, evidence column and TIM make these relationships explicit and easier to maintain.

The LLM-supported approach is useful as a lightweight maintenance aid. Stable identifiers and a central traceability matrix provide the structure, while Claude can suggest candidate links and possible impact areas after a change. The group remains responsible for checking the evidence and deciding whether each link should be accepted. This is consistent with the literature, which shows both the value of traceability for change management and the limitations of fully automated link recovery.

The main unresolved points remain those already recorded in A3/A4, including quantitative NFR baselines, detailed escalation thresholds, supported communication channels, and possible incident-cancellation or duplicate-incident handling. A5 adds two traceability-specific open points: the terminal outcome for a permanently unmatched workflow and the eventual StakeholderNeed → ProductGoal relationship if that derivation is explicitly documented later.

The overall maintenance principle can therefore be summarised as:

**Artefact → Trace Link → Evidence → Change → Impact → Maintenance**

A trace link is useful only when its meaning and supporting evidence are clear, a change can be followed through its affected artefacts, and the relationship is reassessed when that evidence or meaning changes.

---

## G. Final Review with Claude and Decision Record

A final Claude review was performed after restructuring the assignment. The purpose was to check whether the accepted review findings had actually been incorporated into the main sections rather than remaining only in a decision table.

### G.1 Corrections Applied

| Review Item | Applied Change |
|---|---|
| Prototype-component traceability | Added an explicit statement that prototype-component links are not applicable at the current project stage. |
| Inter-requirement dependencies | Added FR-13 → FR-11/FR-12, FR-20 → FR-19 and NFR-07 → NFR-06 to A.1.7 and the matrix. |
| Scenario coverage wording | Changed A.1.4 so that all FRs are described as model-mapped, while only selected requirements are described as scenario-validated. |
| Requirement revision vs future refinement | Distinguished applied A3 requirement revisions from A4 findings C-03/C-06 that remain future refinements. |
| `constrains` direction | Removed the incorrect FR → ModelElement use and kept `constrains` as NFR → FR/ModelElement. |
| Second dependency example | Added FR-11/FR-12 → FR-13 to the matrix. |
| Bidirectional impact analysis | Added both forward and backward change-impact examples in C.2. |
| Scope-control evidence | Added a concrete example showing how an implementation-specific proposal can be rejected rather than added to the requirement baseline. |
| Broken-link definition | Defined a potentially broken link as one whose source or target artefact changed in a way that may alter the relationship's meaning or evidence. |
| LLM self-review limitation | Added the risk that repeated use of the same LLM can reinforce earlier suggestions, with human review as the mitigation. |
| Literature | Reduced the review to four verified sources and removed the previously unverified reference set and unsupported numerical claim. |
| Literature argument | Reorganised the discussion around the chain: change-management value → maintenance cost → automation → imperfect automation → human validation. |
| Requirement-change maintenance | Added a nine-step maintenance process and the FR-09 ParcelResolve example. |

### G.2 Deferred / Not Asserted Items

Two points remain deliberately unresolved rather than being invented:

- **StakeholderNeed → ProductGoal (`motivates`):** not added because A2 does not explicitly document which stakeholder need motivated each product goal.
- **Concrete version-control mechanism for the matrix:** the process describes the matrix as a maintained project artefact without claiming a specific storage/versioning technology that the group has not formally selected.

### G.3 Review Limitation

Claude was used as a review aid, not as an independent authority. The same model was used in earlier assignments, so the review cannot be treated as fully independent from previous AI-assisted suggestions. The final trace links, evidence, literature selection, revisions and decisions remain the responsibility of the group.

---

## AI Assistance Disclosure

AI assistance (Claude) was used, consistently with Assignments 2–4, to help organise sections, suggest candidate trace links for human review, locate and verify recent literature, and perform the final review recorded in Section G. The traceability relationships, evidence selections, tool approach, literature interpretation and final decisions were reviewed and determined by the group. AI suggestions were not accepted automatically; they were considered against the project artefacts and either applied, modified, deferred, or left unasserted based on the group's reasoning.
