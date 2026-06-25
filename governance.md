# MorphoDepot Organization — Governance Policy

> **Status: DRAFT v0.1 — for discussion, not yet adopted.** Prepared 2026-06-24 as a starting
> point. Everything here is a proposal: numbers in `[DECISION: …]` callouts and any specific
> threshold are meant to be debated and changed. Nothing in this document is in force until the
> founders (and the initial Steering Committee) formally adopt it (see §11).

---

## 1. Why this document exists

**The purpose of this policy is to define *who* may make which decisions, *how* those decisions are made, and *what
recourse* a member has when they disagree. It complements — and does not replace — the
[MorphoDepot Terms of Usage](terms.md), which is the agreement between the platform and its
users. Where the Terms grant discretion to "the organization administrators," this document
defines who those administrators are and how that discretion is exercised and checked.

---

## 2. Guiding principles

1. **Bounded authority, no unilateral irreversible power.** No single person — including the
   Director (§4.5) — may *single-handedly* take an irreversible action about a published dataset,
   a member, or the organization itself. Such actions always require a second authorized person
   (the "two-person rule," §5). Roles below the Director rotate and are term-limited.
2. **Stewardship, not ownership.** Published archival datasets are a community resource under
   joint stewardship. The organization holds them in trust for the community and the public.
3. **Editorial independence.** Whether a dataset *meets the bar to be published* is an editorial
   judgment, made by editors, separate from who *runs* the organization.
4. **Transparency by default.** Governance decisions are recorded; the rules and the reasoning
   are visible to members. Private handling is reserved for personal, legal, or safety matters.
5. **Due process.** Members are entitled to clear criteria, notice, a reason, and an appeal for
   any adverse decision — except where the Terms permit emergency action (then the review comes
   after the fact).
6. **Durability of the scholarly record.** Citable datasets and their DOIs are part of the
   scientific record. Withdrawal is handled like a journal retraction (tombstone + reason), not
   a silent deletion.
7. **Sustainability beyond the founders and the current grant.** The org must be able to outlive
   any individual and any single funding source (§9).
8. **Founder-led now, community-governed by design.** MorphoDepot is, at this stage, actively led
   by its founding Director, who retains a standing administrative role until they choose to step
   down. This is deliberately **not** a "benevolent dictator for life" model: the Director's power
   is bounded (no unilateral irreversible action, no veto over policy or appeals), real authority
   is vested in the Steering Committee and the Editorial Board, and the stated goal is to fill the
   other roles with volunteers and broaden participation over time. Where positions go unfilled,
   the Director may cover them as a temporary fallback while actively recruiting — a stopgap, not
   the intended structure.

---

## 3. Scope

This policy governs: the `MorphoDepot` GitHub organization; **archival** datasets created within
it; organization membership; the shared infrastructure (Jetstream2 object storage, the GitHub
App / control plane, the onboarding app, RepoClerk); and the governance bodies themselves.

It does **not** govern **short-term** datasets, which live on members' personal GitHub accounts,
outside the organization, under their sole control (see Terms §2 and the
[archival guidelines](MorphoDepot-archival-guidelines.md)).

---

## 4. Roles and bodies

Authority is layered. Most day-to-day work needs no central body; the central body exists for
the decisions that are irreversible, contested, or organization-wide.

**Right-sized on purpose.** MorphoDepot is a small project, not a scholarly society — there are no
elections, dues, or standing bureaucracy. These roles describe *who may decide what*, not a payroll
or an org chart that must be filled. Several roles may be held by the same few people today; they
are written down so that **as the community grows, authority can spread without re-litigating the
rules**. Roles are filled by people volunteering and being appointed — never by campaign — and the
structure formalizes (larger committee, fixed terms) only if and when there are enough hands to
warrant it.

### 4.1 Members
Individuals onboarded via ORCID (one person, one ORCID iD, one GitHub account). Members may
create and curate archival datasets. Membership is open to everyone who intends to create and
maintain archival datasets and who accepts the Terms and Code of Conduct.

