<p align="center">
  <img src="./portal-mark.svg" alt="Portal" width="112">
</p>

<h1 align="center">Portal</h1>

<p align="center">Chat, call and spend time together. On your terms.</p>

<p align="center">
  <img src="https://img.shields.io/badge/privacy-end--to--end%20encrypted-7c3aed?style=flat-square" alt="End-to-end encrypted">
  <img src="https://img.shields.io/badge/login-passkeys-0f766e?style=flat-square" alt="Passkey sign-in">
  <img src="https://img.shields.io/badge/hosting-self--hostable-2563eb?style=flat-square" alt="Self-hostable">
</p>

<p align="center"><a href="https://portalchat.org">Portal</a> · <a href="https://docs.portalchat.org">Documentation</a></p>

---

## What is Portal?

Portal brings **group chats, video calls and shared browsing** into one place for your friends or community. Send a message, share your screen or just hang out together.

Your messages and files are **end-to-end encrypted**. That means they are encrypted on your device and opened on the devices of the people you share them with, without giving Portal the keys to read them. Group conversations, direct messages and stranger chats all get the same protection.

Use Portal as it is, connect your own hosting, or run it yourself.

## 💬 Your people, in one place

- **Group chats & private channels.** Public or invite-only groups, roles, moderation, custom emoji and GIFs. A private group's name, description and artwork are encrypted too. Create restricted channels that only the people you grant access to can read.
- **Voice, video & screen sharing.** Messages, photos, files and calls are end-to-end encrypted, including your screen share. Set disappearing messages with a timer you choose.
- **Watch parties & shared browsing.** Open a shared browser with Rift, let one person take the controls and follow along together. Use hosted hardware or connect your own computer.
- **Passwordless sign-in.** Use a passkey with your fingerprint, face or device PIN. No phone number or email required. Pair a new device from one you already trust, and revoke a device's access if you lose it.

**Browser, phone or desktop.** Start in your browser without installing an app, install Portal on your phone, or use the desktop app.

## 🔎 Discover your next group chat

**Find a community, not just an invite link.** Browse public groups in Explore or search by name or **#tag**. A group's tag gives people a simple way to find it and share it with friends. Private groups stay out of discovery.

## 🎲 Stranger: meet someone new

**Random one-to-one chats.** Get paired with someone new and start talking. Add interest tags to find common ground, see which tags people are waiting under, or jump straight in. Hit **Next** to meet someone else, or block someone you do not want to meet again.

Conversations are **end-to-end encrypted**. Try text chat as a guest without setting up a passkey, or use *incognito mode* to appear under a random alias instead of your usual profile.

## 🌀 Rift: a browser you share

*For watch parties, late-night hangouts and “you have to see this” moments.*

Rift runs a separate browser for your group, rather than broadcasting your own desktop. Everyone watches the same page and hears its audio while one person drives. **Pass the controls** when someone else wants a turn.

Watch something together, explore a website or hang out while a friend browses. Rift opens directly from the chat and does not require starting a call.

Use hosted GPU capacity or pair your own computer. A paired machine waits for a session; connecting it does not leave a browser continuously running.

## 🏡 Hosting, your way

**Just use Portal.** You do not need to own a server or set anything up to chat and hang out.

**Bring your own hosting.** Connect a computer for Rift, your own file storage, or a server for calls. Storage can be an R2 or S3-compatible bucket, or something you host at home. These are separate choices; you do not need to host everything.

Groups can choose their storage, call server and Rift host independently. Keep using Portal while hosting just the parts you want to own. One machine can provide both Rift and calls, with each service enabled separately.

**Self-host the whole thing.** Host Portal for your own group or community with Docker Compose. Your chat server, storage and calls can live on infrastructure you control.

## Contributions beyond Portal

Building Portal has led to **three merged contributions to Amazon's open-source [MLS library](https://github.com/awslabs/mls-rs)**, which helps power Portal's encryption.

