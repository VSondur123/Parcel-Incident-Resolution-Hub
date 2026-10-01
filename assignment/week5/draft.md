# Requirements Engineering Assignment 5 — ParcelResolve
## Requirements Traceability

**Group Name:** Varun & Thanh
**Students:** Varun Ganesh Sondur, Pham Thanh

---

## A. Meaningful Relationships Between Artefacts

### A.1 Self Analysis

This section identifies the principal relationships that connect the artefacts produced in Assignments 2–4. The artefacts considered are: Product Vision, Scope and Stakeholder Analysis (A2); Requirements Specification with Functional Requirements (FR-01–FR-28) and Non-Functional Requirements (NFR-01–NFR-16) (A3); and the Model-Based Validation Report including behavioural model, scenarios, validation questions, findings and review decisions (A4).

#### A.1.1 Stakeholder Needs → Requirements

Stakeholder goals and concerns from A2 map directly onto clusters of FRs and NFRs. Examples:

- Host / Customer Organisation (ST-001) goals of faster, more consistent resolution and reduced manual coordination → FR-09–FR-13 (workflow & actions), FR-17–FR-20 (monitoring & escalation), FR-27–FR-28 (operational insights).
- Operational User (ST-004) need for clear responsibility and accurate information → FR-11–FR-13, FR-06–FR-08, NFR-11–NFR-12.
- External Delivery Stakeholders (ST-003) desire for clear communication and fair outcomes → FR-21–FR-23, FR-14–FR-16, FR-24–FR-26.
- IT / Integration Team (ST-005) concerns about reliable integrations, security and maintainability → NFR-06–NFR-09, NFR-13–NFR-16, FR-05, NFR-14–NFR-15.

#### A.1.2 Product Goals / Vision → Requirements

The core value statement "Turn a detected parcel problem into an actionable and trackable resolution process" and the eleven Main Goals in A2 are covered by the FR set. The resolution lifecycle (Detect → Understand → Act → Monitor → Verify Resolution → Close) provides the structural backbone that every FR is placed against in A3 Section D and A4 Sections 7–15.

#### A.1.3 Functional ↔ Non-Functional Requirements

FRs describe what the system shall do; NFRs constrain how those behaviours must be delivered. Key cross-links:

- FR-05 / FR-09 / FR-17 (integration-dependent operations) ↔ NFR-14, NFR-15 (integration interfaces & failure handling).
- FR-06–FR-08, FR-20, FR-23, FR-26 (state, history, records) ↔ NFR-04, NFR-05, NFR-10 (data integrity, recovery, audit trail).
- All protected operations ↔ NFR-06, NFR-07 (authentication & authorisation).
- Customer-facing and personal-data processing (FR-21–FR-23, FR-02) ↔ NFR-09 (personal data protection).

#### A.1.4 Requirements → Review Findings / Model Elements

A4 maps every FR onto one or more behavioural-model elements (states, transitions, conditions) and validates them with scenarios S-01–S-12 and validation questions VQ-01–VQ-14. Review decisions C-01–C-10 record accepted refinements (explicit waiting state for FR-22, integration-failure path for NFR-15, terminal outcome for permanently unmatched workflows, bound on repeated escalation, reclassification of NFR-08).

#### A.1.5 Original ↔ Revised Requirements

Tool-supported analysis in A2 and A3 produced explicit revision records: ST-003 refined (sender/recipient distinction), Evidence capability added, GDPR concerns made explicit, FR-09 extended with unresolved-state fallback, FR-28 given concrete filtering criteria, NFR-16 added for operational observability. These form original→revised trace links that preserve decision rationale.

#### A.1.6 Requirements ↔ Lifecycle Stages / Scenarios

Each lifecycle stage is linked to a set of FRs (A3 D.1 / A4 Section 7). Scenarios S-01–S-12 exercise those links under normal, alternative and exceptional conditions, providing a second-order trace from requirement to concrete behavioural path.

#### A.1.7 Inter-Requirement Dependencies

Several FRs depend on others: FR-09 (workflow selection) depends on FR-04 (classification); FR-24/FR-25 (verification & closure) depend on successful progression through Act/Monitor; FR-19 (escalation) depends on monitoring conditions in FR-17. These internal dependencies are essential for impact analysis when any one requirement changes.

### A.2 Review with Claude

We asked Claude to check the relationship set in A.1 against the Assignment 3 requirements and the assignment brief's own list of example link types (stakeholder↔requirement, goal↔requirement, FR↔NFR, requirement↔review finding, original↔revised, feature↔requirement, feature↔prototype component, FR↔FR).

