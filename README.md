# Minimum-cost CI matrix

필수 환경·기능의 검증 범위를 전부 덮는 최소 비용 CI 작업 조합을 찾는다.

A focused executable resource for AI-assisted structured work. **Zero runtime dependencies, no API key, Node.js 22+.**

[Live workspace](https://proofnova.github.io/ci-matrix-cover/) · [한국어 리소스 모음](https://proofnova.github.io/) · [Task contract](resource.json) · [Prior art](RESEARCH.md)

```sh
git clone https://github.com/proofnova/ci-matrix-cover.git
cd ci-matrix-cover
npm test
node cli.mjs example.json
```

## What it does

Exact bitmask dynamic programming rather than greedy cheapest-first selection.

Every declared requirement must be covered; an over-budget optimum is not a feasible plan.

## Connect a model

Import `execute` from `./run.mjs`. Expose this declared tool to your model, validate its tool name/input contract, execute it, and retain the returned JSON and input digest. Calculations and constraint checks are performed by the resource. No paid model or new agent framework is required.

[SKILL.md](SKILL.md) contains the workflow, interpretation and recovery procedure. [example.json](example.json) is a complete input; [cases.json](cases.json) contains worked and held-out synthetic checks. The website executes the same code locally in a bounded Worker. It has no model or external data upload.

## Recovery and limits

Add coverage for missing requirements or raise the explicit budget; never drop a required environment.

Underlying algorithms and task outcomes already exist in the alternatives. An existing tool configured for this exact task may remove the need for a separate project. Small synthetic tests cannot establish broad expertise or external demand. See [RESEARCH.md](RESEARCH.md). A plan/audit is not an external action or proof of actual user benefit.

## Contribute

Open an issue with a synthetic/redacted failing JSON input, expected result and Node version. Add a regression test and run `npm test`. Never include credentials or real private records in public examples.

MIT · Proofnova · 2026