[Commit author information #369](https://github.com/awslabs/mls-rs/pull/369) · [Referenced proposals #380](https://github.com/awslabs/mls-rs/pull/380) · [Group tree information #381](https://github.com/awslabs/mls-rs/pull/381)

<details>
<summary><strong>For the technically curious</strong></summary>

<p align="center">
  <img src="https://img.shields.io/badge/source_%26_tests-250k%2B_lines-475569?style=flat-square" alt="250k+ lines across source and tests, excluding generated code">
  <img src="https://img.shields.io/badge/API-20%2B_routers-0f766e?style=flat-square" alt="20+ API routers">
  <img src="https://img.shields.io/badge/frontend-15_domains-7c3aed?style=flat-square" alt="15 frontend domains">
</p>

| Layer | Stack |
| :--- | :--- |
| **Web** | ![React](https://img.shields.io/badge/React-151B23?style=flat-square&logo=react&logoColor=61DAFB) ![TypeScript](https://img.shields.io/badge/TypeScript-151B23?style=flat-square&logo=typescript&logoColor=3178C6) ![Vite](https://img.shields.io/badge/Vite-151B23?style=flat-square&logo=vite&logoColor=646CFF) ![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-151B23?style=flat-square&logo=tailwindcss&logoColor=06B6D4) ![Zustand](https://img.shields.io/badge/Zustand-151B23?style=flat-square) ![Zod](https://img.shields.io/badge/Zod-151B23?style=flat-square&logo=zod&logoColor=408AFF) |
| **Desktop** | ![Electron](https://img.shields.io/badge/Electron-151B23?style=flat-square&logo=electron&logoColor=9FEAF9) |
| **Backend** | ![Python](https://img.shields.io/badge/Python-151B23?style=flat-square&logo=python&logoColor=FFD43B) ![FastAPI](https://img.shields.io/badge/FastAPI-151B23?style=flat-square&logo=fastapi&logoColor=009688) ![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-151B23?style=flat-square&logo=sqlalchemy&logoColor=D71F00) ![Pydantic](https://img.shields.io/badge/Pydantic-151B23?style=flat-square&logo=pydantic&logoColor=E92063) ![Socket.IO](https://img.shields.io/badge/Socket.IO-151B23?style=flat-square&logo=socketdotio&logoColor=white) |
| **Encryption** | ![Rust](https://img.shields.io/badge/Rust-151B23?style=flat-square&logo=rust&logoColor=F5A97F) ![WebAssembly](https://img.shields.io/badge/WebAssembly-151B23?style=flat-square&logo=webassembly&logoColor=A78BFA) ![MLS · RFC 9420](https://img.shields.io/badge/MLS-RFC_9420-475569?style=flat-square&labelColor=151B23) ![AES-GCM](https://img.shields.io/badge/AES--GCM-151B23?style=flat-square) |
| **Sign-in** | ![WebAuthn](https://img.shields.io/badge/WebAuthn-151B23?style=flat-square) ![Passkeys](https://img.shields.io/badge/Passkeys-151B23?style=flat-square) |
| **Calls & Rift** | ![LiveKit](https://img.shields.io/badge/LiveKit-151B23?style=flat-square&logo=livekit&logoColor=white) ![WebRTC](https://img.shields.io/badge/WebRTC-151B23?style=flat-square&logo=webrtc&logoColor=white) ![GPU-backed browsing](https://img.shields.io/badge/GPU--backed_browsing-151B23?style=flat-square) |
| **Data & storage** | ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-151B23?style=flat-square&logo=postgresql&logoColor=699ECA) ![Redis](https://img.shields.io/badge/Redis-151B23?style=flat-square&logo=redis&logoColor=FF4438) ![S3-compatible](https://img.shields.io/badge/S3--compatible-151B23?style=flat-square) ![Cloudflare R2](https://img.shields.io/badge/Cloudflare_R2-151B23?style=flat-square&logo=cloudflare&logoColor=F38020) |
| **Self-hosting** | ![Docker Compose](https://img.shields.io/badge/Docker_Compose-151B23?style=flat-square&logo=docker&logoColor=2496ED) · Bring your own GPU, storage and call servers |

<sub>Line count includes source and tests, excluding generated code.</sub>

</details>

---

<sub>This is Portal's public profile. The application source is intended for release under AGPL-3.0.</sub>
