#**Symmetrical Verification and Validation (V-Model design)**

**3.1 V-Model Symmetrical Mapping**

**Selected Feature:** Secure Online Payment Authorisation with Secure2u Module

The module is responsible for receiving payment requests, displaying transaction information, authenticating users and recording payment approval or rejection.

V-Model consists of two main sides:

- **Left side:** Verification through requirement analysis and system design.
- **Right side:** Validation through corresponding testing activities.

Each development stages are mapped to their corresponding testing stages.

**Left Side - Design Phase** | **Right Side - Testing Phase**
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
R: unit testing will verifies each function works correctly.

**Quality Attribute Verification**

A. Based on the selected Secure2u payment authorisation feature, our team identifies security as the non-functional quality attribute and local biometric authentications the technical constraint.

**A. Non-Functional Quality Attribute: Security** (Registered Device Authorisation)

Ensure that online payment transactions can only be approved through customer's registered device. This will prevents unauthorised individuals from approving payments using stolen card details or intercepted messages.

**Security Requirement:** The system must verify that every payment approval request originates from an active registered device before allowing transaction to be proceed.