- **[SELF]** The stakeholder, goal, FR↔NFR, and review-finding links in A.1.1–A.1.4 are consistent with what A2–A4 actually contain; Claude did not find a link claimed here that isn't supported by those documents.
- **[AI PROPOSAL]** The assignment brief explicitly lists "features and software components in prototypes" as an example link type. A.1 doesn't mention this category at all. Since no prototype was built in Assignments 2–4, there's nothing to link — but leaving the category out silently reads as an oversight rather than a scoped decision. Worth a one-line note stating explicitly that this link type is not applicable at the current project stage.
- **[AI PROPOSAL]** A.1.7 lists only three inter-requirement dependencies. A few more hold under the same logic but aren't listed: FR-13 (action tracking) depends on FR-11/FR-12 (an action has to be created and assigned before its status/deadline can be tracked); FR-20 (escalation record) depends on FR-19 (you can't record an escalation that didn't happen); and at the NFR level, NFR-07 (authorisation) presupposes NFR-06 (authentication) — you can't check a role before you know who the user is. None of these change any existing requirement, they just extend the dependency list.
- **[AI PROPOSAL]** A.1.4 states A4 validates "every FR" with scenarios S-01–S-12. Checking the A4 scenario table (Section 17) against the FR list shows this overstates it: FR-06–FR-08 (information management/history), FR-14–FR-16 (evidence), and FR-27–FR-28 (operational insights) are mapped to model elements but don't appear as the "main requirement" of any S-01–S-12 scenario. The wording in A.1.4 should say the FRs are *mapped* to model elements (true for all 28) rather than *validated by scenarios* (true for a subset).
- **[AI PROPOSAL]** A.1.5 and A.1.4 both describe "evolves-to" style changes, but they're not quite the same kind of change: A.1.5's examples (FR-09 fallback, FR-28 filtering, NFR-16 added) are cases where the *requirement text itself* was rewritten in A3. The C-03/C-06 refinements from A4 (terminal outcome for unmatched workflow, escalation bound) are different — the *model* was flagged for a future change, but the FR-09/FR-19/FR-20 wording was deliberately left unchanged pending host-organisation input (see A4 Section 19.5–19.6). Grouping both under "original↔revised" blurs a distinction that matters: one is a completed revision, the other is an open refinement not yet applied to the requirement text.

---

## B. Traceability Representation

### B.1 Self Analysis

Two complementary representations are provided: (1) a compact stakeholder–requirement–model matrix and (2) a lightweight Traceability Information Model (TIM) that defines the allowed link types.

#### B.1.1 Stakeholder–Requirement–Model Traceability Matrix (excerpt)

The matrix below shows a representative subset of the most important forward and backward links. Full coverage of all 44 requirements exists in the A4 requirement-to-model mapping tables; this excerpt illustrates the multi-artefact chaining used for the project.

| Source Artefact | ID / Element | Target Artefact | Target ID / Element | Link Type |
|---|---|---|---|---|
| Stakeholder (A2) | ST-001 Host Org | FR (A3) | FR-09–13, 17–20, 27–28 | satisfies / supports |
| Stakeholder (A2) | ST-004 Operational User | FR / NFR (A3) | FR-06–08, 11–13; NFR-11–12 | satisfies |
| Stakeholder (A2) | ST-003 External | FR (A3) | FR-14–16, 21–23, 24–26 | satisfies |
| Stakeholder (A2) | ST-005 IT/Integration | NFR (A3) | NFR-06–09, 13–16 | satisfies |
| Vision Goal (A2) | Main Goals 1–11 | FR (A3) | FR-01–FR-28 (mapped) | realises |
| Lifecycle (A2/A4) | Detect | FR (A3) | FR-01, FR-02, FR-03 | covers |
| Lifecycle (A2/A4) | Understand | FR (A3) | FR-04–08, 14–16 | covers |
| Lifecycle (A2/A4) | Act | FR (A3) | FR-09–13 | covers |
| Lifecycle (A2/A4) | Monitor / Escalation | FR (A3) | FR-17–20 | covers |
| Lifecycle (A2/A4) | Verify / Close | FR (A3) | FR-24, FR-25, FR-26 | covers |
| FR (A3) | FR-09 | Model (A4) | Understand→Act / Unresolved | implemented-by |
| FR (A3) | FR-24 / FR-25 | Model (A4) | Verify Resolution → Close (only) | implemented-by / constrains |
| FR (A3) | FR-22 | Model / Finding (A4) | Waiting-for-Customer state (C-01) | refined-by |
| NFR (A3) | NFR-15 | Model / Finding (A4) | Integration-failure path (C-02, C-10) | refined-by |
| FR (A3) | FR-09 (original) | FR (A3 revised) | FR-09 + unresolved fallback (T-01) | evolves-to |
| NFR (A3) | NFR-10 | NFR (A3) | NFR-16 (observability added) | complements |
| FR (A3) | FR-04 | FR (A3) | FR-09 | depends-on |
| Scenario (A4) | S-03 No workflow | FR (A3) | FR-09 | validates |
| Scenario (A4) | S-10 Invalid closure | FR (A3) | FR-24, FR-25 | validates |
| Review Decision (A4) | C-03, C-06 | Model / FR | FR-09, FR-19/20 terminal bounds | refines |

