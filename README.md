# The Evolution of AI — Interactive Perspectives

A collection of self-contained, interactive HTML visualizations telling the story of modern AI from different perspectives. No build step, no dependencies — open [index.html](index.html) (or any page) directly in a browser.

## The perspectives

| # | Perspective | Page |
|---|-------------|------|
| 1 | **Infrastructure** — the cloud-native era that set the stage | [cloud-native-map.html](cloud-native-map.html) |
| 2 | **Architecture** — inside a transformer, step by step | [transformer-visualized.html](transformer-visualized.html) |
| 3 | **Training** — how an LLM becomes an LLM | [how-llm-becomes-llm_1.html](how-llm-becomes-llm_1.html) |
| 4 | **Alignment** — RLHF, learning from human feedback | [rlhf-visualized.html](rlhf-visualized.html) |
| 5 | **Applications** — the AI-native living blueprint | [ai-native-map_3.html](ai-native-map_3.html) |
| 6 | **Agents** — the supplied-core agent, learning without weights | [supplied-core-agent.html](supplied-core-agent.html) |

Also included: [supplied-core-agent-framework.md](supplied-core-agent-framework.md) — the written framework behind perspective 6.

## Running

Open `index.html` in any modern browser, or serve the folder:

```sh
python3 -m http.server
```

Each visualization is a single HTML file with inline CSS/JS.
