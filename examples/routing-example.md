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
Primary agent: Carla
Support: Nelson
QA: John
Reason: auth, data integrity, user-facing risk
Output: decision, plan, risks, validation
```
