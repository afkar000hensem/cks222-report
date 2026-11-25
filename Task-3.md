#**Symmetrical Verification and Validation (V-Model design)**

**3.1 V-Model Symmetrical Mapping**

**Selected Feature:** Secure Online Payment Authorisation with Secure2u Module

The module is responsible for receiving payment requests, displaying transaction information, authenticating users and recording payment approval or rejection.

V-Model consists of two main sides:

- **Left side:** Verification through requirement analysis and system design.
- **Right side:** Validation through corresponding testing activities.

Each development stages are mapped to their corresponding testing stages.

| **Left Side - Design Phase** | **Right Side - Testing Phase** |
|---|---|
| Requirement Specification | Acceptance Testing |
| System Architecture | System / Integration Testing |
| Detailed Design | Unit Testing |

**Explanation of Symmetrical Mapping:** 

**Example of Requirements:** Viewing payment information, approving the payments and receive confirmation of buying.

1. Requirement Analysis - Acceptance Testing

L: During requirement specification, the team will identifies what people require when making online payments.
R: During acceptance testing, users will test whether the completed system satisfies the requirements.

2. System Architecture - System / Integration Testing

L: Team defines functional requirements and non-functional requirements. 
R: System testing checks whether complete application satisfies these requirements.

L: Team designs relationship between all of the requirements
R: Integration testing checks whether the requirements communicate properly and correctly.

3. Detailed Design - Unit Testing

L: Team defines detailed behaviour for individual functions/requirements
R: Unit testing will verifies each function works correctly.

**3.2 Quality Attribute Verification**

A. Based on the selected Secure2u payment authorisation feature, our team identifies security as the non-functional quality attribute and local biometric authentications the technical constraint.

**A. Non-Functional Quality Attribute: Security** (Registered Device Authorisation)

Ensure that online payment transactions can only be approved through customer's registered device. This will prevents unauthorised individuals from approving payments using stolen card details or intercepted messages.

**Security Requirement:** The system must verify that every payment approval request originated from an active registered device before allowing transaction to be proceed.

**Verification activities:**

1. Review system requirements to confirm that payment approval is limited to registered devices.
2. Check system design to understand how device registiration and authentication work.
3. Test payment approval using registered device.
4. Try to approve payment using unregistered device.
5. Test whether device has been removed from the account can still approve paymnts.
6. Check whether failed approval attempts are recorded in the system.

**Validation Activites:**

1. Ask users to try approving payment using their registered device.
2. Ask users to try accessing payment using another device.
3. Collect feedback from customer about this feature.

**B. Technical Constraint: Biometric Authentication Integration**

Based on our second user story, our group decided that the system should support biometric authentication, such as fingerprint or facial recognition. This allows customers to approve payments without manually entering their MAE app PIN, especially when they are making transactions in public.

**Technical Constraint:** The application must support the biometric authentication features on customer's device. When biometric authentication is successful, customer can proceed with the request payment. However, when biometric authentication is unavailable or unsuccessful, the MAE app PIN should be available as an alternative method.

**Verification Activities:**

1. Check system design whether it uses the device's support biometric authentication feature.
2. Try approving payment using successful fingerprint or facial recognition.
3. Check whether MAE app PIN can be used if biometric authentication fails.
4. Confirm that payment is not approved when authentication fails.

**Validation activites:**

1. Ask users to try approving payment using biometric authentication.
2. Check whether they can continue the process of payment.
3. Collect feedback on whether they find it more convenient by using this biometric authentication rather than entering their PIN.

**C. Difference Between Verification and Validation**

| Aspect | Verification | Validation |
|---|---|---|
| Main purpose | Confirming that software conforms to the written requirements and specification | Confirming that the completed software satisfies actual user needs and business goals |
| Main question | Are we building the system right? | Are we building the right system |
| Security example | Testing whether unregistered devices are blocked from approving payments | Collect feedback on whether customer satisfied on using registered device only |
| Biometric example | Testing whether fingerprint and facial recognition work correctly | Asking customers whether biometric authentication are convenient to use |
| Activities | Code inspections, unit testing, and design reviews | User Acceptance Testing(UAT) |