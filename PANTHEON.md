# AutoAgent — Pantheon Integration
**Forked for the Pantheon | 2026-05-31**
**Source:** https://github.com/HKUDS/AutoAgent
**Paper:** https://arxiv.org/abs/2502.05957
**Status:** FORKED ✅ | Deploy Target: The Nexus (primary) / Termux (lightweight)

---

## Pantheon Role: The Forge — Prime Manufacturing Layer

AutoAgent is the automated agent factory for the Pantheon. Instead of writing
code for each new Prime, describe the agent in natural language → AutoAgent
builds it, tools and all, autonomously.

> "Build a ScoutPrime agent that scrapes LEEPA, pulls Zillow comps,
>  calculates spread, and sends alerts to Telegram."
→ AutoAgent builds it. No code required.

This is how the Pantheon scales from 5 Primes to 25.

---

## Pantheon Prime Build Queue (via AutoAgent)

| Prime | Natural Language Prompt | Status |
|---|---|---|
| ScoutPrime v5 | "Scrape LEEPA + PropertyOnion, calc spread vs Zillow, Telegram alert" | QUEUED |
| ContentPrime v2 | "Find trending niche, write script, generate video, post to YouTube/TikTok" | QUEUED |
| ArbitrageScout | "Monitor Polymarket + Kalshi for spread, execute hedge, report profit" | QUEUED |
| SentinelPrime | "Watch GitHub Actions + Render status, alert on failures via Telegram" | QUEUED |
| PropPilot3D | "Take listing photo, generate TRELLIS.2 3D render, attach to PDF report" | QUEUED (needs Nexus) |

---

## Quick Start (Termux — lightweight, no Docker)

```bash
git clone https://github.com/kevinleestites2-dev/AutoAgent
cd AutoAgent
pip install -e .

# Point to Ollama bridge (free, local LLM)
export API_BASE_URL="https://naval-measures-mat-modern.trycloudflare.com"
export COMPLETION_MODEL="ollama/llama3"

# Deep Research mode (lightest)
auto deep-research

# Full agent builder
auto main
```

## Quick Start (Nexus — full power, Docker)

```bash
git clone https://github.com/kevinleestites2-dev/AutoAgent
cd AutoAgent
pip install -e .

# With Ollama running locally on Nexus
export API_BASE_URL="http://localhost:11434"
export COMPLETION_MODEL="ollama/llama3"
auto main
```

---

## LLM Config for Pantheon

AutoAgent uses LiteLLM under the hood — supports any provider.

**Free (Ollama, local):**
```bash
export API_BASE_URL="[Ollama tunnel from TOOLS.md]"
export COMPLETION_MODEL="ollama/llama3"
```

**Free (OpenRouter — Forgemaster key in TOOLS.md):**
```bash
export OPENROUTER_API_KEY="[key from TOOLS.md]"
export COMPLETION_MODEL="openrouter/meta-llama/llama-3-70b-instruct"
```

---

## Key Capabilities

- **Natural Language Agent Building** — describe it, AutoAgent codes it
- **Self-Play Improvement** — agents iteratively rewrite their own tools
- **Deep Research Mode** — rivals OpenAI Deep Research at $0/month
- **Multi-Agent Workflows** — describe a pipeline, get a deployed system
- **GAIA Benchmark** — academic-grade performance validation
- **Any LLM** — Ollama, OpenRouter, Anthropic, OpenAI, Gemini, Deepseek

---

## Integration Queue
- [ ] Wire Ollama bridge as default LLM backend
- [ ] Test Deep Research mode on ScoutPrime property analysis
- [ ] Build ScoutPrime v5 agent via natural language prompt
- [ ] Build ArbitrageScout via natural language prompt
- [ ] Connect agent outputs to Telegram reporting (existing bot token)
- [ ] Deploy full instance on The Nexus with Docker