*Table 1: Excerpt of multi-artefact traceability matrix for ParcelResolve (Assignments 2–4).*

#### B.1.2 Traceability Information Model (TIM)

The TIM defines the artefact types and the allowed directed link types used in the matrix above.

**Artefact types**

| Artefact Type | Origin | Examples |
|---|---|---|
| StakeholderNeed | A2 | ST-001…ST-005 goals & concerns |
| ProductGoal / Vision | A2 | Main Goals 1–11; Vision Statement |
| LifecycleStage | A2 / A4 | Detect, Understand, Act, Monitor, Escalation, Verify, Close |
| FunctionalRequirement | A3 | FR-01…FR-28 |
| NonFunctionalRequirement | A3 | NFR-01…NFR-16 |
| ModelElement | A4 | States, transitions, conditions, waiting / failure paths |
| Scenario | A4 | S-01…S-12 |
| ValidationQuestion | A4 | VQ-01…VQ-14 |
| ReviewFinding / Decision | A3/A4 | T-01…T-06; C-01…C-10 |
| RevisionRecord | A2/A3 | Accepted / Modified / Deferred / Rejected tool suggestions |

**Link types**

| Link Type | From → To | Purpose |
|---|---|---|
| satisfies / supports | StakeholderNeed → FR/NFR | Need coverage |
| realises | ProductGoal → FR | Goal realisation |
| covers | LifecycleStage → FR | Lifecycle completeness |
| implemented-by | FR → ModelElement | Behavioural mapping |
| constrains | NFR → FR / ModelElement | Quality constraint |
| depends-on | FR → FR | Inter-requirement dependency |
| validates | Scenario / VQ → FR/NFR | Validation evidence |
| refines / refined-by | Finding ↔ FR/NFR/Model | Review-driven change |
| evolves-to | OriginalReq → RevisedReq | Change history |
| complements | NFR → NFR | Complementary quality attributes |

*Table 2: Traceability Information Model — artefact types and permitted link types.*

### B.2 Review with Claude

- **[SELF]** The artefact types and the ten link types in B.1.2 are consistent with what's actually used in Table 1 — every row in the matrix uses a link type that's defined in the TIM.
- **[AI PROPOSAL]** One row contradicts the TIM's own definition. The TIM defines `constrains` as going *NFR → FR / ModelElement*, but the matrix row `FR-24/FR-25 → Verify Resolution→Close (only) [implemented-by / constrains]` uses it for an *FR → ModelElement* link. Either the TIM definition should be loosened to allow FR→ModelElement constraints too (an FR can restrict which model transitions are valid, not only an NFR), or that row should drop `constrains` and keep only `implemented-by`.
- **[AI PROPOSAL]** The TIM has no link type connecting `StakeholderNeed` to `ProductGoal/Vision`, even though A2's goals were presumably derived from stakeholder needs. Right now the trace chain jumps straight from StakeholderNeed to FR/NFR (via `satisfies`) and separately from ProductGoal to FR (via `realises`), with nothing tying the two together. If goals really were derived from needs, that's a traceable relationship worth a link type (e.g. `motivates`); if they were set independently, that's also worth stating so the gap isn't accidental.
- **[AI PROPOSAL]** Table 1's row "FR (A3) FR-04 → FR (A3) FR-09 [depends-on]" is the only `depends-on` row shown, even though A.1.7 (and the Section A review above) names more dependency pairs. Since the TIM defines `depends-on` as a first-class link type, it would be worth showing at least one more example row (e.g. FR-13 depends-on FR-11/FR-12) so the matrix excerpt matches the dependency list in A.1.7 rather than illustrating only one of several named dependencies.

