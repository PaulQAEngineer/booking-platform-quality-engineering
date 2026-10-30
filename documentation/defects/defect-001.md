# DEFECT-001

## Summary

Booking creation accepts an empty surname value.

---

## Defect Information

| Field | Value |
|---------|---------|
| ID | DEFECT-001 |
| Title | Booking Creation Accepts Empty Surname |
| Severity | High |
| Priority | High |
| Status | Open |
| Test Scenario | TC012 |
| Reported By | Paul |
| Date Reported | October 2026 |

---

## Description

The booking creation endpoint accepts requests where the surname field is empty.

This allows incomplete customer records to be created.

---

## Steps to Reproduce

1. Create a booking request.
2. Set surname to an empty string.
3. Submit request.

### Request

```json
{
  "firstname": "John",
  "lastname": "",
  "totalprice": 100,
  "depositpaid": true
}
```

---

## Expected Result

API should reject the request and return a validation error.

```http
400 Bad Request
```

---

## Actual Result

Booking created successfully.

```http
201 Created
```

---

## Impact

Invalid customer records can be stored within the system.

---

## Recommendation

Implement mandatory field validation for surname before processing booking creation requests.
