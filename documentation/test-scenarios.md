# Test Scenarios

## Document Information

| Item | Details |
|--------|--------|
| Project | Booking Platform Quality Engineering Showcase |
| Author | Paul |
| Version | 1.0 |
| Date | October 2026 |
| Test Level | API Testing |

---

# Purpose

This document defines the high-level test scenarios used to validate the Booking Platform API.

Scenarios have been designed using a risk-based approach and focus on validating functional behaviour, security controls, data integrity, system resilience and performance expectations.

---

# Scenario Coverage Summary

| Area | Number of Scenarios |
|----------|----------|
| Functional Testing | 10 |
| Negative Testing | 8 |
| Security Testing | 7 |
| Performance Testing | 5 |
| Regression Testing | 5 |
| Total | 35 |

---

# Functional Test Scenarios

## TC001 - Create Booking With Valid Data

**Objective:** Verify a booking can be created successfully.

**Expected Result:**

- Booking created successfully
- HTTP 200 or 201 returned
- Booking identifier generated

---

## TC002 - Retrieve Existing Booking

**Objective:** Verify an existing booking can be retrieved.

**Expected Result:**

- Booking details returned
- Correct booking identifier returned
- HTTP 200 returned

---

## TC003 - Retrieve All Bookings

**Objective:** Verify all available bookings can be retrieved.

**Expected Result:**

- Booking collection returned
- Response structure valid
- HTTP 200 returned

---

## TC004 - Update Existing Booking

**Objective:** Verify booking information can be updated.

**Expected Result:**

- Updated values stored
- HTTP 200 returned
- Data persists after retrieval

---

## TC005 - Delete Existing Booking

**Objective:** Verify a booking can be deleted.

**Expected Result:**

- Booking removed successfully
- HTTP 201 or 200 returned
- Deleted booking unavailable afterwards

---

## TC006 - Generate Authentication Token

**Objective:** Verify valid credentials generate a token.

**Expected Result:**

- Token generated
- Token returned in response
- HTTP 200 returned

---

## TC007 - Create Multiple Bookings

**Objective:** Verify multiple bookings can be created sequentially.

**Expected Result:**

- Unique booking identifiers generated
- No data corruption

---

## TC008 - Verify Booking Data Persistence

**Objective:** Verify booking information remains available after creation.

**Expected Result:**

- Booking data unchanged
- Correct data retrieved

---

## TC009 - Validate Booking Response Schema

**Objective:** Verify response structure matches API contract.

**Expected Result:**

- Schema validation successful
- Required fields present

---

## TC010 - Verify Content Type Headers

**Objective:** Verify API returns correct content type.

**Expected Result:**

- Content-Type header present
- Application/JSON returned

---

# Negative Test Scenarios

## TC011 - Create Booking Without First Name

**Objective:** Verify validation occurs when first name is missing.

**Expected Result:**

- Validation error returned
- Request rejected

---

## TC012 - Create Booking Without Last Name

**Objective:** Verify validation occurs when surname is missing.

**Expected Result:**

- Validation error returned
- Request rejected

---

## TC013 - Create Booking With Empty Request Body

**Objective:** Verify empty payload handling.

**Expected Result:**

- Request rejected
- Appropriate error message returned

---

## TC014 - Create Booking With Null Values

**Objective:** Verify null values are handled correctly.

**Expected Result:**

- Request rejected
- Validation failure returned

---

## TC015 - Create Booking With Invalid Date Format

**Objective:** Verify date validation.

**Expected Result:**

- Request rejected
- Validation message returned

---

## TC016 - Retrieve Non-Existent Booking

**Objective:** Verify handling of invalid identifiers.

**Expected Result:**

- HTTP 404 returned
- Error message returned

---

## TC017 - Update Non-Existent Booking

**Objective:** Verify handling of invalid update operations.

**Expected Result:**

- HTTP 404 returned
- Update not performed

---

## TC018 - Delete Non-Existent Booking

**Objective:** Verify handling of invalid deletion operations.

**Expected Result:**