### 4.2 Curators (per dataset)
The creator of an archival dataset is its **Curator**: responsible for reviewing and merging
contributions, cutting releases, and crediting contributors. Curatorship is a *responsibility*,
not administrative ownership of the repository (Terms §2). See §6.7 for what happens when a
curator becomes inactive.

### 4.3 Editorial Board (publication review)
A panel of members (the current `MD-reviewers` team) who decide whether a dataset or release
**meets the bar to be made public**. This is a *validity/soundness* check in the spirit of a
journal handling editor (the PLOS ONE model) — not a judgment of scientific importance, and not
a re-segmentation. Automated checks run first; a human editor signs off on what automation
cannot judge. Editors serve fixed, renewable terms and act independently of the Steering
Committee on individual publication decisions.

> `[DECISION: Editorial Board size and term. Proposal: ≥3 active editors, 1-year renewable terms,
> a named Editor-in-Chief or rotating chair to break ties and assign cases.]`

### 4.4 Organismal Domain Review Teams
Teams organized by taxon / organismal domain (e.g., fishes, mammals, plants). They provide
domain expertise for review and curation within their area. **Membership is by invitation from
the Steering Committee or Editorial Board, informed by the "research and organismal focus" a
member provides at onboarding — it is not self-selected.** Domain teams are advisory to editors
on domain-specific questions.

### 4.5 Director
MorphoDepot has a standing **Director** — currently the founding PI, A. Murat Maga (`@muratmaga`) —
responsible for the day-to-day running and administration of the organization, chairing the Steering
Committee (§4.7), setting its agenda, and representing MorphoDepot to its funder, host institutions,
and the wider community. **The Director is not term-limited and holds the role until they resign or
step down.** The role is deliberately bounded so it is leadership, not autocracy:
- the Director may decide **routine and operational** matters alone, but **cannot single-handedly
  take any irreversible action** — those require the two-person rule (§5);
- the Director **has no veto** over Steering Committee decisions, policy amendments, editorial
  decisions, or appeals;
- the Director recuses, like anyone else, from matters in which they have a personal stake.

On the Director's resignation or sustained unavailability, the Steering Committee selects a successor
Director by the normal process — the *role* persists; no one holds it by right.

### 4.6 Technical Director
The **Technical Director** — currently Steven Pieper (`@pieper`), the platform's principal engineer —
leads the engineering and operation of the shared infrastructure (the GitHub App / control plane,
object storage, the onboarding app, RepoClerk, CI runners) and the maintainers who keep it running.
The Technical Director sits **ex officio** on the Steering Committee for technical input and is **not
expected to drive policy** — the role is engineering and operations, not governance.

**Operational access is not governance authority** — neither the Technical Director nor any
maintainer can, on their own, withdraw a dataset or remove a member. But because an integrity check
needs a *second pair of eyes* rather than a second policymaker, the Technical Director (or another
maintainer) **may serve as the second authorizer for the two-person rule** (§5) — co-signing that an
irreversible action was properly decided, without having to own the policy judgment behind it.

### 4.7 Steering Committee (the governance body)
The collective body that holds organization-level authority: organization policy (including this
document); appointing and removing editors and domain-team leads; final decisions on
withdrawal/takedown and membership removal; appeals (§7); and infrastructure/budget oversight.

- **Composition.** The Director (chair, §4.5) plus the **Editor-in-Chief** (§4.3) and the **Technical
  Director** (§4.6), both ex officio, plus **one or more community members who volunteer and are
  appointed to serve**. There are no elections — willing volunteers are invited and confirmed by the
  sitting Committee. The aim is to seat **at least one or two voting members who are neither the
  Director nor staff**, so the Director is not the sole decider — but the body stays as small as the
  available volunteers allow. `[DECISION: a target size (e.g. 3–6) understood as a goal, not a
  precondition to act.]`