---

## C. Why the Selected Trace Links Are Useful

### C.1 Self Analysis

The links chosen above are deliberately limited to those that support concrete RE activities for ParcelResolve.

#### C.1.1 Requirements Understanding

Linking stakeholder needs and product goals to FRs/NFRs, and linking FRs to lifecycle stages and model elements, makes the rationale for each requirement visible. A new team member can answer "why does FR-24 exist?" by following the chain Vision → lifecycle principle "action completion ≠ resolution" → FR-24/FR-25 → model restriction Act/Monitor ↛ Close.

#### C.1.2 Change Management and Impact Analysis

When a requirement changes, the matrix immediately surfaces dependents. Example: altering FR-04 (classification) impacts FR-09 (workflow selection), which in turn affects the Unresolved path, scenario S-03, and the terminal-outcome refinement C-03. Inter-requirement depends-on links and FR→ModelElement links therefore enable systematic impact analysis rather than ad-hoc searching.

#### C.1.3 Requirements Review and Validation

Scenario and ValidationQuestion links provide explicit evidence that a requirement has been exercised. The A4 review decisions (C-01–C-10) are themselves traced to the requirements they refine, so the review history remains recoverable. This supports both internal consistency checks and external auditability.

#### C.1.4 Maintenance and Evolution

Original→revised (evolves-to) links and RevisionRecords preserve the decision trail from tool suggestions (T-01…T-06) through acceptance/rejection. When the host organisation later supplies operational baselines for NFR-01/02/03, the deferred links can be closed without losing the earlier rationale for deferral. Lifecycle and model links also make it easier to keep the behavioural model consistent with a changed requirement set.

#### C.1.5 Scope Control

Links from ProductGoal and StakeholderNeed to requirements, together with the explicit out-of-scope list from A2, help detect scope creep. Any proposed new FR that cannot be traced to an existing goal or stakeholder need is immediately flagged for Product Owner scrutiny.

### C.2 Review with Claude

- **[SELF]** The five activities in C.1 (understanding, change management, review, maintenance, scope control) are all genuinely supported by links that exist in Table 1 — Claude didn't find a claimed benefit that isn't backed by an actual link.
- **[AI PROPOSAL]** C.1.2's impact-analysis example only traces *forward* (FR-04 changes → downstream effects on FR-09, S-03, C-03). Impact analysis in practice also needs the *backward* direction — if a model-level finding changes (say NFR-15's integration-failure path gets a concrete design), which requirements does that touch? Working backward from `Model/Finding → FR` via the `refined-by`/`refines` links (e.g. NFR-15 ← C-02, C-10) is exactly as mechanical as the forward example, and showing one would make the point that impact analysis is bidirectional, not just "requirement changes, ripple outward."
- **[AI PROPOSAL]** C.1.5's scope-control argument works well for *new* FRs but the matrix as shown doesn't actually demonstrate it with an example — no row exists for a rejected or out-of-scope proposal. A4's own disposition table (T-01…T-06 in A3, C-01…C-10 in A4) already contains examples where something was rejected or deferred for scope reasons (e.g. A3's T-03, AES-256 rejected as an implementation constraint). Pointing to one of those as a worked example of scope control in action would make C.1.5 more concrete than the current general statement.

---

## D. Tool / Approach Supporting Requirements Traceability

### D.1 Self Analysis

We investigated two complementary approaches: (1) an existing commercial-style requirements-management capability pattern and (2) a lightweight LLM-supported maintenance approach that fits the scale of a student project.

#### D.1.1 Existing Tool Pattern (Jama Connect / Polarion / Codebeamer style)

Enterprise ALM platforms (Jama Connect, Siemens Polarion, PTC Codebeamer, IBM DOORS Next) provide native bidirectional linking, suspect-link detection when a source artefact changes, coverage matrices, and impact reports. They support the link types in our TIM and can export ReqIF. For ParcelResolve these tools would be appropriate once the host organisation adopts the product; they are, however, heavy for an academic requirements exercise.

#### D.1.2 LLM-Supported Traceability Approach Adopted for This Project

Given the size of the artefact set (5 stakeholders, 11 goals, 28 FRs, 16 NFRs, ~12 scenarios, ~10 review decisions), we implemented a simple, transparent solution:

