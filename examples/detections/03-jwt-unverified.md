# Demo 3: JWT signature check disabled

Engines shown: `jwt_guard`. Illustrative sample, written fresh for this
showcase. Finding is redacted, not a real scan dump.

## Vulnerable sample

```python
# DO NOT DO THIS - tokens are accepted without verifying the signature
def current_user(token):
    payload = decode(token, options={"verify_signature": False})
    return payload["sub"]
```

## What Orion reports (redacted)

```text
HIGH   EXAMPLE-REDACTED   auth.py:4   JWT accepted without verification
```

## Fixed sample

```python
def current_user(token):
    payload = decode(token, key=PUBLIC_KEY, algorithms=["RS256"])
    return payload["sub"]
```

What this shows: authentication shortcuts that accept forged tokens get
flagged at the call site, so login stays tied to verified signatures.
