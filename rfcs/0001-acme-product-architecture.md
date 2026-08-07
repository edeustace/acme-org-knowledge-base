# RFC 0001 — Acme Product architecture

|  |  |
|---|---|
| **Status** | proposed |
| **Author** | ede |
| **Created** | 2026-08-07 |

## Summary

This RFC defines the high-level architecture for Acme Product. The aim is a system
that is simple to operate with a small team, kind to new joiners, and cheap to run
at our current scale.

## Goals

- A single deployable service backed by Postgres.
- Everything on the cloud account we already have — no new vendors.
- This knowledge base stays the source of truth for how the system actually works.

## Non-goals

- Multi-region and high availability in this iteration.
- A service mesh, or any other distribution we don't yet need.

## Architecture

One service, deployed as a container, talking to Postgres, with a job queue for
background work:

```
client ──► api ──► postgres
                └──► queue ──► workers
```

The API is the only entry point. Workers consume jobs and share the same codebase
and database, so there is nothing to reconcile between them besides the data itself.

## Decisions

1. **Single service, not microservices.** Two engineers can operate this today;
   splitting it now buys nothing but operational load.
2. **Postgres over a document store.** The data is relational, and the tooling
   around Postgres is better than anything else we evaluated.
3. **Config via environment; secrets in Secret Manager.** No config files baked
   into images, and nothing secret commited to git.

## Open questions

- The horizontal-scaling story once the queue becomes the bottleneck.
- Start a second region before or after the first major release?

## References

- [Engineering principles](../handbook/engineering-principles.md)
- [RFC process](./README.md)