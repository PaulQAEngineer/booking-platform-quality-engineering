# Test Plan

---

## Document Information

| Item | Details |
| --- | --- |
| Project | Booking Platform Quality Engineering Showcase |
| Author | Paul |
| Version | 2.0 |
| Date | October 2026 |
| Test Level | API Testing |
| Test Type | Functional, Negative, Security, Performance, Regression |
| Test Approach | Risk\-Based Testing |

---

# Purpose

This Test Plan defines the testing activities, scope, resources, schedule and controls required to validate the quality, reliability and security of the Booking Platform API.

The plan aligns with the Test Strategy and provides a structured approach to verifying that business\-critical booking functionality operates as expected while reducing operational and customer\-facing risk.

---

# Business Context

The Booking Platform API enables customers and systems to create, manage, retrieve and cancel bookings.

Failures within these workflows could result in:

- Loss of revenue
- Customer dissatisfaction
- Operational disruption
- Data integrity issues
- Security vulnerabilities

Testing activities will focus on validating areas with the greatest business impact and highest risk.

---

# Objectives

The objectives of testing are to:

- Verify API functionality meets defined business requirements.
- Validate complete booking lifecycle workflows.
- Ensure authentication and authorisation controls function correctly.
- Confirm invalid requests are handled safely and consistently.
- Verify API contracts remain stable.
- Identify defects before release.
- Reduce operational and business risk.
- Provide confidence in production readiness.

---

# Requirements Traceability

The following requirements will be validated through testing.

| Requirement ID | Description |
| --- | --- |
| REQ\-001 | Authenticate User |
| REQ\-002 | Create Booking |
| REQ\-003 | Retrieve Booking |
| REQ\-004 | Update Booking |
| REQ\-005 | Delete Booking |
| REQ\-006 | Validate Request Data |
| REQ\-007 | Handle Invalid Requests |
| REQ\-008 | Protect Sensitive Data |

Each requirement will be linked to one or more test scenarios to ensure complete coverage.

---

# Scope

## In Scope

The following functionality will be tested:

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
- Third\-Party Integration Testing

---

# Business Critical Areas

The following areas present the highest business risk and will receive increased testing focus.

| Area | Business Risk |
| --- | --- |
| Authentication | Unauthorised system access |
| Booking Creation | Revenue loss and failed customer transactions |
| Booking Retrieval | Customer support impact and booking visibility issues |
| Booking Updates | Incorrect reservation information |
| Booking Deletion | Data loss and operational disruption |
| Validation Rules | Data integrity issues |

---

# Test Deliverables

The following artefacts will be produced:

- Test Strategy
- Test Plan
- Risk Assessment
- Test Scenarios
- Requirements Traceability Matrix
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
| --- | --- |
| Postman | API Test Execution |
| Newman | Automated Collection Execution |
| GitHub | Source Control |
| GitHub Actions | CI/CD Pipeline |
| JSON Schema Validation | Contract Validation |

---

# Test Data Requirements

Testing will utilise a range of representative business scenarios and data conditions.

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

- SQL Injection payloads
- Script Injection payloads
- Invalid tokens
- Expired tokens

---

# Test Approach

Testing will follow a risk\-based approach.

The level of testing applied to each feature will be determined by:

- Business impact
- Customer impact
- Likelihood of failure
- Technical complexity
- Security exposure

Business\-critical workflows will receive the greatest test coverage.

---

# Test Automation Strategy

## Purpose

Automation is intended to provide rapid feedback, improve regression coverage and support continuous integration practices.

## Automation Scope

The following areas will be automated:

- Authentication
- Booking Creation
- Booking Retrieval
- Booking Update
- Booking Deletion
- Schema Validation
- Regression Tests

## Automation Exclusions

The following activities will remain manual:

- Exploratory Testing
- Ad\-hoc Investigations
- Usability Evaluation
- One\-off Risk Assessments

## Execution

Automated tests will execute:

- Locally during development
- Via Newman execution
- Through GitHub Actions pipelines
- Prior to deployment activities

---

# Functional Testing

## Objective

Verify expected business functionality operates correctly.

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

Assess API responsiveness, reliability and stability under expected usage conditions.

## Coverage

- Response Times
- Throughput
- Error Rates
- Stability

### Success Criteria

- Average response time below 500ms
- No unexpected 5xx responses
- Stable performance throughout execution

---

# Regression Testing

## Objective

Ensure existing functionality remains unaffected by changes.

## Coverage

- Authentication
- Booking Workflows
- Validation Rules
- Business Critical Flows

Regression testing will be automated wherever possible and executed before release approval.

---

# Test Schedule

| Week | Activity |
| --- | --- |
| Week 1 | Environment Setup and Smoke Testing |
| Week 2 | Functional Testing |
| Week 3 | Negative Testing and Defect Logging |
| Week 4 | Security Validation |
| Week 5 | Performance Validation |
| Week 6 | Regression Testing |
| Week 7 | Defect Retesting |
| Week 8 | Reporting and Closure |

---

# Resource Requirements

| Role | Responsibility |
| --- | --- |
| QA Engineer | Test Design, Automation and Execution |
| Developer | Defect Investigation and Resolution |
| Stakeholders | Review and Approval |

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

- 100% of Priority 1 scenarios have been executed.
- No Critical defects remain open.
- No High severity defects remain unresolved.
- Regression testing has completed successfully.
- Automation execution has completed successfully.
- Test Summary Report has been produced.
- Stakeholder review has been completed.

---

# Defect Management

Defects will be recorded, prioritised and tracked throughout testing.

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

Testing is dependent upon:

- Environment availability
- API deployment stability
- Authentication services
- Valid test accounts
- Supporting documentation
- Test data availability

---

# Risks

The following testing risks have been identified:

- Environment instability
- Incomplete requirements
- Authentication service failures
- Test data availability issues
- API contract changes
- Delayed defect resolution

For detailed risk analysis, refer to the Risk Assessment document.

---

# Test Metrics

The following quality metrics will be monitored.

| Metric | Target |
| --- | --- |
| Priority 1 Execution | 100% |
| Smoke Test Pass Rate | 100% |
| Critical Defects Open | 0 |
| High Severity Defects Open | 0 |
| Average Response Time | <500ms |
| Automation Pass Rate | >95% |
| Requirement Coverage | 100% |

---

# Reporting

The following reports will be produced:

- Daily Test Progress Updates
- Defect Reports
- Automation Execution Reports
- Test Summary Report

---

# Approval

This Test Plan defines the execution approach used to validate the Booking Platform API and support release readiness decisions.

The document should be reviewed and updated throughout the project lifecycle as requirements, risks and priorities evolve.

---

**Author:** Paul

**Project:** Booking Platform Quality Engineering Showcase

**Version:** 2.0