- **Terms & rotation (volunteer seats).** Volunteers serve **as long as they are willing and
  active**; there are no fixed elections or campaigns. The Committee reaffirms the roster
  `[DECISION: annually]`; anyone may step down at any time; rotation is encouraged but not forced
  when few volunteers are available.
- **Decisions.** Quorum = `[DECISION: a majority of seated members, including at least one
  non-Director voting member]`. Routine decisions by simple majority; **irreversible decisions
  (withdrawal, takedown, member removal, amending this document) require a higher bar** —
  `[DECISION: Proposal: 2/3 of seated members]`. The Director chairs and may break ties, but does
  not otherwise outvote the body and holds no veto. No one decides a matter in which they have a
  personal stake (recusal, §5).

### 4.8 Advisory Board (optional)
`[DECISION: whether to add a non-voting external advisory board — senior community members,
a host-institution representative, an ethics/data-stewardship advisor — to give the Steering
Committee outside perspective without operational entanglement.]`

---

## 5. How decisions are made

- **Conflict of interest / recusal.** Anyone with a personal stake in a matter (their own
  dataset, their own membership, a close collaborator's) recuses from deciding it. Recusals are
  recorded.
- **Two-person rule for irreversible actions.** Any action that cannot be undone — making a
  published dataset private, deleting content, removing a member, hand-minting/withdrawing a DOI —
  requires authorization by **at least two** people: the deciding Director/Committee member plus a
  second authorized person who is not the requester. The second authorizer may be another Steering
  Committee member or the Technical Director (§4.6) acting as an integrity check. This is the concrete
  mechanism that prevents sole-admin control even while the org is small and founder-led.
- **Documentation.** Every governance decision is logged with date, who decided, the reason, and
  the outcome (§8).
- **Default to the lighter body.** A decision is escalated to the Steering Committee only if it
  is irreversible, contested, organization-wide, or an appeal. Editors decide publications;
  curators decide contributions; the Committee does not relitigate those by default.

---

## 6. Operational policies

### 6.1 Membership admission
Open ORCID-based onboarding (join.morphodepot.org). Admission is automatic on a valid,
email-verified ORCID + GitHub identity and acceptance of the Terms and Code of Conduct. The
Steering Committee may pause or condition admission only for documented abuse or legal reasons.

### 6.2 Staging window — how long before a dataset must go public
A newly created archival dataset is **staged privately** while the curator prepares it. To keep
private staging from becoming indefinite private hosting on shared infrastructure:

- A staged dataset that has **not been submitted for publication within `[DECISION: 14 days]`**
  of creation is flagged and then discarded (its working copy and staged source volume removed).
  *(14 days is the value currently enforced in the extension; adopt, lengthen, or add an
  extension-on-request mechanism.)*
- The curator receives reminders before discard. `[DECISION: reminder cadence — e.g., day 7 and
  day 12 — and whether a one-time extension can be requested.]`
- Discarding a *staged* (never-public) dataset is **not** a governance action — it is automatic
  and reversible by simply re-creating; only *published* datasets are protected (§6.5).

### 6.3 Publication review (the editorial gate)
When a curator requests publication, automated checks run first (terminology, real specimen
metadata, plausible voxel size, a license, a representative screenshot, baseline built on the
source volume). On pass, an editor performs the human check and either **approves** (the dataset
goes public and becomes citable on release) or **requests changes** (it returns to the curator
with a specific list).

- **Turnaround target.** `[DECISION: Proposal: editors aim to act within 10 working days; if no
  editor acts within N days the case is reassigned by the chair.]`
- **What approval certifies.** That the dataset is *sound and well-formed*, not that it is
  finished or important. Accuracy is the community's ongoing job.
- **Editor independence.** A publication decision is the editor's; the Steering Committee does
  not overrule an individual editorial decision except through the appeal process (§7).

### 6.4 Releases and DOIs
Releases of archival datasets are minted citable DOIs through Zenodo (a version DOI per release
plus a concept DOI for the latest). **A DOI, once minted, is permanent** — this is what makes
the dataset citable and is why withdrawal is handled as retraction, not deletion (§6.5).

### 6.5 Making a published dataset private, or withdrawing it
Publishing an archival dataset is a **one-way door**: the curator alone **cannot** un-publish,
hide, or delete it (Terms §2). Reverting a public dataset to private — or withdrawing it — is an
exceptional governance action.

- **Who may request:** the curator, any member raising a concern, or an editor/Committee member.
- **Grounds (illustrative):** a serious error invalidating the data; a rights/licensing problem;
  an ethical or legal problem (e.g., suspected non-de-identified human-subject data — see Terms
  §4); a credible takedown claim.
- **Who decides:** the Steering Committee under the two-person, higher-bar rule (§5). Editors
  advise; the curator is heard first.
- **What actually happens to a DOI'd dataset:** because the DOI is permanent, the dataset is
  **tombstoned**, not erased — the landing page/record is replaced with a withdrawal notice
  stating that it was withdrawn and (to the extent appropriate) why, and the version is removed
  from active discovery. Outright deletion is reserved for legal compulsion (§6.6).
- **Curator-requested withdrawal** (author changed their mind) is honored where no third party
  has built on the dataset and no legal/credit obligation prevents it; otherwise it is
  tombstoned with a neutral notice rather than deleted.
- **Record:** every withdrawal is logged with the decision, grounds, and notice text.

> `[DECISION: distinguish "make private again" (recoverable, e.g., to fix a fixable problem) from
> "withdraw" (permanent tombstone). Proposal: prefer request-changes/new-release to fix problems
> in place; reserve private-again for active investigations and withdrawal for the rest.]`

### 6.6 Content takedown and emergency action
For content that is illegal, infringing, or unsafe (DMCA, export-control, suspected HSR/PII,
malware), the Terms (§7) permit **immediate** action by administrators without prior notice. In
that case: a technical maintainer may restrict access immediately to stop ongoing harm, but the
action is **reviewed by the Steering Committee within `[DECISION: 5 working days]`**, the
affected member is notified with a reason as soon as is lawful, and the appeal process (§7)
applies after the fact.

### 6.7 Curator continuity and orphaned datasets
Datasets outlive individuals. If a curator becomes unreachable/inactive for
`[DECISION: 6 months]` and a dataset has pending contributions or problems:
- The Steering Committee may **reassign curatorship** to another willing, qualified member
  (preferably from the relevant domain team), with notice to the original curator.
- Reassignment changes *responsibility*, not authorship/credit for prior work.
- A member may also voluntarily transfer curatorship at any time.

### 6.8 Code of Conduct, suspension, and removal
The organization adopts a Code of Conduct `[DECISION: adopt Contributor Covenant or equivalent]`.
Violations, or violations of the Terms, may lead to warning, temporary suspension, or removal:
- Routine warnings/suspension: handled by the Steering Committee or a delegated conduct contact.
- **Removal from the organization** is irreversible-class and requires the higher-bar,
  two-person rule (§5), with notice, a stated reason, and a right of appeal (except where the
  Terms permit emergency removal, reviewed after the fact).
- Removal does not retract a member's already-published, validly-licensed datasets (those stay
  as part of the record under their license), unless separate grounds for withdrawal exist.

