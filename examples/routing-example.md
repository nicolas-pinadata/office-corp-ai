# Example: Routing

Input:

> Fix this typo in the homepage.

Expected routing:

```txt
Budget: Lean
Primary agent: Nelson
QA: No
Reason: trivial reversible change
Output: patch summary
```

Input:

> Redesign the authentication flow and migrate existing users.

Expected routing:

```txt
Budget: Deep Work
Primary agent: Daniel
Support: Nelson
QA: Monica
Reason: auth, data integrity, user-facing risk
Output: decision, plan, risks, validation
```
