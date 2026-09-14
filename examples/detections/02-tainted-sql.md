# Demo 2: SQL injection via tainted input

Engines shown: `taint`, `sast`. Illustrative sample, written fresh for
this showcase. Finding is redacted, not a real scan dump.

## Vulnerable sample

```python
# DO NOT DO THIS - request input reaches the query unescaped
def get_account(username):
    query = "SELECT * FROM accounts WHERE name = '" + username + "'"
    return db.execute(query)
```

## What Orion reports (redacted)

```text
CRITICAL   EXAMPLE-REDACTED   accounts.py:4   user input reaches SQL sink
```

## Fixed sample

```python
def get_account(username):
    query = "SELECT * FROM accounts WHERE name = %s"
    return db.execute(query, (username,))
```

What this shows: untrusted input flowing into a database call is traced
to the sink and reported at the exact line, with severity reflecting
the risk.