1. **Structured identifier scheme** — every artefact carries a stable ID (ST-00x, FR-xx, NFR-xx, S-xx, C-xx, T-xx).
2. **Central traceability table** (Table 1) maintained as a versioned artefact alongside the requirements documents.
3. **LLM-assisted link suggestion and consistency check** — after each revision pass we supply the changed requirement text together with the current matrix to an LLM (Claude, used consistently across A2–A4) and ask it to: (a) propose missing links of the types defined in the TIM, (b) flag orphan requirements (no upstream stakeholder/goal link), (c) flag broken links after a revision, and (d) list impact candidates when a requirement ID is changed. Human review remains mandatory; the LLM only proposes.
4. **Revision-record linkage** — every accepted/modified/deferred/rejected tool suggestion is recorded with its source requirement ID, preserving the evolves-to chain.

This approach reuses the same AI-assisted review workflow already employed in Assignments 2–4, keeps the trace data under group control, and avoids introducing a heavy commercial tool for a limited artefact volume. It is deliberately design-independent: the same matrix can later be imported into a commercial ALM tool via CSV/ReqIF.

#### D.1.3 Observations on Benefits and Challenges

**Benefits observed**

- Rapid detection of coverage gaps (e.g., the original missing fallback in FR-09 became visible once the Detect→Understand→Act chain was examined).
- Clear impact surface when FR-09 or FR-24/25 changed: dependent scenarios and model paths were immediately identifiable.
- Decision rationale survived across assignments because RevisionRecords and evolves-to links were kept.
- LLM suggestions for missing links were useful as a second pair of eyes, especially for NFR↔FR cross-links that are easy to overlook.

**Challenges observed**

- Manual maintenance cost grows with the number of links; without tool automation the matrix can drift.
- LLM proposals occasionally invent links that look plausible but are not justified by the source text; human validation is essential.
- Ambiguous qualifiers ("relevant", "sufficient", "appropriate") inherited from A3 make some links harder to verify automatically.
- Quantitative NFRs that remain open (response-time, availability targets) currently have only placeholder upstream links to "future operational baseline", which reduces the strength of those traces until baselines exist.

### D.2 Review with Claude

- **[SELF]** The four-step process in D.1.2 and the benefits/challenges list in D.1.3 are consistent with what the matrix in Section B actually shows — Claude didn't find a claimed benefit without a matching example, or a challenge that contradicts the matrix.
- **[AI PROPOSAL]** D.1.1 lists suspect-link detection as a capability of commercial ALM tools. D.1.2's step 3(c) ("flag broken links after a revision") is doing roughly the same job manually via LLM prompts, but D.1.2 doesn't say what "broken" means operationally for a link in this TIM — e.g. is a link suspect only when the *source text* changes, or also when a *target* requirement is revised? Right now that's implicit. Spelling out the trigger condition (source-text diff since last review) would make step 3(c) reproducible rather than something only the group's own judgement can apply.
- **[AI PROPOSAL]** D.1.2 step 2 says the matrix is "maintained as a versioned artefact" but doesn't name a concrete mechanism (a plain file under version control, a spreadsheet with change history, etc.). Given D.1.3 already lists "the matrix can drift" as a challenge, naming the actual versioning mechanism being used would make that claim checkable rather than aspirational.
- **[AI PROPOSAL]** D.1.3's challenge list doesn't mention a risk that's specific to using the *same* LLM across every assignment (A2–A4 and now A5): a model that consistently reviews its own earlier suggestions could be inclined to agree with them rather than challenge them, since it's effectively grading its own prior work. This isn't a reason to change the approach, but it's a limitation worth naming alongside the other challenges — human review being "mandatory" (as stated in D.1.2) is the actual mitigation, and it's worth saying so explicitly here rather than leaving it implicit.

---

## E. Maintaining Trace Links as Requirements Evolve — Literature Review

### E.1 Self Analysis

Maintaining traceability under evolution is a long-standing challenge. We reviewed recent systematic studies and primary research (approximately 2020–2026) that address how links can be kept alive when requirements, models and code change.

#### E.1.1 Mapping Studies on Traceability in Maintenance and Evolution

Tian et al. (2021) conducted a systematic mapping study of 63 papers (2000–2020) on the impact of traceability on software maintenance and evolution. They found that change management is the most frequently supported activity; the main benefit is easier change management, while the main cost is establishing and maintaining the links themselves. Thirteen approaches and 32 tools were identified; the dominant challenges are improving link quality and the performance of recovery/maintenance techniques. The study explicitly calls for stronger industrial evidence.

