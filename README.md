# AI Adoption Maturity Scorer

A department-specific AI adoption assessment tool powered by the Claude API.

**[→ Live demo](https://adoption-maturity-scorer.vercel.app)**

## What it does

8 questions across 6 dimensions (Strategy, Enablement, Measurement, Governance, Workflows, Culture). Select your department, answer the questions, and get a maturity level + three opinionated, department-specific action recommendations generated live by Claude.

The scoring is deterministic. The action plan is generative — Claude reasons across your full answer profile and department context to produce advice that hardcoded logic can't replicate.

## Architecture

```
Browser → Vercel serverless function (/api/score) → Anthropic API
```

- API key stored as a Vercel environment variable — never exposed client-side
- Streaming response via SSE for live token output
- No framework — vanilla HTML/CSS/JS

## Stack

- Vanilla HTML/CSS/JS
- Claude API (`claude-sonnet-4-6`) with streaming
- Vercel serverless functions (Node.js)

## Run locally

```bash
npm i -g vercel
vercel dev
```

Set `ANTHROPIC_API_KEY` in a `.env.local` file:

```
ANTHROPIC_API_KEY=sk-ant-...
```

## Deploy

```bash
vercel --prod
```

Add `ANTHROPIC_API_KEY` in Vercel project settings → Environment Variables.

---

Built by [Ankita Menon](https://linkedin.com/in/ankitabmenon)
