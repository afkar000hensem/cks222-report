# Process Tailoring & Team Dynamics — Maybank Secure2u

## 1. Tailoring with Münch's 4 Ps

**Project in context: Maybank Secure2u**

Secure2u is a faster and more secure way to approve Maybank2u and MAE transactions using **Secure Verification** (one-tap approval). Available on the MAE app, once activated it becomes the default method for approving transactions.

Applying **Münch's 4 Ps** helps prevent heavyweight process overhead from scuttling project success.

### a) Problem (Complexity, novelty, volatility of constraints)
* **High Complexity & Novelty:** Replacing legacy SMS TAC/MSOS codes with cryptographic device binding, push notifications, and offline time-based OTPs (Secure TAC) integrated across Maybank2u web, the MAE mobile app, and external FPX/card gateways.
* **High Constraint Volatility:** Rapidly evolving malware/APK scam vectors and strict, shifting anti-fraud mandates from Bank Negara Malaysia (BNM)—such as mandatory 12-hour cooling-off periods and ATM activation checks—require an adaptive process capable of handling sudden regulatory and security updates.

### b) Project (Team size, distribution, budget, schedule)
* **Large, Distributed Teams:** Requires coordinated development across multiple specialized squads, including MAE mobile app teams, core banking backend engineers, payment gateway/FPX teams, cybersecurity/fraud operations, and ATM firmware teams.
* **Strict Schedules & Enterprise Budget:** Backed by substantial enterprise banking capital, but constrained by hard BNM regulatory compliance deadlines (such as the phased retirement of SMS OTPs) and high coordination overhead across distributed engineering and QA units.

### c) People (Skill levels, team cohesion, culture, turnover)
* **Specialized Skill Sets:** Demands engineers experienced in mobile security (iOS Keychain / Android Keystore, anti-tampering, and Malware Shielding), high-concurrency backend architecture, and regulatory compliance.
* **Cross-Team Cohesion & Culture:** Bridges traditional core-banking Waterfall/governance culture with agile mobile product teams. Standardized documentation and security handoffs are essential to mitigate knowledge loss from enterprise staff turnover.

### d) Product (Criticality, reliability, lifespan, security needs)
* **Mission-Critical & High Reliability:** Handles millions of daily financial authorizations where downtime directly impacts commerce; requires near-zero downtime (99.99%+ availability) and strict failover mechanisms (such as offline Secure TAC fallback when push notifications fail).
* **Maximum Security & Long Lifespan:** Because financial loss and regulatory penalties are severe, the software process cannot be lightweight—it must enforce formal threat modeling, penetration testing, code audits, and strict release gates over a multi-year lifecycle.

---

## 2. Why Extreme Process Models Fail for Secure2u

### Why Pure Ad-Hoc Agile Fails
Pure, unbridled Agile—characterized by minimal documentation, informal handoffs, and rapid continuous deployment without heavy gates—is incompatible with Secure2u's context:
* **Product (Criticality & Security Needs):** Secure2u authorizes millions of ringgit in daily transactions. Ad-hoc practices bypass formal threat modeling, cryptographic verification, and mandatory penetration testing, exposing customers to severe financial loss and Bank Negara Malaysia (BNM) penalties.
* **Project (Team Size & Distribution):** Development spans separate MAE mobile teams, core banking ledger engineers, FPX/card gateway teams, and ATM firmware vendors. Informal, verbal Agile coordination breaks down across distributed enterprise teams, leading to integration failures and unversioned API mismatches.
* **People (Turnover & Compliance Culture):** In a large enterprise bank, relying on tacit knowledge rather than formal architectural specifications creates high operational risk if key security or backend engineers leave.

### Why Rigid, Linear Waterfall Fails
A purely sequential, heavyweight Waterfall model—freezing all requirements upfront with multi-month phase gates before any code ships—is also not viable:
* **Problem (Volatility of Constraints):** Financial malware (such as malicious Android APKs intercepting notifications) and social engineering tactics evolve monthly. Under rigid Waterfall, responding to a newly discovered exploit or an urgent BNM anti-scam directive would stall in months of change-control bureaucracy while customers remain vulnerable.
* **Problem (Novelty) & Product (User Friction):** Features such as the 12-hour cooling-off period, Malware Shielding, and ATM activation require real-world telemetry to balance security against legitimate user lockouts. Waiting until the end of a 12-month Waterfall cycle for user feedback would result in friction-heavy UX or high transaction drop-off rates.
* **People (Cross-Team Culture):** Forcing fast-moving mobile app squads (iOS/Android) into a slow mainframe release cadence stalls UI improvements and bug fixes that do not touch core cryptographic infrastructure.