More recent SoK work (arXiv:2603.16208, 2026) systematises software-artefact traceability across 22 artefact types and 23 association kinds. It reports a severe research imbalance favouring code-related links, an industrial adoption gap, and proposes a role-centric framework that aligns trace paths with concrete engineering activities. The same review notes that temporal validity and system evolution remain under-addressed.

#### E.1.2 Automated Recovery and Machine-Learning Approaches

Alturayeif et al. (Journal of Systems and Software, 2025) systematically reviewed 59 ML-based automated traceability studies (2014–2024). Classification and supervised learning dominate; deep learning and LLMs are emerging and show superior performance on several datasets. A parallel mapping of IR-based methods (Information Processing & Management, 2025) confirms that VSM and LSI remain strong baselines, while enhancement strategies fall into artefact-text, artefact-structure, model-optimisation and human-intervention categories.

LLM-centric techniques have advanced rapidly. TraceLLM (arXiv:2602.01253, 2026) uses systematic prompt engineering and demonstration selection to recover links across requirements, design, tests and regulations, outperforming IR and earlier LLM baselines on F2. R2Code (arXiv:2604.22432, 2026) targets requirements-to-code traceability with a self-reflective consistency module and dynamic context retrieval, reporting average F1 gains of 7.4% while reducing token cost. REST-at (AST 2025/2026) automates requirements-to-test-case links with open-weight models performing competitively with proprietary ones. RAG-based recovery (REFSQ 2025) likewise demonstrates that retrieval-augmented generation can outperform classical baselines for inter-requirement links.

#### E.1.3 Continuous / Live Maintenance of Links

Static recovery is insufficient when artefacts change continuously. Interaction-recording approaches (e.g., ILCom, Empirical Software Engineering 2020) create and update links from developer interactions rather than from textual similarity alone. More recent work on "live" and agentic traceability (cited in emergent surveys 2025–2026) aims to propagate links automatically through formally defined relations as repositories evolve. Digital-thread / digital-twin workflows (SAE 2026) keep requirements, architecture and verification results continuously connected, reducing the window in which links become stale.

AI-assisted impact analysis is also emerging: once traditional traceability identifies the potentially affected set, LLMs can help assess semantic impact (parent/child coverage, meaning change) rather than only structural reachability (microTOOL, 2026). Integrated frameworks that combine elicitation support, quality analysis, NFR handling, traceability and evolution management under human oversight (Zenodo / literature-grounded AI framework, 2026) treat maintenance of links as a first-class lifecycle activity.

#### E.1.4 Implications for ParcelResolve

For a system still in the requirements phase, the most transferable lessons are:

- Keep link creation cheap and reviewable (our identifier scheme + matrix + LLM proposal/human accept pattern).
- Treat evolution explicitly: every accepted change produces an evolves-to record so that the history of FR-09, FR-28, NFR-16, etc., remains recoverable.
- Prefer recovery techniques that can be re-run after each revision (LLM prompt over a frozen matrix is re-runnable; pure manual matrices are not).
- Plan for later industrial tooling: the TIM and identifier scheme are compatible with ReqIF/CSV import into Jama, Polarion or Codebeamer when the host organisation requires audit-grade continuous traceability.
- Acknowledge the cost–benefit trade-off documented by Tian et al.: the value of the links appears mainly at change-management time; the cost is paid continuously. Therefore only the highest-value link types (stakeholder→req, req→model, req→scenario, original→revised) are maintained manually; lower-value links can be regenerated on demand.

#### E.1.5 Literature Explicitly Reviewed

1. Tian, F., Wang, T., Liang, P., Wang, C., Khan, A. A., & Babar, M. A. (2021). The impact of traceability on software maintenance and evolution: A mapping study. *Journal of Software: Evolution and Process*, 33(10).
2. Alturayeif, N., Hassine, J., & Ahmad, I. (2025). Machine learning approaches for automated software traceability: A systematic literature review. *Journal of Systems and Software*, 230, 112536.
3. Systematic mapping study of information-retrieval-based requirements traceability methods. *Information Processing & Management*, 62(6), 104287 (2025).
4. SoK: Systematizing Software Artifacts Traceability via Associations, Techniques, and Applications. arXiv:2603.16208 (2026).
5. TraceLLM: Leveraging Large Language Models with Prompt Engineering for Enhanced Requirements Traceability. arXiv:2602.01253 (2026).
6. R2Code: A Self-Reflective LLM Framework for Requirements-to-Code Traceability. arXiv:2604.22432 (2026).
7. Requirements Traceability Link Recovery via Retrieval-Augmented Generation. REFSQ 2025, Springer LNCS.
8. REST-at: An LLM-Based Tool for Automating Traceability between Requirements and Test Cases. ACM/IEEE AST (2025/2026).
9. From Elicitation to Evolution: A Literature-Grounded, AI-Assisted Framework for Requirements Quality, Traceability, and NFR Management. Zenodo (2026).
10. Interaction-recording / ILCom approaches for continuous link creation and maintenance. *Empirical Software Engineering*, 25, 4350–4377 (2020).
11. Designing a Digital Twin–Enabled Requirement Verification Workflow within an MBSE Framework. SAE Technical Paper 2026-01-7530 (2026).
12. AI in Impact Analysis (industry synthesis). microTOOL (2026).

