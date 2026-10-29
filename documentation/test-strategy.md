# API Test Strategy

## Document Information

| Item | Details |
|--------|--------|
| Project | Booking Platform Quality Engineering Showcase |
| Author | Paul |
| Version | 2.0 |
| Date | October 2026 |
| Test Level | API Testing |
| Test Approach | Risk-Based Testing |

---

# Objective

The objective of this testing effort is to provide confidence that the Booking Platform API supports reliable, secure, scalable and accurate booking operations.

Testing activities will validate critical customer journeys, ensure data integrity is maintained throughout booking workflows, identify security vulnerabilities, and verify that API responses meet agreed performance expectations.

This strategy aims to reduce business risk by identifying defects as early as possible and ensuring all critical API functionality is thoroughly validated.

---

# Business Risks

The following business risks have been identified:

| Risk | Business Impact |
|--------|--------|
| Customers unable to create bookings | Revenue loss |
| Invalid booking data accepted | Data integrity issues |
| Booking updates fail | Customer dissatisfaction |
| Booking deletions behave incorrectly | Data loss |
| Authentication weaknesses | Security breach |
| Poor API performance | User experience degradation |
| Unhandled errors | Service instability |

---

# Risk Assessment Matrix

| Risk | Probability | Impact | Priority |
|--------|--------|--------|--------|
| Authentication failure | Medium | High | P1 |
| Booking creation failure | Medium | High | P1 |
| Invalid data acceptance | High | High | P1 |
| Booking update failure | Medium | High | P1 |
| Excessive response times | Medium | Medium | P2 |
| Error message defects | Low | Medium | P3 |

---

# API Quality Risks

The following quality risks have been identified:

- Missing input validation
- Incorrect HTTP response codes
- Broken authentication controls
- Authorisation failures
- Data corruption
- Inconsistent API contracts
- Unhandled exceptions
- Sensitive data exposure
- Excessive response times
- Regression defects

---

# Scope

## In Scope

The following API capabilities will be tested:

- Booking creation
- Booking retrieval
- Booking updates
- Booking deletion
- Authentication
- Authorisation validation
- Data validation
- Error handling
- Response validation
- API contract validation
- Security controls
- Performance validation
- Regression testing
- Test automation

---

## Out of Scope

The following areas are excluded from this testing effort:

- Front-end user interface testing
- Mobile application testing
- Browser compatibility testing
- Third-party integrations
- Infrastructure penetration testing
- Accessibility testing

---

# Test Approach

Testing will follow a risk-based approach where effort is prioritised against features presenting the highest business and customer impact.

The strategy combines:

- Functional Testing
- Negative Testing
- Security Testing
- Performance Testing
- Regression Testing
- Automation Testing

Testing activities will be performed throughout the lifecycle to ensure rapid defect detection and continuous quality feedback.

---

# Coverage Priorities

## Priority 1 (Critical)

- Authentication
- Authorisation
- Booking creation
- Booking updates
- Data integrity

---

## Priority 2 (High)

- Booking retrieval
- Error handling
- Validation messages
- API contract validation

---

## Priority 3 (Medium)

- Reporting functions
- Monitoring validation
- Non-critical endpoints

---

# Test Types

## Functional Testing

### Objective

Verify API functionality behaves according to requirements.

### Coverage

- Create bookings
- Retrieve bookings
- Update bookings
- Delete bookings
- Authentication workflows
- Response validation

### Example Scenarios

- Create valid booking
- Update existing booking
- Retrieve booking by identifier
- Delete existing booking

---

## Negative Testing

### Objective

Verify invalid requests are handled correctly and do not compromise system stability.

### Coverage

- Missing required fields
- Invalid data formats
- Null values
- Empty strings
- Boundary value violations
- Invalid identifiers

### Example Scenarios

- Create booking with missing surname
- Invalid booking dates
- Invalid authentication token
- Invalid booking identifier

---

## Security Testing

### Objective

Verify security controls prevent unauthorised access and malicious input.

### Coverage

- Authentication validation
- Authorisation validation
- Input validation
- Injection attack testing
- Sensitive information exposure
- Session token handling

### Example Scenarios

