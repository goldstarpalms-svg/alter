# 02 — Architecture

ALTER is a single-page progressive web app. Everything runs in the browser; nothing requires a server.

## The four parts

| Layer | What it is | Where |
|---|---|---|
| **MIND** | The reasoning engine. Offline demo brain by default; swap in a free Gemini key for real world knowledge. | `app/index.html` (`geminiReply` / `demoReply`) |
| **MEMORY** | Persistent on-device facts about you. | `localStorage` (`alter.memory.v1`) |
| **FACE** | The avatar that blinks, listens and talks. | DOM + CSS (`#avatar`) |
| **PLANE** | The control plane: overview, tasks, memory, knowledge, settings. | `app/index.html` (right panel) |

## Data flow

1. You type or speak a message.
2. The app checks your **memory** for context and the applied **mind** (Gemini if a key is saved, otherwise the offline demo brain).
3. ALTER replies in the chat, animates the avatar, and optionally speaks the reply.
4. Every action is written to the **activity log** (full audit, always visible).
5. A `remember …` message is extracted and stored to memory.

## Sovereignty

- Memory lives only in **this browser's** `localStorage`. Nothing is uploaded.
- One-click **JSON export** and one-click **wipe**.
- The Gemini key, if added, never leaves the device.

## Offline app shell

A service worker (`app/sw.js`) caches the shell so ALTER launches even with no network. `app/index.html` is self-contained — the entire app, no build step.
