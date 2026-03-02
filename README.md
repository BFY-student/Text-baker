# 🍞 Text Baker

A single-file, AI-powered language polishing and humanization tool. Paste your text, pick a style, and let an LLM polish it with visible revision marks — or humanize AI-generated text to sound more natural.

## ✨ Features

### Core Functionality
- **Three processing modes**:
  - 🔧 **Polish Text** — Improve grammar, clarity, and style with visible revision marks
  - 🎭 **Humanize Text** — Transform AI-generated text into natural human writing
  - 🔥 **Polish & Humanize** — Combine both for maximum quality

- **Multiple AI providers** — OpenAI-compatible APIs, Google Gemini, and Local/Ollama
- **Revision marks** — additions in **bold green**, deletions in ~~strikethrough red~~, full rephrases in ***bold-italic orange***
- **Tunable output** — choose language, register (Formal → Casual → Technical), and polish intensity (grammar-only → full rephrase)
- **Academic writing optimized** — automatically avoids first-person pronouns (we, our, us) in formal/academic styles

### User Experience
- **Persistent settings** — API configuration saved to localStorage, survives page refreshes
- **Copy clean text** — one click to copy the final version without markup
- **History** — every operation saved; reload past results from history modal
- **API verification** — test your API connection before processing
- **Zero dependencies** — pure HTML + CSS + JS in a single file. No build tools, no CDN, no framework
- **Dark mode** UI, fully responsive on desktop and mobile

## 🚀 Quick Start

1. **Open the app**: Simply open `text-baker.html` in any modern browser
2. **Configure API** (one-time setup):
   - Click to expand **API Provider Configuration**
   - Select your provider (OpenAI, Gemini, or Local/Ollama)
   - Enter API key and model name
   - Click **Verify API Connection** to test
   - Settings are automatically saved!
3. **Process text**:
   - Set language, style (register), and intensity
   - Paste text in the left panel
   - Click **Polish**, **Humanize**, or **Polish & Humanize**
   - View results with revision marks on the right
   - Toggle between marked and plain views
   - Copy clean text with one click

## 🔌 Supported Providers

| Provider | Base URL | Model Example | API Key |
|----------|----------|---------------|---------|
| **OpenAI** | `https://api.openai.com/v1` | `gpt-4o` | Required |
| **Google Gemini** | `https://generativelanguage.googleapis.com/v1beta` | `gemini-2.5-flash` | Required |
| **Local / Ollama** | `http://localhost:11434/v1` | `qwen3-vl:30b`, `llama3` | Auto-filled |

### Using Ollama (Local)
1. Install and run [Ollama](https://ollama.ai)
2. Pull a model: `ollama pull qwen3-vl:30b`
3. Select "Local / Ollama" provider in Text Baker
4. Base URL auto-fills to `http://localhost:11434/v1`
5. Enter your model name (e.g., `qwen3-vl:30b`)
6. Start processing!

> **Note on CORS:** Browsers block requests from `file://` pages to localhost. If you open `text-baker.html` directly, Ollama calls will fail. Fix with one of:
> - Restart Ollama with: `OLLAMA_ORIGINS=* ollama serve`
> - Or serve the file locally: `python3 -m http.server 8000` then open `http://localhost:8000/text-baker.html`

## 🌡️ Adaptive Temperature

Temperature is set automatically per task for optimal results:

| Mode | Temperature | Rationale |
|------|------------|-----------|
| **Polish** | 0.2 | Predictable, faithful corrections |
| **Humanize** | 0.6 | Creative freedom for natural phrasing |
| **Polish & Humanize** | 0.2 → 0.6 | Polish first, then humanize |

## 🎨 Style & Register Options

- **Formal** → Semi-formal → **Neutral** → Semi-casual → **Casual** → **Technical**
- Automatically adapts writing conventions:
  - Academic styles: avoid first-person (we/our/us), use passive voice
  - Business style: action-oriented, active voice
  - Informal: conversational, permits contractions
  - Technical: precise terminology, consistent vocabulary

## 📖 Polish Intensity Levels

0. **Grammar only** — Fix errors, preserve style
1. **Light touch** — Minimal improvements
2. **Moderate** — Balance preservation with enhancement
3. **Heavy rewrite** — Significant quality improvements
4. **Full rephrase** — Complete optimization for clarity

## 🎭 Humanize Mode

Transforms AI-generated text to read naturally using:
- Variable sentence length (high burstiness)
- Reduced dependency distance
- Unpacked nominalizations
- Elimination of AI markers ("delve into", "navigate", "tapestry of")
- Genre-appropriate epistemic markers
- Controlled imperfection for authenticity
- Semantic fidelity preserved

## 💾 Data & Privacy

- **All processing happens through your chosen API** — no third-party servers
- **History stored locally** — uses browser localStorage only
- **API keys stored locally** — never transmitted except to your configured endpoint
- **No tracking, no analytics, no external requests**

## 🛠️ Technical Details

- Pure vanilla JavaScript, no frameworks
- Single HTML file (< 50KB)
- Works offline (after initial load) with local Ollama
- Compatible with all modern browsers
- Mobile-friendly responsive design

## 📝 License

MIT — Free to use, modify, and distribute

---

**Made with ❤️ for writers, researchers, and anyone who works with text**
