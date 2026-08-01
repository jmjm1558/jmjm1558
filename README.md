```
     ██╗███╗   ███╗   jmjm1558@github
     ██║████╗ ████║   ─────────────────────────────────────────────
     ██║██╔████╔██║   role      AI / automation engineer
██   ██║██║╚██╔╝██║   location  Colombia · remote (UTC-5)
╚█████╔╝██║ ╚═╝ ██║   focus     LLM agents that reach production
 ╚════╝ ╚═╝     ╚═╝   stack     Python · FastAPI · Next.js · Docker
                      infra     Ubuntu · Hetzner VPS · CUDA
                      now       local voice assistant · GNOME ext
                      open to   remote ML / AI contract work
                      site      juanjimenez.ai
```

I build systems where the model does the work, not the demo. Most of what I
ship runs on my own machine or a small VPS: local inference, agents wired to
real tooling, and the boring plumbing that keeps them alive.

### What I'm building

**[agent-island](https://github.com/jmjm1558/agent-island)** — A Dynamic
Island for GNOME Shell. A pill in the top bar shows every AI coding agent
session running on the machine in real time, color-coded by state; click a
row and it focuses that session's terminal pane. No daemon, no polling, no
custom socket.
`GJS · GNOME Shell · tmux`

**[transcriptor](https://github.com/jmjm1558/transcriptor)** — Drop in a
recording or paste a link, get a Markdown transcript with timestamps plus an
auto-written meeting summary. Whisper large-v3 runs on the local GPU, so the
audio never leaves the machine. Also records live meetings on two tracks and
labels who said what.
`Python · faster-whisper · CUDA · Gradio · yt-dlp`

**[jimenez-site](https://github.com/jmjm1558/jimenez-site)** — My site.
App Router, three locales (es/en/pt) routed through middleware.
`TypeScript · Next.js 16 · next-intl · Tailwind`

### Not public (client work)

- **Tender-screening agent** — ingests Colombian public procurement notices,
  scores each against a company's actual capabilities and emits a GO/NO-GO
  verdict with the risks spelled out.
- **WhatsApp sales agent + CRM** — qualifies inbound leads on WhatsApp and
  hands off to a human at the right moment.

### Reach me

[juanjimenez.ai](https://juanjimenez.ai) · [jmjm1558@gmail.com](mailto:jmjm1558@gmail.com)