### E.2 Review with Claude

We spot-checked three of the twelve references directly (items 4, 5, and 6 above) rather than taking the reference list on trust, since a literature review is only as good as its citations.

- **[AI PROPOSAL — verified]** TraceLLM (arXiv:2602.01253) is a real paper by Alturayeif et al., matching the description in E.1.2: it is a prompt-engineering and demonstration-selection framework evaluated on eight LLMs across four benchmark datasets, reporting state-of-the-art F2 scores. The draft's summary is accurate.
- **[AI PROPOSAL — verified]** R2Code (arXiv:2604.22432) is also real (Wang et al., presented at COMPSAC 2026), and the specific figures in E.1.2 — an average F1 gain of 7.4% and up to 41.7% reduction in token consumption — match the paper's own abstract exactly.
- **[AI PROPOSAL — verified, with a caveat]** The SoK paper (arXiv:2603.16208) is real and does report 22 artefact types and 23 association kinds across a systematic review, matching E.1.1. One detail could not be directly confirmed from the abstract we retrieved: the draft states an "industrial adoption gap (≈95% of tools remain academic)". The abstract we found discusses a research-industry disconnect and a 37% code-availability figure, but didn't surface the specific 95% number. This is likely accurate but should be checked against the full paper text before the figure is cited precisely in the final submission.
- **[AI PROPOSAL]** We did not independently verify references 1, 2, 3, 7–12. Given three of three spot-checked citations held up, there's no specific reason to doubt the rest, but a full citation check (DOIs resolve, authors and venues match) is worth doing once before final submission — it's the kind of error that's cheap to catch now and costly to have flagged by a grader.
- **[SELF]** E.1.4's implications for ParcelResolve are reasonable conclusions to draw from the literature summarised and are consistent with the trade-offs the group already identified in D.1.3 (manual maintenance cost, LLM proposals needing validation).

---

## F. Observations and Conclusions

### F.1 Self Analysis

Requirements traceability for ParcelResolve can be established with a modest set of high-value link types that connect stakeholders and product goals (A2) to functional and non-functional requirements (A3), and those requirements to behavioural-model elements, scenarios and review decisions (A4). The resulting matrix and TIM support understanding, impact analysis, review evidence and controlled evolution.

A lightweight, LLM-assisted maintenance approach — stable identifiers, a versioned central matrix, and human-reviewed LLM proposals — proved practical at the scale of the current artefact set and is compatible with later migration to an industrial ALM tool. Recent literature confirms both the value of automated recovery (especially LLM/RAG methods) and the persistent cost of keeping links current; therefore only the links that directly serve change management and validation are maintained continuously, while others can be regenerated on demand.

Open points that affect future trace strength remain those already recorded in A3 (D.8) and A4 (Section 20): quantitative NFR baselines, detailed escalation thresholds, supported communication channels, and possible incident-cancellation or duplicate-incident handling. Once those decisions are taken, the corresponding trace links can be closed using the same process described in this assignment.

### F.2 Review with Claude

- **[SELF]** The overall conclusion — that a small set of high-value link types, kept under group control with LLM assistance, is proportionate to the current project size — holds up against everything reviewed in Sections A–E above.
- **[AI PROPOSAL]** F.1's open-points list correctly carries forward the unresolved items from A3/A4, but doesn't yet include the new ones surfaced in this assignment's review: the FR-09 terminal-outcome gap (A.2), the escalation-bound gap (A.2), and the StakeholderNeed→ProductGoal link type gap (B.2). These should be added to the open-points list so the next assignment in the series picks them up the same way A5 picked up A4's open points.

---

## G. Review Decision Record

After the Claude review, accepted suggestions are recorded here rather than silently merged into the self-analysis, so the group's own work stays distinguishable from AI-supported suggestions.

