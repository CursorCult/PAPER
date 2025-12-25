---
description: "Tests must exercise real user behavior; unreality is PAPER."
alwaysApply: true
---

# **PAPER**

**P**aper-thin
**A**ssertions,
**P**athetically
**E**xercising
**R**eality

---

## Scope

PAPER replaces rules that attempt to control *how* tests are written
(e.g. *no mocks*, *minimal mocks*).

PAPER instead judges **whether tests represent real use**.

Mocks are not the violation.
**Unreal behavior is the violation.**

---

## Invariant

> Tests must exercise real user behavior.
> Assertions that pass without surviving real workflows are **PAPER**.

---

## Violation

> If a real user path fails while tests pass, the test suite contains **PAPER**.

This includes (but is not limited to):

* isolated function calls that users never perform directly
* mocked or synthetic state that bypasses real transitions
* tests that validate outputs without executing the full workflow
* “status”, “list”, or “inspect” commands tested without preceding real mutations

---

## Remedy

> Replace PAPER tests with workflow-level tests **before** fixing code.

Fixes applied while PAPER remains are invalid.

---

## Why this replaces `nomocks` / `minimal mocks`

* `nomocks` bans a tool
* `minimal mocks` regulates quantity
* **PAPER judges adequacy**

A test may use mocks and still be REAL.
A test may use zero mocks and still be PAPER.

Only reality matters.

---

## Review Language (intentional)

Use PAPER as a noun, not advice.

* “This test is PAPER.”
* “Status is covered, but it’s PAPER.”
* “We’re accumulating PAPER around CLI workflows.”
* “The failure wasn’t subtle — the tests were PAPER.”

If someone asks *why*, point to the invariant. No debate required.
