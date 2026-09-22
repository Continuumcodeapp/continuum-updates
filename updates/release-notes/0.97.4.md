# 0.97.4

Claude Opus 5.5, GPT-6 Sol and GPT-6 Luna are in every model picker and in Continuum inference.

## Claude Opus 5.5

- Opus 5.5 replaces Opus 5 everywhere you pick a Claude model: with your own Claude subscription, through OpenRouter with your own key, and in Continuum inference. The `opus` alias now selects it.
- It costs $4 in and $20 out per million tokens, less than Opus 5, with $0.20 cache reads, a 1M context window and 128K output. Thinking is always on; the effort setting (low to max) controls how hard it thinks.
- Opus 5 is retired from Continuum inference. It still runs on your own Claude subscription, and past Opus 5 usage keeps its price.

## GPT-6 Sol and GPT-6 Luna

- GPT-6 Sol ($2 in, $10 out per million tokens) and GPT-6 Luna ($0.10 in, $0.50 out) sit under GPT-6 Astra in the ChatGPT and Continuum pickers, in the same order as OpenAI's Codex. The GPT-5.6 models stay listed.
- Both have a 1.05M context window and 128K output. Requests over 272K input tokens are priced at OpenAI's long-request rate.
- With a ChatGPT account these models need Codex CLI 0.155.0 or later. Continuum's bundled and installed Codex is now 0.155.1.

## Usage and billing

- Usage and cost tracking price all three models on Mac, iPhone, web, Windows, Linux and Continuum inference, including Opus 5.5 used through OpenRouter.