- Appropriate error returned
- No unintended data changes

---

# Security Test Scenarios

## TC019 - Invalid Authentication Credentials

**Objective:** Verify authentication validation.

**Expected Result:**

- Access denied
- HTTP 401 returned

---

## TC020 - Missing Authentication Token

**Objective:** Verify protected endpoints cannot be accessed.

**Expected Result:**

- Access denied
- HTTP 403 or 401 returned

---

## TC021 - Expired Authentication Token

**Objective:** Verify expired sessions are rejected.

**Expected Result:**

- Access denied
- Appropriate error returned

---

## TC022 - SQL Injection Attempt

**Payload Example**

```json
{
  "firstname": "' OR '1'='1"
}
```

**Expected Result:**

- Request rejected or sanitised
- No system impact

---

## TC023 - Script Injection Attempt

**Payload Example**

```json
{
  "firstname": "<script>alert('test')</script>"
}
```

**Expected Result:**

- Input rejected or sanitised
- No script execution

---

## TC024 - Authorisation Validation

**Objective:** Verify users cannot access restricted resources.

**Expected Result:**

- Access denied
- Appropriate response code returned

---

## TC025 - Sensitive Data Exposure Check

**Objective:** Verify confidential data is not exposed.

**Expected Result:**

- No passwords returned
- No tokens exposed
- No sensitive information leaked

---

# Performance Test Scenarios

## TC026 - Booking Creation Response Time

**Objective:** Verify booking creation response times.

**Expected Result:**

- Response time < 500ms

---

## TC027 - Booking Retrieval Response Time

**Objective:** Verify retrieval performance.

**Expected Result:**

- Response time < 500ms

---

## TC028 - Booking Update Response Time

**Objective:** Verify update performance.

**Expected Result:**

- Response time < 500ms

---

## TC029 - Booking Deletion Response Time

**Objective:** Verify deletion performance.

**Expected Result:**

- Response time < 500ms

---

## TC030 - Consecutive Request Stability

**Objective:** Verify consistent performance during repeated requests.

**Expected Result:**

- No degradation observed
- Error rate remains acceptable

---

# Regression Test Scenarios

## TC031 - Booking Creation Regression

**Expected Result:**

- Functionality unchanged
- Previous defects remain resolved

---

## TC032 - Booking Retrieval Regression

**Expected Result:**

- Functionality unchanged
- Existing behaviour maintained

---

## TC033 - Booking Update Regression

**Expected Result:**

- Updates continue functioning correctly

---

## TC034 - Authentication Regression

**Expected Result:**

- Authentication controls remain effective

---

## TC035 - Validation Rules Regression

**Expected Result:**

- Existing validation rules continue to function

---

# Scenario Traceability Matrix

| Risk ID | Scenario Coverage |
|----------|----------|
| R001 Booking Creation Failure | TC001, TC026, TC031 |
| R002 Invalid Booking Data Accepted | TC011 - TC015, TC035 |
| R003 Authentication Bypass | TC019 - TC024, TC034 |
| R004 Incorrect Booking Updates | TC004, TC017, TC033 |
| R005 Booking Deletion Errors | TC005, TC018 |
| R006 Slow API Responses | TC026 - TC030 |
| R007 Incorrect Error Messages | TC011 - TC018 |
| R008 API Contract Changes | TC009 |
| R009 Missing Validation Rules | TC011 - TC015, TC035 |
| R010 Service Unavailable | TC030 |

---

# Execution Priority

## Priority 1

- TC001
- TC004
- TC006
- TC011
- TC012
- TC019
- TC020
- TC022
- TC024

## Priority 2

- TC002
- TC003
- TC005
- TC015
- TC016
- TC025
- TC026
- TC027

## Priority 3

- Remaining scenarios

---

# Approval

This document defines the primary API test scenarios for the Booking Platform Quality Engineering Showcase project.

The scenarios will evolve as requirements, risks and implementation details change.

---

**Author:** Paul  
**Project:** Booking Platform Quality Engineering Showcase  
**Version:** 1.0