- Invalid credentials
- Missing authentication token
- SQL injection attempts
- Script injection attempts
- Direct object reference testing

### Example Payloads

```json
{
  "firstname": "' OR '1'='1"
}
```

```json
{
  "firstname": "<script>alert('test')</script>"
}
```

---

## Performance Testing

### Objective

Assess responsiveness and reliability of the API under expected operating conditions.

### Coverage

- Response times
- Throughput
- Reliability
- Error rates

### Success Criteria

- Average response time below 500ms
- No unexpected server errors
- Consistent performance across critical workflows

---

## Regression Testing

### Objective

Ensure existing functionality remains unaffected by changes.

### Coverage

- Booking workflows
- Authentication
- Authorisation
- Validation rules
- Critical business processes

Regression tests will be automated wherever practical.

---

# Test Data Strategy

Testing will utilise multiple data sets to ensure effective coverage.

### Valid Data

- Correct customer information
- Valid booking dates
- Valid credentials

### Invalid Data

- Missing mandatory fields
- Invalid field types
- Invalid date formats
- Null values
- Empty values

### Boundary Data

- Maximum field lengths
- Minimum field lengths
- Date boundaries

### Security Data

- SQL injection payloads
- Script injection payloads
- Invalid tokens
- Expired tokens

Where possible, test data will be reset between executions to ensure repeatability.

---

# Test Environment

## Environment

Staging / Test Environment

## Tools

- Postman
- Newman
- GitHub
- GitHub Actions
- JSON Schema Validation

## Test Data Sources

- Generated test bookings
- Environment variables
- Collection variables
- Mock security payloads

---

# Test Coverage Matrix

| Capability | Functional | Negative | Security | Performance | Automation |
|------------|------------|------------|------------|------------|------------|
| Create Booking | Yes | Yes | Yes | Yes | Yes |
| Retrieve Booking | Yes | Yes | Yes | Yes | Yes |
| Update Booking | Yes | Yes | Yes | Yes | Yes |
| Delete Booking | Yes | Yes | Yes | Yes | Yes |
| Authentication | Yes | Yes | Yes | Yes | Yes |

---

# Assumptions

The following assumptions apply:

- API documentation is accurate
- Test environment is stable
- Test accounts are available
- Required endpoints are deployed
- Database state can be reset when required
- Authentication services remain operational

---

# Entry Criteria

Testing may begin when:

- API deployed successfully
- Environment available
- Authentication configured
- API documentation available
- Test data prepared
- Critical dependencies operational

---

# Exit Criteria

Testing will be considered complete when:

- No Critical defects remain open
- No High severity defects remain unresolved
- All Priority 1 scenarios executed
- Regression suite passes successfully
- Automation execution completed
- Test report produced
- Stakeholder review completed

---

# Defect Management

Defects will be categorised using the following severity levels.

## Critical

System unavailable or major business process blocked.

## High

Core functionality impacted with significant business impact.

## Medium

Functionality affected but workaround available.

## Low

Minor defect with limited impact.

All defects will be documented, prioritised and tracked through to closure.

---

# Automation Strategy

Automation will be implemented using Postman and Newman.

Automated coverage will focus on:

- Smoke testing
- Functional regression testing
- Authentication validation
- Data validation
- Security checks
- Response time monitoring

Collections will be executed locally and within CI/CD pipelines to support continuous quality feedback.

Future enhancements may include:

- Playwright API automation
- Contract testing
- Performance monitoring
- Scheduled regression execution

---

# Success Metrics

The following quality objectives apply:

- 100% of Priority 1 scenarios executed
- 100% automated smoke suite pass rate
- Zero Critical defects open
- Zero High severity defects accepted into production
- Average API response time below 500ms
- 100% authentication controls validated

---

# Deliverables

The following project artefacts will be produced:

- Test Strategy
- Test Plan
- Risk Assessment
- Coverage Matrix
- Postman Collections
- Environment Files
- Newman Execution Reports
- Defect Reports
- Automation Reports
- Test Summary Report

---

# Approval

This document defines the testing approach for the Booking Platform Quality Engineering Showcase project and will be reviewed and updated as testing activities evolve.
