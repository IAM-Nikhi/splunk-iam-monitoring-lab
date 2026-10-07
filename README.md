# Splunk IAM Monitoring Lab

Practical monitoring patterns for IAM operations.

## Monitoring Scenarios
- repeated failed sign-ins
- disabled identity authentication
- privileged group changes
- provisioning failures
- post-termination activity
- connector errors

## Example SPL

```spl
index=iam action=failure
| stats count by user
| sort - count
```

```spl
index=iga event_type=provisioning status=failed
| stats count by application error_code
```

## Exercise
Review event data and identify suspicious activity, repeated provisioning failures, and privileged-access changes.
