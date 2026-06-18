# 2. Use pre-commit for local quality gates

<!-- In vim, use !!date -I to get current date. -->

Date: 2026-06-18

## Status

<!-- Proposed, Accepted, Deprecated, Superseded, or Rejected -->

Accepted

## Context

This template ships quality and security gates so new
projects inherit them from day one. The same checks run
locally and in CI, giving contributors fast feedback
before they push.

We consolidate overlapping tools and split checks by
cost: fast checks on commit, heavier and security scans
on push. Per-hook rationale lives as inline comments in
`.pre-commit-config.yaml`, not in this ADR.

See [pre-commit](https://pre-commit.com) for the
framework.

## Decision

- [ ] Use pre-commit to orchestrate local quality and
  security gates, mirroring CI.
- [ ] Consolidate the Python lint and format toolchain.
- [ ] Run heavy and security scans at push time, and
  pin container images by digest.

## Consequences

Pros:

- One feedback loop shared by developers and CI.
- Fewer tools to install and keep in sync.
- Secrets and misconfigurations are caught before they
  reach the remote.

Cons:

- Some scans need Docker on the contributor machine.
- Push-time scans add latency to `git push`.
- Hook revisions need periodic bumping to stay current.
