# Test Plan

## Document Information

| Item | Details |
|--------|--------|
| Project | Booking Platform Quality Engineering Showcase |
| Author | Paul |
| Version | 1.0 |
| Date | October 2026 |
| Test Level | API Testing |
| Test Type | Functional, Negative, Security, Performance, Regression |
| Test Approach | Risk-Based Testing |

---

# Purpose

This test plan defines the activities, resources, scope, schedule and approach required to validate the quality of the Booking Platform API.

The plan supports the objectives defined within the Test Strategy and ensures testing activities are executed consistently and effectively.

---

# Objectives

The objectives of testing are to:

- Verify API functionality meets expected business requirements.
- Validate booking workflows operate correctly.
- Ensure appropriate authentication and authorisation controls exist.
- Verify invalid input is handled safely.
- Identify defects before release.
- Reduce business and operational risk.
- Provide confidence in production readiness.

---

# Scope

## In Scope

The following API functionality will be tested:

- Authentication
- Booking Creation
- Booking Retrieval
- Booking Update
- Booking Deletion
- Data Validation
- Error Handling
- API Contract Validation
- Security Controls
- Performance Validation
- Automated Regression Testing

---

## Out of Scope

The following areas are excluded:

- User Interface Testing
- Browser Compatibility Testing
- Mobile Application Testing
- Accessibility Testing
- Infrastructure Penetration Testing
- Third-Party Integration Testing

---

# Test Deliverables

The following artefacts will be produced:

- Test Strategy
- Test Plan
- Risk Assessment
- Test Scenarios
- Postman Collections
- Environment Configuration Files
- Newman Execution Reports
- Defect Reports
- Automation Reports
- Test Summary Report

---

# Test Environment

## Environment

Staging / Test Environment

## Tools

| Tool | Purpose |
|--------|--------|
| Postman | API Test Execution |
| Newman | Automated Collection Execution |
| GitHub | Source Control |
| GitHub Actions | CI/CD Pipeline |
| JSON Schema Validation | Contract Validation |

---

# Test Data Requirements

Testing will utilise a range of data conditions.

## Positive Test Data

- Valid customer details
- Valid booking dates
- Valid authentication credentials

## Negative Test Data

- Missing mandatory fields
- Invalid data types
- Invalid date formats
- Empty strings
- Null values
- Invalid identifiers

## Boundary Test Data

- Maximum field lengths
- Minimum field lengths
- Date boundaries
- Numeric boundaries

## Security Test Data

- SQL Injection Payloads
- Script Injection Payloads
- Invalid Tokens
- Expired Tokens

---

# Test Approach

Testing will follow a risk-based approach.

Testing effort will focus on areas with the greatest business impact and highest likelihood of failure.

The following test types will be executed.

---

# Functional Testing

## Objective

Verify expected system behaviour.

## Coverage

- Create Booking
- Retrieve Booking
- Update Booking
- Delete Booking
- Authentication
- Response Validation

### Example Scenarios

- Create Valid Booking
- Retrieve Existing Booking
- Update Existing Booking
- Delete Existing Booking

---

# Negative Testing

## Objective

Verify invalid requests are handled correctly.

## Coverage

- Validation Rules
- Invalid Data
- Missing Fields
- Invalid Identifiers
- Authorisation Failures

### Example Scenarios

- Missing Surname
- Invalid Date Format
- Empty Request Body
- Invalid Booking Identifier

---

# Security Testing

## Objective

Verify security controls prevent unauthorised access and malicious behaviour.

## Coverage

- Authentication
- Authorisation
- Token Validation
- Input Validation
- Data Protection

### Security Checks

- Missing Token
- Invalid Token
- Expired Token
- SQL Injection Attempts
- Script Injection Attempts

---

# Performance Testing

## Objective

Assess API responsiveness and stability.

## Coverage

- Response Times
- Server Reliability
- Error Rates
- Throughput

### Success Criteria

- Average response time below 500ms
- No unexpected 5xx responses
- Stable performance across key workflows

---

# Regression Testing

## Objective

Ensure existing functionality remains unaffected by changes.

## Coverage

- Booking Workflows
- Authentication
- Validation Rules
- Business Critical Flows

Regression testing will be automated wherever possible.

---

# Test Schedule

| Phase | Activity |
|--------|--------|
| Phase 1 | Environment Verification |
| Phase 2 | Functional Testing |
| Phase 3 | Negative Testing |
| Phase 4 | Security Testing |
| Phase 5 | Performance Validation |
| Phase 6 | Regression Testing |
| Phase 7 | Defect Retesting |
| Phase 8 | Test Completion Reporting |

---

# Resource Requirements

| Role | Responsibility |
|--------|--------|
| QA Engineer | Test Design and Execution |
| Developer | Defect Resolution |
| Project Stakeholders | Review and Approval |

---

# Entry Criteria

Testing may begin when:

- API has been deployed.
- Environment is available.
- Documentation is available.
- Authentication service is operational.
- Test data is prepared.
- Critical dependencies are functioning.

---

# Exit Criteria

Testing will be considered complete when:

- All Priority 1 scenarios have been executed.
- No Critical defects remain open.
- No High severity defects remain unresolved.
- Regression testing has completed successfully.
- Automation execution has completed successfully.
- Test Summary Report has been produced.
- Stakeholder review has been completed.

---

# Defect Management

Defects will be recorded and prioritised using the following classification.

## Critical

Production use blocked or major business functionality unavailable.

## High

Core functionality impacted with significant business impact.

## Medium

Functionality impaired with acceptable workaround.

## Low

Minor issue with limited business impact.

---

# Dependencies

Testing is dependent on:

- Environment availability
- API deployment stability
- Authentication services
- Valid test accounts
- Supporting documentation

---

# Risks

The following testing risks have been identified:

- Environment instability
- Incomplete requirements
- Authentication service failures
- Test data availability issues
- API contract changes
- Delayed defect resolution

Detailed risk information can be found within the Risk Assessment document.

---

# Test Metrics

The following metrics will be monitored:

| Metric | Target |
|----------|----------|
| Priority 1 Execution | 100% |
| Smoke Test Pass Rate | 100% |
| Critical Defects Open | 0 |
| High Severity Defects Open | 0 |
| Average Response Time | <500ms |
| Automation Pass Rate | >95% |

---

# Reporting

The following reports will be produced throughout testing:

- Daily Test Progress Updates
- Defect Reports
- Automation Execution Reports
- Test Summary Report

---

# Approval

This Test Plan defines the execution approach for validating the Booking Platform API.

The document is subject to review and update throughout the testing lifecycle as requirements, risks and priorities evolve.

---

**Author:** Paul  
**Project:** Booking Platform Quality Engineering Showcase  
**Version:** 1.0