---

## 3. Recommended Hybrid Process Models

### 1. Scaled Agile Framework (SAFe) with Stage-Gate Governance
SAFe combines enterprise-level planning and hard milestone synchronization (prescriptive) with decentralized, sprint-based team execution (agile).

* **Prescriptive Layer (Program & Portfolio Level):** Uses Program Increment (PI) Planning every 8–12 weeks and formal Compliance/Security Stage-Gates to align hard regulatory deadlines (such as Bank Negara Malaysia directives) across all dependent teams—MAE mobile squads, core banking ledger engineers, FPX gateways, and ATM firmware vendors.
* **Agile Layer (Team Level):** Individual feature squads execute in 2-week Scrum/Kanban sprints to build UI flows, push notification handlers, and anti-malware detection updates once API contracts are locked.
* **Alignment with Münch's 4 Ps:**
  * **Project (Team size, distribution, schedule):** Directly addresses multi-team coordination across large, distributed banking departments while enforcing fixed regulatory delivery dates.
  * **Product (Criticality & reliability):** Built-in architectural runways and formal release gates help ensure features reach production only after passing penetration testing and compliance sign-offs.

### 2. Disciplined Agile (DA)
Disciplined Agile (DA) is a goal-driven, hybrid process toolkit designed to tailor practices based on team context, risk, and regulatory constraints rather than forcing a single rigid methodology.

* **Prescriptive Layer (Inception & Transition Phases):** Enforces formal upfront architectural modeling, threat modeling, and a dedicated Transition Phase for production readiness, security audits, and phased canary rollouts (such as rolling out a new Secure2u device-binding rule to 5% of users before full release).
* **Agile Layer (Construction Phase):** Lets teams tailor day-to-day workflows—using iterative sprints for fast-changing mobile UX and Malware Shielding rules, while applying stricter verification loops for core cryptographic modules.
* **Alignment with Münch's 4 Ps:**
  * **Problem (Complexity & volatility of constraints):** Adapts smoothly to evolving scam vectors and BNM policy changes without overhauling core security architecture.
  * **People (Skill levels, culture, turnover):** Balances governance artifacts (protecting against enterprise staff turnover) with embedded security specialists while avoiding over-formalization on low-risk UI tasks.

---

## 4. Tuckman's Team Dynamics & Conflict Management

### 1. Forming
On **8 October 2026**, the team initially came together with 5 members and quickly agreed on a trusted leader. All members, including the elected leader, accepted the decision smoothly. Ground rules were established early: don't be afraid to ask questions, avoid lone decisions, treat one another respectfully, and help teammates who fall behind.

### 2. Storming
During storming, every member—including the leader—shared opinions on how to approach the assignment and debated how to proceed, such as which company and USM project to audit. Members also actively tagged one another in the WhatsApp group to keep everyone engaged and prevent free-riding.

### 3. Norming
After a week of ongoing discussion about the assignment, cooperation improved and disagreements were resolved by checking interpretations against the assignment instructions to find the most accurate consensus. Roles were assigned through a first-come, first-served poll, reducing friction over task ownership.

### 4. Performing
In the final two weeks before submission, the team operated as a cohesive unit with flexible task sharing. Members reviewed each other's work and offered constructive feedback, catching minor errors early and fixing them quickly so progress stayed steady with minimal roadblocks through completion.

### How We Managed Conflict During Process Engineering Tasks
When conflicts arose, we held team-wide discussions where members backed their viewpoints with evidence from the assignment instructions. We made sure quieter voices were heard and no single person dominated the conversation. After weighing all perspectives and supporting evidence, we reached decisions by majority agreement while checking for remaining concerns so potential gaps were addressed before moving forward.
