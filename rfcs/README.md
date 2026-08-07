# RFCs

RFCs are where the org agrees on meaningful decisions *before* the code lands. They
are living documents: propose, discuss, accept, ship.

## Status

| Status | Meaning |
|---|---|
| `draft` | Being written, no decision |
| `proposed` | Open for review — comment on the doc in Lens |
| `accepted` | Decision made, implementation in progress |
| `done` | Shipped and in operation |
| `superseded` | Replaced by a later RFC |

## Active

- [0001 — Acme Product architecture](./0001-acme-product-architecture.md) — `proposed`

## How to propose

1. Number the RFC as the next free `000N`.
2. Fill in summary, goals, decisions, and open questions.
3. Open a PR, set status to `proposed`, and post the link.
4. Collect review as inline comments; resolve them as they're addressed.
5. When it settles, set `accepted`. After implementation ships, `done`.

## Conventions

- RFCs that change an existing decision must mark the older one `superseded`.
- Keep them short enough that someone can read one in a lunch break.