# Pull Request Review Checklist

Use this as a repeatable reference. Mark items that apply; record evidence or follow-up links for anything left unchecked.

## 1. Review setup and scope

- [ ] Read the PR title, description, linked issue, acceptance criteria, and design notes.
- [ ] Confirm the change solves the stated problem and stays within scope.
- [ ] Identify affected users, services, data, environments, and deployment risks.
- [ ] Inspect the diff against the correct base branch, including renamed and deleted files.
- [ ] Check commits for accidental debugging code, generated artifacts, secrets, or unrelated refactors.
- [ ] Read surrounding code and callers, not only changed lines.
- [ ] Check repository conventions, contribution guidance, required checks, and ownership rules.
- [ ] Decide which conditional sections apply: API, UI, database, concurrency, infrastructure, dependencies, or migrations.

## 2. Correctness and behavior

- [ ] Verify the implementation matches the requirement and acceptance criteria.
- [ ] Trace the main success path end to end.
- [ ] Check inputs, outputs, state transitions, invariants, and side effects.
- [ ] Confirm all callers and consumers remain compatible.
- [ ] Check error handling: errors are detected, actionable, observable, and not silently ignored.
- [ ] Verify retries, timeouts, cancellation, cleanup, and idempotency where relevant.
- [ ] Check ordering, atomicity, transactions, consistency, and duplicate-event behavior.
- [ ] Confirm defaults and fallback behavior are intentional and safe.
- [ ] Check feature flags, rollout behavior, configuration, and backward/forward compatibility.

## 3. API checks

- [ ] Verify status codes, request and response schemas, validation, and error formats.
- [ ] Check authentication, authorization, tenant isolation, and sensitive-data handling.
- [ ] Verify pagination, sorting, filtering, versioning, and backward compatibility.
- [ ] Check rate limits, timeouts, retries, and idempotency for externally visible operations.
- [ ] Confirm API documentation and client contracts are updated where needed.

## 4. UI checks

- [ ] Verify loading, success, empty, error, disabled, permission, and responsive states.
- [ ] Check keyboard navigation, focus management, labels, contrast, and screen-reader behavior.
- [ ] Confirm user input is validated and actionable error messages are shown.
- [ ] Check state persistence, refresh behavior, duplicate submissions, and unsaved changes.
- [ ] Verify supported browsers, viewport sizes, localization, and text overflow where relevant.

## 5. Database and migration checks

- [ ] Verify constraints, indexes, query semantics, transaction boundaries, and migration ordering.
- [ ] Check migration safety for existing data, rollback behavior, and repeated execution.
- [ ] Confirm reads and writes remain compatible during rolling deployments.
- [ ] Check locking, isolation, performance, pagination, and large-data behavior.
- [ ] Verify backups, retention, privacy, and cleanup requirements where applicable.

## 6. Concurrency and distributed-system checks

- [ ] Identify race conditions, lost updates, duplicate processing, and out-of-order events.
- [ ] Verify locking, leases, optimistic concurrency, and conflict resolution.
- [ ] Check queue behavior, delivery guarantees, dead-letter handling, and replay safety.
- [ ] Confirm timeouts, cancellation, backpressure, circuit breakers, and graceful degradation.
- [ ] Verify operations are safe to retry and have clear idempotency boundaries.

## 7. Security and privacy

- [ ] Check authorization at every trust boundary; do not rely on client-side controls.
- [ ] Validate and safely encode untrusted input.
- [ ] Check for injection, path traversal, SSRF, unsafe deserialization, and insecure file handling.
- [ ] Confirm secrets, tokens, personal data, and credentials are not logged or committed.
- [ ] Verify encryption, key management, secure defaults, dependency advisories, and least privilege.
- [ ] Check audit logging and privacy, retention, deletion, and data-minimization requirements.

## 8. Infrastructure and operations

- [ ] Verify configuration, environment variables, permissions, networking, and resource limits.
- [ ] Check deployment ordering, health probes, startup and shutdown behavior, and rollback plans.
- [ ] Confirm observability: logs, metrics, traces, alerts, dashboards, and actionable diagnostics.
- [ ] Check scaling, quotas, cost impact, regional behavior, backups, and disaster recovery.
- [ ] Verify infrastructure changes are reproducible and documented.

## 9. Dependencies and maintainability

- [ ] Review dependency additions, removals, versions, licenses, and known vulnerabilities.
- [ ] Confirm lock files, generated code, build scripts, and runtime requirements are updated.
- [ ] Check naming, structure, types, comments, and consistency with local conventions.
- [ ] Remove dead code, temporary workarounds, debug output, and unnecessary complexity.
- [ ] Confirm documentation, examples, release notes, and configuration references are current.

## 10. Testing and verification

- [ ] Run focused tests for the changed behavior and relevant edge cases.
- [ ] Add or update tests for new behavior, regressions, failure paths, and security-sensitive logic.
- [ ] Run formatting, linting, type checks, builds, and required repository checks.
- [ ] Verify test data does not contain secrets or inappropriate personal information.
- [ ] Test rollback, migration, feature-flag, and deployment scenarios when applicable.
- [ ] Record commands run, results, limitations, and any follow-up work.

## 11. Final review decision

- [ ] All blocking findings are resolved or explicitly accepted by the appropriate owner.
- [ ] Remaining comments are clear, actionable, and prioritized.
- [ ] The diff contains no unrelated changes or accidental artifacts.
- [ ] Required approvals, checks, and ownership reviews are complete.
- [ ] The PR is ready to merge, or the reason for requesting changes is documented.

### Review notes

- Findings:
- Evidence and links:
- Follow-up items:
- Final decision:
