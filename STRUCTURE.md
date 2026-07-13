# 📁 Project Structure — @zavedyaid/baileys v1.0.0

This is the ZavedyaID v1 restructure of the itsliaaa-enhanced Baileys fork. Two structural changes
were made from upstream, both verified to keep every import path resolving correctly:

1. The compiled output folder was renamed from `lib/` to `core/`.
2. The 33-file `Utils/` folder was split into five topic subfolders so related code sits together.

```
zavedyaid-baileys/
├── core/
│   ├── index.js                # Package entry point
│   ├── Defaults/                # Default configs, browser fingerprints, base socket config
│   ├── Signal/                  # Signal protocol (E2E encryption) implementation
│   │   └── Group/                # Group (sender-key) encryption
│   ├── Socket/                   # Core WebSocket connection + all socket features
│   │   └── Client/                 # Low-level WebSocket client
│   ├── Store/                     # In-memory store helpers (chats, contacts, messages)
│   ├── Types/                      # Shared type definitions
│   ├── Utils/                      # Shared utilities, split by topic (see below)
│   │   ├── auth/                    # Auth state: multi-file, single-file, sqlite, key management
│   │   ├── crypto/                  # Crypto primitives, signal helpers, LT-hash, noise handshake
│   │   ├── messages/                 # Message encode/decode, media, retries, stanza acks
│   │   ├── network/                   # Connection validation, reporting, offline-node handling
│   │   ├── misc/                       # Generics, logger, mutex, chat/business/link-preview helpers
│   │   └── index.js                     # Re-exports everything (public surface unchanged)
│   ├── WABinary/                          # WhatsApp binary node (de)serialization
│   ├── WAM/                                 # WhatsApp analytics/metrics encoding
│   └── WAUSync/                               # User sync query protocols
├── WAProto/                # Protobuf-generated WhatsApp message definitions
├── engine-requirements.js  # Node.js version guard (>=20 required)
├── package.json
├── LICENSE                 # MIT — WhiskeySockets, Lia Wynn (itsliaaa), ZavedyaID
├── README.md                # Usage docs + credit chain
├── CHANGELOG.md               # What changed in this v1.0.0 rebuild
└── STRUCTURE.md                 # This file
```

## What did NOT change

The public API is identical — `Utils/index.js` still re-exports everything the same way, so
`import { ... } from '@zavedyaid/baileys'` works exactly as it did upstream. Only internal file
locations moved; every relative import across the whole codebase (303 in `.js`, 103 in `.d.ts`)
was recomputed and verified to resolve correctly, and every file passed a Node.js syntax check
after the move.

## Credit chain

| Layer | Author | Contribution |
|---|---|---|
| 1 | WhiskeySockets | Original Baileys library |
| 2 | Lia Wynn (itsliaaa) | Interactive messages, albums, newsletter media fixes, extra message types |
| 3 | ZavedyaID | `lib/` → `core/` rename, `Utils/` topic split, packaging, v1.0.0 rebrand |

See [`README.md`](README.md) for full usage docs and [`LICENSE`](LICENSE) for the license terms.
