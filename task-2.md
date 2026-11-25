# Task 2: Requirements Quality & Agile User Stories

## Backlog Item

**Feature:** Online payment authorised with Secure2u through the MAE app with MAE app PIN or biometric authentication.

## Agile User Stories

**Story 1:** As a Maybank customer, I want to be able to approve an online payment from my registered device only, so that scammers cannot approve fraudulent payments from my account even if they have access to my messages and card details.

| Attribute | Story 1 |
|---|---|
| Independent | Partly. The story needs device registration to be built first, but the approval requirements and constraints are independent of the implementation of device registration. |
| Negotiable | Yes. The story gives the developers flexibility on how to let the user approve their payment. |
| Valuable | Yes. The story prevents scammers from approving online payments by only allowing the customer's registered device to approve them. |
| Estimable | Yes. The work can be estimated based on the approval rule and the push notification system on the target operating systems. However, it is unknown how each device is identified, so this is treated as an assumption. |
| Small | Yes. The story is only for the approval of the payment from a registered device and does not include device registration. |
| Testable | Yes. The feature can be tested by three scenarios: <br> 1. A payment is triggered and approved from the registered device, and the payment goes through. <br> 2. Someone triggers a payment using the customer's bank details and the customer rejects it, so the payment is cancelled. <br> 3. Someone triggers a payment on the customer's account and no one approves it on the registered device within 50 seconds (for example, a scammer has no registered device to approve it), so the request times out and the payment is cancelled. |

**Story 2:** As a Maybank customer, I want another option to approve an online payment that does not require me to enter my MAE app PIN, so that no one nearby can watch me enter it when I am approving in public.

| Attribute | Story 2 |
|---|---|
| Independent | Partly. The biometric mechanism is simple enough to be developed before the Story 1 approval feature. However, the feature cannot be finalised until the Story 1 approval feature is fully developed. |
| Negotiable | Yes. This story gives the developers flexibility on how to let the user approve their online payment, as long as it does not require the MAE app PIN. |
| Valuable | Yes. The feature provides privacy to customers when approving an online payment in public. |
| Estimable | Yes. The feature is straightforward enough to be estimated, as the app only requests biometric authentication from the device. What is not known from the story is how many failed attempts are allowed before it triggers the PIN fallback, so this is assumed to be 3 attempts. |
| Small | Yes. This feature is simple because it only requests its own biometric authentication from the operating system, so the authentication happens on the device itself rather than on Maybank's server. |
| Testable | Yes. The feature can be tested by three scenarios: <br> 1. Approval is done with the alternative method without using the PIN. <br> 2. Approval with the alternative method fails 3 times and the PIN must be typed in. <br> 3. Approval requires the PIN to be typed in because the alternative method is not set up. |

## Given-When-Then Acceptance Criteria

### Story 1

**S1.1 Positive: customer approves**
- **Given** the customer triggers an online payment on their account
- **When** the customer approves the online payment on their registered device
- **Then** the online payment goes through

**S1.2 Negative: customer rejects**
- **Given** someone triggers an online payment using the customer's bank details
- **When** the customer rejects the online payment approval
- **Then** the online payment is cancelled

**S1.3 Boundary: approval times out**
- **Given** someone triggers an online payment on the customer's account
- **When** no one approves the online payment on the registered device within 50 seconds
- **Then** the approval request times out and the online payment is automatically cancelled

### Story 2

**S2.1 Positive: biometric approval**
- **Given** the customer is approving an online payment and has biometric authentication set up
- **When** the customer passes the biometric authentication
- **Then** the online payment is approved

**S2.2 Negative: PIN fallback after failed biometrics**
- **Given** the customer is approving an online payment and has biometric authentication set up
- **When** the customer fails the biometric authentication 3 times
- **Then** biometric authentication stops and Secure2u falls back to PIN authentication

**S2.3 Boundary: no biometric set up**
- **Given** the customer's registered Secure2u device does not have biometric authentication set up
- **When** the customer tries to approve the online payment
- **Then** Secure2u offers only PIN authentication

The 50-second timeout is based on Maybank's Secure2u FAQ (see References).

## Definition of Done

A story is done only when all three parts below are met.

### 1. Core Acceptance Criteria
- [ ] Story 1: S1.1 (customer approves), S1.2 (customer rejects) and S1.3 (times out after 50 seconds) all pass
- [ ] Story 2: S2.1 (biometric approval), S2.2 (PIN fallback after 3 failed attempts) and S2.3 (PIN only when no biometric is set up) all pass

### 2. Process Compliance (all stories)
- [ ] Tests were written before the code (TDD)
- [ ] The code is refactored
- [ ] The code is peer reviewed by the Code Reviewer, with the Code Review Report stored in the GitHub pull request
- [ ] The Quality Assurance Engineer's Static Analysis Report shows zero remaining warnings
- [ ] The feature is threat modelled (SDL-Agile), and PIN/biometric results are never written to logs
- [ ] Names and flows in the code match the design models

### 3. Integration Verification (all stories, mapped to the V-Model in Task 3)
- [ ] The code is merged to the main branch with a passing build within the ten-minute target (CI)
- [ ] Unit tests pass (Detailed Design ↔ Unit Testing), including amount-integrity tests such as RM500.00 never becoming RM5,000.00
- [ ] Integration/system tests pass on Android and iOS (System Architecture ↔ System / Integration Testing)
- [ ] UAT is signed off by the [tunggu task 1 raci siap] (Requirement Specification ↔ Acceptance Testing)
- [ ] The story is ready for deployment

## References

Maybank. *How to authorise transactions (Secure2u).* https://www.maybank2u.com.my/maybank2u/malaysia/en/personal/frequent_queries/secure2u_tac/how-to-authorise-transactions.page
