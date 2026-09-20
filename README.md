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
- **Meet someone new.** Try an encrypted stranger chat without creating a full account.
- **Passwordless sign-in.** Use a passkey with your fingerprint, face or device PIN. No phone number or email required. Pair a new device from one you already trust, and revoke a device's access if you lose it.

**Browser, phone or desktop.** Start in your browser without installing an app, install Portal on your phone, or use the desktop app.

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

Portal uses **MLS (Messaging Layer Security)** for groups, direct messages and stranger chats. Its Rust encryption engine runs in the browser through WebAssembly. A Rust adapter also lets the backend inspect public protocol information without receiving message-decryption keys. Both sides use the same pinned MLS library, with automated checks keeping them in step.

**Recovery matters as much as delivery.** Realtime updates carry complete, versioned state. Reconnecting repairs missed updates, while ordered message history fills the gaps. If two group membership changes happen at once, the client catches up and retries against the new state. A joining device saves its new chat state before acknowledging its encrypted welcome, so an interrupted join can resume.

**Calls use LiveKit with encryption keys derived from MLS.** The media server forwards encrypted audio and video. Attachments are encrypted before upload to S3-compatible storage.

**The architecture is checked, not just documented.** Automated checks enforce code boundaries, keep the generated API client aligned with the backend, and check the shared Rust protocol code. Browser and end-to-end checks exercise the complete flows.

**Built with:** React, TypeScript, Python, FastAPI, Rust, PostgreSQL, Redis and LiveKit.

</details>

---

<sub>This is Portal's public profile. The application source is intended for release under AGPL-3.0.</sub>
