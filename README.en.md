# Agent-Ops-Architecture

**One person, commanding a team of AI agents.**

This repository is the **blueprint** of the Agent Ops trio. It contains **documentation only — no code**.
It answers *why the system is shaped this way*, not *how to install it*.

> 📄 The detailed documents are written in Chinese (the primary audience).
> This page is a one-screen English summary.

---

## The trio

| Repository | Role | In one sentence |
|---|---|---|
| [`Agent-Ops-WeCom-Bridge`](https://github.com/Ly-FirmwareLab/Agent-Ops-WeCom-Bridge) | **Control plane** · human ⇄ agent | Turns WeCom into an agent cockpit: live progress, interrupt anytime, dangerous actions stopped first |
| [`Agent-Ops-Edge-Hub`](https://github.com/Ly-FirmwareLab/Agent-Ops-Edge-Hub) | **Data plane** · agent ⇄ physical world | An MQTT device bus that carries agent commands down to real hardware |
| **This repo** · `Agent-Ops-Architecture` | **Blueprint** · why | The manifesto, the panorama, and the conventions that tie the other two together |

They are not three features — they are **three faces of one architecture**.

---

## The idea in one page

**Two layers, one human in the middle.**

```
Layer 1 · Organization — a chat group
    human  ──@──▶  Agent A (workspace on a workstation)
           ──@──▶  Agent B (workspace on a Raspberry Pi)
           ──@──▶  Agent C (future: edge / cloud)

Layer 2 · Devices — MQTT / HTTP
    Agent  ──▶  touch panel · robot car · future actuators
```

**Five conventions**

1. **The entry point is chat.** Wherever you are, your workbench is there — no public IP, no dedicated server.
2. **`@` is routing, and the human is the only dispatcher.** Agents never talk to each other directly — by design, to prevent collisions and collusion.
3. **An agent = a workspace + a memory + a brain.** Reaching it through another window doesn't make it a different agent.
4. **Layer capabilities; don't rebuild wheels.** If upstream already has it, use upstream.
5. **Every action leaves a trace.** Who triggered it, what ran, what came back — always visible.

---

## Why this exists

Five mismatches motivated it:

1. **Model capability is locked behind the entry point.** You can run an agent in a terminal, but not from a train.
2. **Compute got cheap; orchestration didn't.** Three machines, three manual workflows.
3. **Multi-agent is a trend, but agent-to-agent chatter is a trap** — models reinforce each other's hallucinations, and humans can't see what passed between them.
4. **Devices get connected, but not *commanded*.** IoT platforms answer "what does the device look like", not "who decides, and who stops a bad decision".
5. **AI workflow tooling assumes you have a server.** Most individuals stall at step zero.

Read the full argument: [docs/why.md](docs/why.md) (Chinese).

---

## Documents

| Document | What it covers |
|---|---|
| [docs/why.md](docs/why.md) | Why this ecosystem exists — the era's pain points |
| [docs/manifesto.md](docs/manifesto.md) | The Collaboration Manifesto |
| [docs/architecture.md](docs/architecture.md) | Panorama: two layers, the star topology, the role table, known limits |
| [docs/conventions.md](docs/conventions.md) | The five conventions, plus the interaction baseline for a single task |

---

## License

Documentation is licensed under **[CC BY 4.0](LICENSE)** — reuse, quote and adapt freely, **with attribution**.

Attribution: **Agent-Ops-Architecture · Ly-FirmwareLab** (with a link back to this repository).

---

> For everyone brave enough to rebuild their own workflow in the age of AI.