---

## 7. Appeals and dispute resolution

Any member subject to an adverse decision may appeal.

- **What can be appealed:** a publication rejection that the curator believes misapplied the
  criteria; a withdrawal/make-private decision; a curatorship reassignment; a suspension or
  removal; a takedown.
- **To whom:** the appeal is heard by people **who were not the original deciders**. Proposal:
  - editorial decisions → appealed to the Editor-in-Chief or a different editor, then to the
    Steering Committee;
  - Steering Committee decisions → heard by an **Appeals panel** of Committee members who
    recused from the original decision, plus `[DECISION: optionally one advisory-board member]`.
- **Timeline:** appeal filed within `[DECISION: 30 days]`; a decision and written reason returned
  within `[DECISION: 30 days]`.
- **Finality:** the appeal outcome is final within the organization. It is recorded (§8).
- **Conflicts:** anyone involved in the original decision recuses from the appeal.

---

## 8. Transparency and records

- A **governance log** records every Committee decision (policy changes, editor/team
  appointments, withdrawals, removals, appeals) with date, decision, reason, and who decided —
  redacted only where personal/legal/safety concerns require.
- Editorial outcomes (approved/changes-requested) are visible on the dataset's tracking issue.
- This policy, the Terms, the Code of Conduct, and the current roster of the Steering Committee,
  editors, and domain-team leads are published. `[DECISION: where — the MorphoDepot/docs repo.]`
