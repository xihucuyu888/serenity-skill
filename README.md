# Serenity Skills

Codex skills for translating market information into testable investment research frameworks.

## Skills

- `serenity-alpha`: translates market news into alpha hypotheses using a `news -> demand -> financial statements -> small-cap elasticity -> validation path` framework.
- `bayesian-intrinsic-growth-valuation`: estimates a company's intrinsic 3-5 year growth rate with Bayesian hypothesis updates, then compares it with market-implied growth and FOMO.

## 直接使用托管版

如果你觉得本地安装、配置 Codex skill 或维护环境不方便，也可以订阅 [@iamai_omni](https://x.com/iamai_omni/creator-subscriptions/subscribe)，然后访问 [app.k2ai.dev](https://app.k2ai.dev) 直接使用托管版。订阅版不需要你自己搭建，并且会附赠许多其他功能，适合想快速上手、持续使用 Serenity 体系的用户。也可以扫码直接打开订阅页：

<img src="docs/assets/iamai-omni-subscribe-qr.png" alt="Subscribe to @iamai_omni QR code" width="220">

## Repository Layout

```text
skills/
├── serenity-alpha/
│   ├── SKILL.md
│   ├── agents/openai.yaml
│   └── references/original-framework.md
└── bayesian-intrinsic-growth-valuation/
    ├── SKILL.md
    ├── agents/openai.yaml
    └── references/original-framework.md
```

Each subdirectory under `skills/` is an independent Codex skill. Codex discovers a skill from its `SKILL.md`; files under `references/` are supporting material loaded only when needed.

## Install

Copy all skills into your Codex skills folder:

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R skills/* "${CODEX_HOME:-$HOME/.codex}/skills/"
```

Or install only one skill:

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R skills/serenity-alpha "${CODEX_HOME:-$HOME/.codex}/skills/"
cp -R skills/bayesian-intrinsic-growth-valuation "${CODEX_HOME:-$HOME/.codex}/skills/"
```

Then invoke `$serenity-alpha` for news-to-alpha analysis, or `$bayesian-intrinsic-growth-valuation` for Bayesian intrinsic-growth valuation. If a newly copied skill does not appear, restart Codex.

## What They Do

`serenity-alpha`:

- Separates narrative news from already-observable demand changes.
- Maps demand into revenue, margin, cash-flow, and balance-sheet impact.
- Searches for small, pure, potentially misclassified beneficiaries.
- Builds 1-4 quarter verification chains and falsification points.
- Frames position posture conditionally as research, not personalized investment advice.

`bayesian-intrinsic-growth-valuation`:

- Converts fundamentals, industry cycle, TAM, valuation, and new information into H0-H5 growth-hypothesis probabilities.
- Updates 3-5 year revenue CAGR assumptions with Bayesian reasoning instead of surface bullish/bearish labels.
- Separates intrinsic growth updates from FOMO, narrative heat, and valuation multiple expansion.
- Compares weighted intrinsic growth with market-implied growth.
- Classifies valuation as undervalued, fair, expensive but tradable, or bubble-like.

## License

MIT
