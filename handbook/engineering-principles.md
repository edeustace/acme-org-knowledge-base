# Engineering principles

Guiding principles, not rules. When two options feel equal, these break the tie.

1. **Write things down.** The answer to "how does X work?" belongs in this
   knowledge base, discoverable in Lens, not in someone's head.
2. **Boring over clever.** Prefer the standard tool, the obvious name, and the
   simple implementation. Novelty is a cost we pay once; predictability pays every
   day.
3. **Small, reviewable changes.** Never a 2,000-line PR. If a change can't be
   reviewed in a sitting, it's not ready to review.
4. **The repo is the product.** Clear prose, good structure, and accurate docs are
   features. Someone landing here at 5pm on a Friday should be able to get oriented
   quickly.
5. **Comments document decisions, not code.** If a comment explains *why*, keep it.
   If it restates *what*, delete it.
6. **Automate the boring parts.** Anything done more than twice should become a
   command, a script, or a check.

## In practice

- Prefer an accepted RFC over a fresh opinion. If an RFC is wrong, change the RFC
  first, then the code.
- Merge small, ship often, and keep `main` green.