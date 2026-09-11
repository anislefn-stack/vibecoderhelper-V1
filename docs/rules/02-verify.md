# Verification Checklist

## Before claiming done — I perform these

1. **Build:** Confirm the project builds successfully with no reported build errors.

2. **Types:** If TypeScript was changed, confirm there are no resulting type errors.

3. **Runtime:** Exercise the changed flow and check for runtime/console errors.

4. **UI Viewport Verification:**
   - If interactive browser testing or preview visual logs are available: Actually exercise the interface at both desktop and mobile widths.
   - If browser testing is NOT available: inspect responsive implementation and mark visual behavior **NOT VERIFIED**.
   - _CRITICAL:_ Never treat the mere presence of responsive utility classes as evidence that the UI was visually verified.

5. **UI States:** When relevant, verify loading, empty, success, error, and invalid-input states.

6. **Edge Cases:** Check relevant boundary conditions, invalid inputs, unusual states, and failure paths.

7. **Accessibility:** When UI changes are involved, check relevant accessibility basics such as keyboard interaction, labels, focus behavior, and readable contrast.

8. **Data:** If database/schema/RLS behavior changed, inspect the resulting configuration and access rules.

9. **Auth:** If authentication or authorization changed, test the relevant authenticated and unauthenticated flows.

10. **Network:** If APIs or integrations changed, inspect the relevant requests and responses.

11. **Tests:** Run the existing relevant test suite when one exists.

12. **Regression Scope:** Check the changed functionality and the most likely affected existing functionality. Never claim full-project verification unless a full suite was actually run.

## I must flag for human verification

- Requirement match: I implemented what I understood; the user must confirm it matches their intended result.
- Multi-role authorization: test every relevant role when not all roles can be exercised.
- Live third-party operations: real payments, emails, external writes, or other actions requiring live credentials/state.
- Real-device behavior: desktop/mobile browser checks do not certify physical devices.
- Untested adjacent functionality: I did not verify unrelated or non-obvious flows.
- Visual/UX judgment: functional correctness does not prove that the result looks or feels right.

## Reporting Rule

### Evidence Rule

Only claim a verification item passed when that specific check was actually performed. Do not infer that an item passed because the code appears correct or the build succeeded. When a required check was not performed, explicitly report it as **NOT VERIFIED**.
