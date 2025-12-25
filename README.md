# PAPER

**Paper-thin Assertions, Pathetically Exercising Reality**

**Install**

```sh
pipx install cursorcult
cursorcult link PAPER
```

Rule file format reference: https://cursor.com/docs/context/rules#rulemd-file-format

**When to use**

- You are replacing "No Mocks" or "Limit Mocks" rules with something stronger.
- You want to catch "unreal" tests that pass CI but fail in production.
- You want a shared vocabulary for calling out brittle/fake tests.

**What it enforces**

- **Reality**: Tests must exercise real user paths.
- **Adequacy**: Mocks are allowed only if the resulting behavior remains real.
- **Workflow**: Isolated unit tests are insufficient if they don't map to real usage.

**Usage in Code Review**

Use PAPER as a noun to diagnose the state of the test suite, not just to critique style.

- “This test passes, but it’s **PAPER**.” (It asserts nothing of value)
- “The logic is covered, but it’s **PAPER**.” (It uses synthetic state impossible in production)
- “We’re accumulating **PAPER** around the payment workflow.” (We have many tests, but none verify the money moves)
- “The failure wasn’t subtle — the tests were **PAPER**.” (We trusted a suite that wasn't exercising reality)

**Credits**

- Developed by Will Wieselquist. Anyone can use it.