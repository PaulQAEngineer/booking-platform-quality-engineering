# DEFECT-003

## Summary

Retrieving a non-existent booking returns an internal server error.

---

## Defect Information

| Field | Value |
|---------|---------|
| ID | DEFECT-003 |
| Title | Invalid Booking ID Returns 500 Error |
| Severity | Medium |
| Priority | Medium |
| Status | Open |
| Test Scenario | TC016 |
| Reported By | Paul |
| Date Reported | October 2026 |

---

## Description

When an invalid booking identifier is supplied, the API returns an internal server error rather than a meaningful client error response.

---

## Steps to Reproduce

1. Retrieve booking.
2. Supply a non-existent booking ID.
3. Submit request.

---

## Expected Result

```http
404 Not Found
```

Appropriate error message returned.

---

## Actual Result

```http
500 Internal Server Error
```

---

## Impact

Incorrect error handling and poor user experience.

---

## Recommendation

Implement validation for non-existent booking identifiers and return an appropriate client-side error response.
