# Demo 1: hardcoded secret

Engines shown: `secrets`. Illustrative sample, written fresh for this
showcase. Finding is redacted, not a real scan dump.

## Vulnerable sample

```python
# DO NOT DO THIS - key committed next to the code that uses it
API_KEY = "REDACTED-EXAMPLE-KEY-DO-NOT-USE"

def fetch_billing_report():
    return call_billing_api(API_KEY)
```

## What Orion reports (redacted)

```text
HIGH   EXAMPLE-REDACTED   billing.py:2   hardcoded credential material
```

## Fixed sample

```python
import os

# Key lives in the environment, never in the file
API_KEY = os.environ["BILLING_API_KEY"]

def fetch_billing_report():
    return call_billing_api(API_KEY)
```

What this shows: credentials committed beside code get flagged with
file and line, so they can be rotated and moved out of the repo.
