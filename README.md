# Text Baker

A single-file, AI-powered language polishing tool. Paste your text, pick a style, and let an LLM polish it sentence by sentence with visible revision marks.

## Features

- **Multiple AI providers** — OpenAI-compatible (including proxies), Google Gemini, and Local/Ollama.
- **Revision marks** — additions in **bold green**, deletions in ~~strikethrough red~~, full rephrases in ***bold-italic orange***.
- **Tunable output** — choose language, register (formal → casual), and polish intensity (grammar-only → full rephrase).
- **Copy clean text** — one click to copy the final version with all marks and deleted fragments removed.
- **History** — every polish operation is saved to localStorage; reload past results from a popup.
- **Zero dependencies** — pure HTML + CSS + JS in a single file. No build tools, no CDN, no framework.
- **Dark mode** UI, responsive on desktop and mobile.

## Usage

1. Open `text-baker.html` in any modern browser.
2. Expand **API Provider Configuration**, enter your provider base URL, API key, and model name.
3. Set language, register, and intensity.
4. Paste text on the left, click **Polish Text**, read results on the right.

## Supported Providers

| Provider | Base URL example | Auth |
|---|---|---|
| OpenAI / proxy | `https://api.openai.com/v1` | Bearer token |
| Google Gemini | `https://generativelanguage.googleapis.com/v1beta` | API key in URL |
| Local / Ollama | `http://localhost:11434` | Optional |

## License

MIT
