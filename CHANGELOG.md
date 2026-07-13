# Changelog

## v1.0.0 — ZavedyaID first release

This is ZavedyaID's first packaged release, built on top of the `itsliaaa/baileys` enhanced fork
(itself built on WhiskeySockets/Baileys). No message-handling logic was rewritten in this release —
the changes are structural and cosmetic:

### Changed
- Renamed the compiled output folder `lib/` → `core/` (updated `package.json` `main`/`types`/`files`
  accordingly, and the one internal URL that referenced the old path).
- Split the 33-file `Utils/` folder into five topic subfolders: `auth/`, `crypto/`, `messages/`,
  `network/`, `misc/`. Every cross-reference (within `Utils/`, and from other folders into `Utils/`)
  was recomputed and re-verified, not just text-replaced.
- Package metadata rebranded to `@zavedyaid/baileys`, version bumped to `1.0.0`.
- `LICENSE` updated to list all three copyright holders in the actual credit chain (WhiskeySockets,
  Lia Wynn/itsliaaa, ZavedyaID) — nothing removed, only added.
- `README.md` reorganized with an explicit "About This Fork" / credit-chain section up top, and the
  original author's attribution notice preserved as a direct, clearly-marked quote rather than left
  ambiguous about who wrote it.
- Added `STRUCTURE.md` (folder guide) and this `CHANGELOG.md`.

### Verified
- All 303 relative imports in `.js` files and 103 in `.d.ts` files resolve correctly after the move.
- Every `.js` file passes `node --check` (no syntax errors introduced).
- No functional/behavioral code was altered — only file locations, package metadata, and docs.

### Not changed
- No API surface changes. Anything importable from upstream `itsliaaa/baileys` is still importable
  the same way from `@zavedyaid/baileys`.
