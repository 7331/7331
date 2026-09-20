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

Portal is a place for your friends, your group or your community. Message each other, jump into a call, share your screen or open a browser together, all in one place.

Your messages and files are end-to-end encrypted. That means they are encrypted on your device and opened on the devices of the people you share them with.

Use Portal as it is, connect your own hosting, or run it yourself.

## What you can do

- **Make a space for your people.** Public or invite-only groups, channels, roles, moderation, custom emoji and GIFs.
- **Keep the conversation going.** Encrypted messages, photos and files, plus voice, video and screen sharing. Set disappearing messages when you want them.
- **Browse together with Rift.** Open a shared browser, let one person take the controls and follow along together. Use hosted hardware or connect your own computer.
- **Meet someone new.** Try an encrypted stranger chat without creating a full account.
- **Skip the passwords.** Sign in with a passkey using your fingerprint, face or device PIN. No phone number or email required.

Use Portal in your browser, install it on your phone, or use the desktop app.

## Hosting, your way

**Just use Portal.** You do not need to own a server or set anything up to chat and hang out.

**Bring your own pieces.** Connect a computer for Rift, your own file storage, or a server for calls. Storage can be an R2 or S3-compatible bucket, or something you host at home. These are separate choices; you do not need to host everything.

**Run the whole thing.** Host Portal for your own group or community with Docker Compose. Your chat server, storage and calls can live on infrastructure you control.

## Contributions beyond Portal

Building Portal has led to **three merged contributions to Amazon's open-source [MLS library](https://github.com/awslabs/mls-rs)**, which helps power Portal's encryption.

[View #369](https://github.com/awslabs/mls-rs/pull/369) · [View #380](https://github.com/awslabs/mls-rs/pull/380) · [View #381](https://github.com/awslabs/mls-rs/pull/381)

<details>
<summary><strong>For the technically curious</strong></summary>

Portal uses **MLS (Messaging Layer Security)** for groups, direct messages and stranger chats. Its Rust encryption engine runs in the browser through WebAssembly. The three upstream changes expose public protocol information the delivery server needs without providing message-decryption keys.

Realtime updates carry complete, versioned state. Reconnecting repairs missed updates, while ordered message history fills the gaps.

**Built with:** React, TypeScript, Python, FastAPI, Rust, PostgreSQL, Redis and LiveKit.

</details>

---

<sub>This is Portal's public profile. The application source is intended for release under AGPL-3.0.</sub>