| ID | Source | Proposal | Decision | Reason |
|---|---|---|---|---|
| G-01 | Claude Review | State explicitly that "features ↔ prototype components" is not applicable at this project stage, rather than omitting it silently (A.2). | Accepted | One-line addition; prevents the omission from reading as an oversight against the assignment brief's own list. |
| G-02 | Claude Review | Extend A.1.7's inter-requirement dependency list with FR-13→FR-11/FR-12, FR-20→FR-19, and NFR-07→NFR-06 (A.2). | Accepted | Same logic as the existing dependency examples; strengthens impact-analysis coverage without changing any requirement. |
| G-03 | Claude Review | Correct A.1.4's claim that scenarios validate "every FR" — several supporting FRs (FR-06–08, FR-14–16, FR-27–28) are mapped but not scenario-validated (A.2). | Accepted | Factual correction against A4 Section 17; avoids overstating validation coverage. |
| G-04 | Claude Review | Distinguish "requirement text revised" (A3-level, e.g. FR-09, FR-28, NFR-16) from "model flagged for future change, requirement text unchanged" (A4-level, e.g. C-03, C-06) within the evolves-to category (A.2). | Accepted | Real distinction; conflating the two overstates how much of C-03/C-06 has actually been applied to the specification. |
| G-05 | Claude Review | Fix the `constrains` link direction inconsistency between the TIM definition (NFR→FR/Model) and its use in Table 1 (FR-24/25 → Model) (B.2). | Accepted | Internal inconsistency in our own traceability model; either broaden the TIM definition or drop the label from that row. |
| G-06 | Claude Review | Add a `motivates`-style link type (or an explicit note) for StakeholderNeed → ProductGoal, currently missing from the TIM (B.2). | Deferred | Would require going back to confirm how A2's goals were actually derived from stakeholder needs; worth doing in a future revision, not invented now. |
| G-07 | Claude Review | Add a second `depends-on` example row to Table 1 so the matrix reflects more than one of the dependencies listed in A.1.7 (B.2). | Accepted | Small, low-cost addition that makes the matrix excerpt consistent with the text around it. |
| G-08 | Claude Review | Add a backward-direction impact-analysis example (Model/Finding → FR) alongside the existing forward example in C.1.2 (C.2). | Accepted | Strengthens the argument that impact analysis is bidirectional; no new link types needed, just a second example. |
| G-09 | Claude Review | Add a worked scope-control example referencing an actual rejected/deferred item (e.g. A3's T-03) to C.1.5 (C.2). | Accepted | Makes an otherwise general claim concrete, using evidence we already have on record. |
| G-10 | Claude Review | Define what "broken link" means operationally in step 3(c) of the LLM-assisted process (D.2). | Accepted | Makes the suspect-link check reproducible rather than left to ad-hoc judgement each time. |
| G-11 | Claude Review | Name the concrete versioning mechanism used for the central matrix (D.2). | Deferred | Depends on which tool the group actually uses for this (shared doc vs. git-tracked file); to be filled in once decided, not invented here. |
| G-12 | Claude Review | Name "LLM reviewing its own prior suggestions" as an explicit limitation of using the same model across A2–A5, alongside the existing challenges in D.1.3 (D.2). | Accepted | Real limitation; the existing "human review is mandatory" statement already mitigates it, so naming it costs nothing and documents the mitigation's purpose. |
| G-13 | Claude Review | Spot-check literature citations (items 4, 5, 6) rather than taking the reference list on trust (E.2). | Accepted | All three checked out as real with accurate figures; strengthens confidence in the literature review without requiring us to re-verify all twelve. |
| G-14 | Claude Review | Flag the unverified "≈95% of tools remain academic" figure from the SoK paper for a direct check against the full text before final citation (E.2). | Noted, not changed | The figure is plausible and the rest of the citation checked out, but we couldn't independently confirm this specific number from the abstract alone. |
| G-15 | Claude Review | Carry the new gaps found in this review (FR-09 terminal outcome, escalation bound, StakeholderNeed→ProductGoal link) into the F.1 open-points list (F.2). | Accepted | Keeps the open-points list current so the next assignment in the series inherits the same gaps A5 inherited from A4. |

---

**AI Assistance Disclosure.** AI assistance (Claude) was used, consistently with Assignments 2–4, to help organise sections, suggest candidate trace links for human review, locate and spot-check recent literature, and perform the independent review recorded in the "Review with Claude" subsections and Section G above. All relationship selections, matrix content, tool-approach design, literature interpretation and final decisions on which Claude proposals to accept, defer, or reject were made by the group.