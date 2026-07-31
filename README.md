# AI Adoption Maturity Scorer

A Claude-powered assessment tool that scores AI adoption maturity across 8 dimensions and generates department-specific action plans in real time.

Built as a work sample demonstrating AI strategy thinking + LLM workflow integration.

## What it does

1. User selects their department (Product, Sales, Support, Marketing, Operations, Finance, Engineering, People & HR)
2. Answers 8 questions across 6 dimensions: Strategy, Enablement, Measurement, Governance, Workflows, Culture
3. Gets scored into one of four maturity levels: Reactive → Aware → Scaling → Optimising
4. Claude API generates a bespoke 3-action plan tailored to their department and exact score profile — streamed live

## Why the AI part matters

The recommendations are not hardcoded. Claude receives the department, every individual answer, and the dimension breakdown, then reasons across the full profile to generate advice calibrated to that team's specific situation.

A Support team scoring low on Governance gets different advice than a Product team with the same overall score. That specificity isn't possible with if/else logic.

## Tech

- Vanilla HTML/CSS/JS — no framework, no build step
- Anthropic Claude API (`claude-sonnet-4-6`) with streaming responses
- Runs entirely client-side

## Run locally

```bash
# Clone the repo
git clone https://github.com/ankitam44/adoption-maturity-scorer.git
cd adoption-maturity-scorer

# Serve locally (any static server works)
npx serve .
# or
python3 -m http.server 8080
```

Open `http://localhost:8080` in your browser.

> **Note:** The Claude API call is handled by the claude.ai environment when run there. For standalone use, you'll need to add your Anthropic API key to the fetch headers.

## Dimensions scored

| Dimension | What it measures |
|-----------|-----------------|
| Strategy | Ownership, roadmap clarity, leadership mandate |
| Enablement | Team confidence, training, prompt libraries |
| Measurement | KPIs, outcome tracking, impact frameworks |
| Governance | Data policies, approved tools, shadow AI risk |
| Workflows | AI integration depth in core processes |
| Culture | Leadership behaviour, organisational priority |

## Maturity levels

| Level | Score | Meaning |
|-------|-------|---------|
| Reactive | 8–14 | Scattered, uncoordinated, compliance risk |
| Aware | 15–22 | Intent exists, execution is fragmented |
| Scaling | 23–28 | Real momentum, quality decay risk |
| Optimising | 29–32 | Ahead of market, compounding advantage |
