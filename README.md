```
     ██╗███╗   ███╗   jmjm1558@github
     ██║████╗ ████║   ─────────────────────────────────────────────
     ██║██╔████╔██║   role      AI trainer · independent contractor
██   ██║██║╚██╔╝██║   location  Colombia · remote (UTC-5)
╚█████╔╝██║ ╚═╝ ██║   focus     LLM agents that reach production
 ╚════╝ ╚═╝     ╚═╝   langs     Python · TypeScript · some Java
                      stack     FastAPI · Next.js · Docker · Gradio
                      models    Claude · DeepSeek · Whisper · Qwen
                      machine   Ubuntu 24.04 · RTX 5060 · 30GB RAM
                      server    Hetzner VPS · Tailscale · systemd
                      editor    VS Code + Claude Code · zsh · tmux
                      studying  numerical methods · modern physics
                      site      juanjimenez.ai

                      ██ ██ ██ ██ ██ ██ ██ ██
                      ██ ██ ██ ██ ██ ██ ██ ██
```

I build systems where the model does the work, not the demo. Most of what I
ship runs on my own machine or a small VPS: local inference, agents wired to
real tooling, and the unglamorous plumbing that keeps them alive at 3am.

```diff
+ available for AI training & evaluation work (remote, USD)
+ available for short ML / automation builds
- not taking full-time roles right now
```

### What I'm building

**[agent-island](https://github.com/jmjm1558/agent-island)** · GNOME Shell extension

A Dynamic Island for your desktop. A pill replaces the clock in the top bar
and shows every AI coding agent session running on the machine in real time,
one dot each, colored by state: green means working, amber means *it is
waiting on you*, gray means done. Click a row and it focuses that session's
terminal pane. The card also mirrors MPRIS playback and the notification
tray, so the notch becomes a hub instead of one more widget.

No daemon, no polling, no custom socket. It reads what the agents already
write to disk. Disabling the extension puts your clock back exactly where it
was.

`GJS · GNOME Shell · tmux · MPRIS`

**[transcriptor](https://github.com/jmjm1558/transcriptor)** · local speech pipeline

Drop in a recording or paste a link, get a Markdown transcript with
timestamps and an auto-written meeting summary. Whisper large-v3 runs on the
local GPU, so the audio never leaves the machine and there is no per-minute
bill.

The interesting part is the live-meeting mode: it records the mic and the
speaker monitor as two separate tracks, then interleaves them by word-level
timestamps into a labeled dialogue. A two-pass anti-echo filter throws away
what the mic picked up from the speakers, so you get "me" and "them" instead
of one soup of overlapping text.

`Python · faster-whisper · CUDA · Gradio · yt-dlp · PipeWire`

**[jimenez-site](https://github.com/jmjm1558/jimenez-site)** · personal site

Services, projects and contact in three languages. Locale routing (es/en/pt)
runs through middleware with next-intl, so every page exists once and the
copy lives in message catalogs. Adding a language is one JSON file and one
line of config, not a new set of pages.

`TypeScript · Next.js 16 · next-intl · Tailwind 4 · Framer Motion`

### Not public (client work)

- **Tender-screening agent.** Ingests Colombian public procurement notices,
  scores each one against a company's actual capabilities and emits a GO /
  NO-GO verdict with the risks spelled out, so a small firm stops reading
  hundreds of tenders it was never going to win.
- **WhatsApp sales agent + CRM.** Qualifies inbound leads in conversation and
  hands off to a human at the right moment, with the history already written
  to the CRM.

### Bugs that cost me a weekend

I keep a lessons file. Every entry is a day I am not getting back:

- A GPU dashboard that polls `nvidia-smi` keeps the dGPU out of runtime
  suspend permanently. It burned battery to measure how much battery was
  being burned. Reading sysfs instead does not wake the card.
- `openwakeword`'s `reset()` only clears the prediction buffer. The ~1.3s
  feature window keeps its audio, so the assistant heard its own wake word
  from ten seconds ago and woke itself up, forever.
- My university's wifi sends a TLS reset to `huggingface.co` based on SNI
  alone. The code was fine. The Whisper weights now come from ModelScope.
- `secrets.token_urlsafe()` happily emits `+`, `/` and `=`. Put one in a
  `redis://:pass@host:port` URL and the parser tries to cast half your
  password to a port number.
- Models wrap JSON in a markdown code fence no matter how firmly the prompt
  forbids it. Strip the fence before `json.loads`. Every time. The smaller the
  model, the more certain it is that you wanted the pretty version.
- SECOP II has no public API and its documents sit behind a reCAPTCHA. The
  correct engineering answer was that this part does not get automated.

### Reach me

[juanjimenez.ai](https://juanjimenez.ai) · [jmjm1558@gmail.com](mailto:jmjm1558@gmail.com)
