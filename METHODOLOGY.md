# Contribution snapshot methodology

The profile snapshot uses deliberately narrow, auditable repository metrics:

> **351 merged pull-request records and 2,153 unique non-merge commits authored by `parkster127` across 8 Hello Sushi repositories, from 2026-01-01 UTC through 2026-09-25T19:30:22Z.**

## Scope

- The scope is the Hello Sushi client project: eight repositories, with four current product codebases represented in the snapshot.
- Repository names and private pull-request URLs are intentionally omitted because the client code is private.
- The reporting window is **2026-01-01T00:00:00Z through 2026-09-25T19:30:22Z**, inclusive.

## Counting rule

- Count one record for each pull request that is **merged** and whose author is `parkster127`.
- Deduplicate by repository plus pull-request number (`repository + PR number`) before counting.
- Keep release, synchronization, backport, promotion, and deployment pull requests in the count. They are real delivery records, but they are not silently relabeled as unique features.
- The result is a contribution record count. It is **not** a count of unique features, deployments, customers, transactions, or lines of code.
- No activity widget or inaccessible private link is used to produce the number.

## Commit counting rule

- Count distinct commit SHAs authored by `parkster127` on the eight default branches in scope.
- Exclude 434 merge commits (`parentCount > 1`). Empty commits were not filtered separately.
- There were no cross-repository duplicate SHAs in the normalized result.
- **2,153** is a repository snapshot, not the official GitHub contribution-graph total.

## Diff-volume context

The scoped PR records contain 1,197,465 additions and 234,884 deletions, for 1,432,349 accumulated diff lines. These values include regenerated, repeated, imported, and release changes; they are not unique handwritten lines of code.

## Context

The broader account snapshot is a different scope and is not used as the profile headline. Private client work is described publicly only at the capability level and only without customer data or private implementation links.