- `[DECISION: an annual report — datasets published, withdrawals, appeals, membership, storage
  use — to the community and the funder.]`

---

## 9. Sustainability and succession

- **Director / Technical Director departure.** The Director role is standing, but the person is not
  irreplaceable: on the Director's resignation or sustained unavailability, the Steering Committee
  selects a successor Director by the normal process. The Technical Director role is filled the same
  way. No role is hereditary. Operational credentials (org ownership, App keys, storage, DNS,
  domains) are held by **at least two** current Committee members/maintainers at all times — never
  by one person — and the holders are recorded.
- **Funding end / sunset.** `[DECISION: a written continuity plan.]` Because the platform is "no
  backup" by policy and runs on grant-funded infrastructure (NSF DBI/2301405; Jetstream2/ACCESS),
  the Committee maintains a plan to, on wind-down: freeze new submissions, preserve published
  datasets and DOIs (e.g., ensure Zenodo copies and an off-platform mirror persist), notify
  members in advance, and, if possible, transfer stewardship to a host institution or nonprofit.
- **No lock-in.** Members keep the right to maintain their own primary copies (Terms §5); the
  org is a coordination and certification layer, not the sole copy of record.

---

## 10. Relationship to other documents

- **Terms of Usage** — the user↔platform agreement. Governance operationalizes the discretion the
  Terms grant to "administrators." If the two conflict, `[DECISION: which controls — proposal:
  the Terms control for user obligations; this policy controls for how the org decides.]`
- **Code of Conduct** — behavioral expectations referenced in §6.8.

---

## 11. Adopting and amending this policy

- **Adoption.** This draft takes effect when the Director and an initial Steering Committee adopt
  it. The first act under it should be to **recruit and seat Committee members and an Editorial
  Board beyond the Director and Technical Director** — distributing the work and the authority is the
  entire point of the exercise.
- **Amendment.** Changes require the higher-bar vote of the Steering Committee (§5) after a
  comment period of `[DECISION: 2 weeks]` open to members. The version and date are recorded on
  every revision.
- **Review cadence.** `[DECISION: review at least annually.]`

---

## Appendix — open decisions to settle (checklist)

1. Steering Committee target size and seat mix (the Director is standing; how many volunteer
   members to aim for, and the quorum rule that keeps the Director from being the sole decider
   whenever volunteers are available).
2. Committee term length, staggering, and renewal limits.
3. Quorum and the "higher bar" threshold for irreversible actions (proposed 2/3).
4. Editorial Board size, terms, and chair/Editor-in-Chief role.
5. Staging window before discard (currently 14 days) + reminder cadence + extensions.
6. Editorial turnaround target and reassignment rule.
7. "Make private" vs "withdraw/tombstone" — exact criteria and DOI handling.
8. Emergency-action review window (proposed 5 working days).
9. Inactive-curator threshold (proposed 6 months) and reassignment procedure.
10. Code of Conduct to adopt; conduct contact.
11. Appeals body composition and timelines.
12. Whether to add an external Advisory Board.
13. Continuity/sunset plan specifics and who holds duplicate credentials.
14. Where the public governance documents and roster live; annual report.
15. Precedence between Terms and this policy.
