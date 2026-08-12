<p align="center">
  <img src="./portal-logo.png" alt="Portal" width="128">
</p>

<h1 align="center">Portal</h1>

Portal is a private messaging app for DMs, group chats, media, and calls. It encrypts messages on your device before they leave, so the server can deliver and sync them without having the keys to read them. Every conversation—including a two-person DM—uses Messaging Layer Security (MLS), the same protocol built for secure group messaging.

## How it works

Portal keeps cryptography on the client and delivery on the server.

```text
React / iOS clients
  plaintext · MLS state · attachment keys · identity keys
                          │
                          │ WebAuthn + REST / Socket.IO
                          │ public MLS framing + opaque ciphertext
                          ▼
Portal backend
  authentication · policy · epoch ordering · delivery · sync
                          │
            ┌─────────────┼─────────────┐
            ▼             ▼             ▼
       PostgreSQL       Redis 8    Cloudflare R2
       account state    timelines   encrypted media
```

The server sees account identity, membership, roles, timing, routing, ciphertext size, and the public parts of MLS commits. It does not receive message plaintext, MLS group secrets, attachment keys, or identity private keys.

## Backend responsibilities

| Area | Implementation |
|---|---|
| Authentication | WebAuthn passkeys, device-scoped sessions, trusted device pairing |
| Authorization | Conversation membership, moderation, roles, and MLS leaf-to-device binding |
| MLS coordination | Public commit validation and compare-and-append epoch changes |
| Messaging | Ordered ciphertext storage without making the server an MLS group member |
| Synchronization | Canonical REST timelines, ETags, bounded replay, and revision manifests |
| Realtime | Socket.IO fan-out and invalidation events; REST remains the source of truth |
| Media | Client-side AES-GCM encryption with opaque objects stored in R2 |
| Calls | WebRTC mesh and SFU-routed group calls with client-side SFrame encryption |

## MLS commit ordering

An MLS membership change also changes the group's epoch. When two clients submit commits for the same epoch, the backend accepts one and returns an epoch conflict for the other. The losing client replays the canonical timeline, rebuilds its commit against the new epoch, and retries.

Welcome messages use a peek-then-consume flow. A joining device saves its MLS state locally before deleting the server copy, so a crash cannot destroy its only usable join material.

## Stack

| Layer | Technology |
|---|---|
| Backend | Python 3.13, FastAPI, async SQLAlchemy, Pydantic, Socket.IO, py-webauthn |
| Web | React 19, TypeScript, Vite, Zustand, Tailwind v4, Zod, Motion |
| Native | Swift and SwiftUI |
| Cryptography | MLS (RFC 9420), AES-GCM attachments, SFrame calls |
| State | PostgreSQL 16, Redis 8, Alembic migrations |
| Edge | Cloudflare R2, Realtime TURN/SFU, internal imgproxy |

## Backend layout

Most domains use three layers:

```text
routes.py       HTTP, dependency injection, schema validation
service.py      orchestration and business rules
repository.py   SQLAlchemy persistence
```

Domain imports follow an enforced acyclic graph, and cross-domain ORM relationships are not allowed. Domains call typed services and pass foreign-key identifiers across boundaries instead.
