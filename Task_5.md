# Process Tailoring and Team Dynamics — Maybank Secure2u

## 1. Tailoring with Münch's 4 Ps

**Project in context: Maybank Secure2u**

Secure2u is a faster and more secure way to approve Maybank2u and MAE transactions using **Secure Verification** (one tap approval). Available on the MAE app, once activated it becomes the default method for approving transactions.

Applying **Münch's 4 Ps** helps prevent heavyweight process overhead from scuttling project success.

### a) Problem (Complexity, novelty, volatility of constraints)
* **High Complexity and Novelty:** Replacing legacy SMS TAC/MSOS codes with device spesific key, push notifications, and offline time based OTPs (Secure TAC) integrated across Maybank2u web, the MAE mobile app, and external FPX/card gateways.
* **High Constraint Volatility:** Rapidly evolving form of apk and malware as a scam vector and a strict evershifting anti fraud mandates from Bank Negara Malaysia (BNM). For example, a mandatory 12 hour cooling off periods and ATM activation checks. These requires an adaptive process capable of handling sudden regulatory and security updates.

### b) Project (Team size, distribution, budget, schedule)
* **Large, Distributed Teams:** Requires coordinated development across multiple specialized teams, including MAE mobile app teams, core banking backend engineers, payment gateway/FPX teams, cybersecurity operations, and ATM firmware teams.
* **Strict Schedules and Enterprise Budget:** Backed by substantial enterprise banking capital, but constrained by hard BNM regulatory compliance deadlines (such as the phased retirement of SMS OTPs) and high coordination overhead across distributed engineering and QA team.

### c) People (Skill levels, team cohesion, culture, turnover)
* **Specialized Skill Sets:** Demands engineers experienced in mobile security (iOS Keychain / Android Keystore, anti-tampering, and Malware Shielding), high concurrency backend architecture, and regulatory compliance.
* **Cross Team Cohesion and Culture:** Documentation of important are essential to ensure all teams involved act as a cohesive team and reduces culture friction. For example, differences in software process between backend team and frontend team can be smoothly handled through detailed documentation. Standardized documentation and security handoffs are essential to mitigate knowledge loss from staff turnover.

### d) Product (Criticality, reliability, lifespan, security needs)
* **Mission Critical and High Reliability:** Handles millions of daily financial authorizations where downtime directly impacts commerce. Therefore, requires near zero downtime (99.99%+ availability) and strict backup mechanisms such as offline Secure TAC fallback when push notifications fail.
* **Maximum Security and Long Lifespan:** Because financial loss and regulatory penalties are severe, the software process cannot be lightweight, it must enforce formal threat modeling, penetration testing, code audits, and strict release gates over a multiyear lifecycle.

---

## 2. Why Extreme Process Models Fail for Secure2u

### Why Pure Ad-Hoc Agile Fails
Pure Agile characterised by minimal documentation, informal handoffs, and rapid continuous deployment without heavy gates is incompatible with Secure2u's context:
* **Product (Criticality and Security Needs):** Secure2u authorizes millions of ringgit in daily transactions. Ad-hoc practices bypass formal threat modeling, device spesific verification, and mandatory penetration testing, exposing customers to severe financial loss and Bank Negara Malaysia (BNM) penalties.
* **Project (Team Size and Distribution):** Development spans separate MAE mobile teams, core banking ledger engineers, FPX/card gateway teams, and ATM firmware vendors. Informal, verbal Agile coordination breaks down across distributed enterprise teams, leading to integration failures and unversioned API mismatches.
* **People (Turnover and Compliance Culture):** In a large enterprise bank, relying on assumed knowledge rather than formal architectural specifications creates high operational risk if key security or backend engineers leave.

### Why Rigid, Linear Waterfall Fails
A purely sequential, heavyweight Waterfall model freezing all requirements upfront with multi-month phase gates before any code is created is also not viable:
* **Problem (Volatility of Constraints):** Financial malware (such as malicious Android APKs intercepting notifications) and social engineering tactics evolve monthly. Under rigid Waterfall, responding to a newly discovered exploit or an urgent BNM anti scam directive would stall in months of change control bureaucracy while customers remain vulnerable.
* **Problem (Novelty) and Product (User Friction):** Features such as the 12 hour cooling off period, Malware Shielding, and ATM activation require real world telemetry to balance security against legitimate user lockouts. Waiting until the end of a 12 month Waterfall cycle for user feedback would result in friction heavy UX or high transaction drop-off rates.
* **People (Cross Team Culture):** Forcing fast moving mobile app squads (iOS/Android) into a slow release schedule stalls UI improvements and bug fixes that do not touch core infrastructure.

---

## 3. Recommended Hybrid Process Models

### Hybrid of Spiral Model and V-Model
This Hybrid combine Spiral Model explicit risk driven loops and early prototyping with V-Model rigorous requirements to test verification mapping
* **Problem (Volatility of Constraints):** Every spiral loop explicitly prioritizes risk analysis—ideal when new Android malware/APK exploits or urgent BNM anti scam rules (like cooling off periods or device verification checks) shift priorities spontaneously.
* **Product (Reliability and User Friction):** Allows prototyping and controlled risk evaluation around security vs. UX trade offs (for instance, preventing false lockouts or handling push notification delivery failures) before full rollout.
* **Project (Team size, distribution, schedule):** Because the V-Model maps every design phase (System, Architecture, and Module Design) to a corresponding testing phase (Integration, System, and Acceptance Testing), distributed teams such as core banking backend engineers, ATM firmware vendors, and payment gateway teams have explicit interface contracts and verification checkpoints before integration.
* **People (Skill levels, team cohesion, culture, turnover)** Mandatory requirements to test traceability matrices and design specs preserve system knowledge when staff rotate or leave, reducing onboarding friction across banking teams.
---

## 4. Tuckman's Team Dynamics and Conflict Management

### 1. Forming
On **8 October 2026**, the team initially came together with 5 members and quickly agreed on a trusted leader. All members, including the elected leader, accepted the decision smoothly. Ground rules were established early: don't be afraid to ask questions, avoid lone decisions, treat one another respectfully, and help teammates who fall behind.

### 2. Storming
During storming, every member—including the leader—shared opinions on how to approach the assignment and debated how to proceed, such as which company and USM project to audit. Members also actively tagged one another in the WhatsApp group to keep everyone engaged and prevent free riding.

### 3. Norming
After a week of ongoing discussion about the assignment, cooperation improved and disagreements were resolved by checking interpretations against the assignment instructions to find the most accurate consensus. Roles were assigned through a first come, first served poll, reducing friction over task ownership.

### 4. Performing
In the final two weeks before submission, the team operated as a cohesive unit with flexible task sharing. Members reviewed each other's work and offered constructive feedback, catching minor errors early and fixing them quickly so progress stayed steady with minimal roadblocks through completion.

### How We Managed Conflict During Process Engineering Tasks
When conflicts arose, we held team wide discussions where members backed their viewpoints with evidence from the assignment instructions. We made sure quieter voices were heard and no single person dominated the conversation. After weighing all perspectives and supporting evidence, we reached decisions by majority agreement while checking for remaining concerns so potential gaps were addressed before moving forward.
