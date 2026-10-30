# DEFECT-002

## Summary

Expired authentication tokens continue to provide access to protected endpoints.

---

## Defect Information

| Field | Value |
|---------|---------|
| ID | DEFECT-002 |
| Title | Expired Token Accepted |
| Severity | Critical |
| Priority | Critical |
| Status | Open |
| Test Scenario | TC021 |
| Reported By | Paul |
| Date Reported | October 2026 |

---

## Description

API accepts expired authentication tokens when accessing protected resources.

---

## Steps to Reproduce

1. Generate valid token.
2. Allow token to expire.
3. Access protected endpoint using expired token.

---

## Expected Result

Access denied.

```http
401 Unauthorized
```

---

## Actual Result

Request processed successfully.

```http
200 OK
```

---

## Impact

Potential unauthorised access to sensitive booking data.

---

## Recommendation

Validate token expiry before authorising protected requests.
