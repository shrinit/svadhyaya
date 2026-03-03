# Svadhyaya — स्वाध्याय

> A practice of turning inward.

An emotionally intelligent journaling app with on-device AI. Private, encrypted, and completely yours.

## Philosophy

Svadhyaya (from Sanskrit: sva "self" + adhyāya "study") is one of the five Niyamas in yoga philosophy — the dedicated practice of self-observation without judgment.

This app embodies three core principles:

- **Clarity**: See your patterns. Name what's beneath the noise.
- **Consistency**: Not streaks. A relationship — built slowly, held gently.
- **Safety**: A space that is always, unconditionally, yours.

## Features

### Core Experience

- **Felt-sense check-in**: Before writing, pause and notice how you're arriving
- **Reflective AI**: After each entry, receive one thoughtful question (never advice)
- **Learning over time**: The AI recognizes your patterns, emotional vocabulary, and rhythms
- **Burn entry**: Write something, breathe, delete it forever — some things are only for the moment
- **Safe mode**: Disable AI entirely when you need just a blank page
- **Monthly letters**: Once a month, the app distills your entries into a letter written to you, by you

### Privacy & Security

- **AES-256 encryption** at rest using your passphrase
- **On-device AI** via WebLLM (Phi-3 Mini model)
- **No cloud, no servers, no accounts**
- **Zero network requests** during journaling (verifiable in DevTools)
- **IndexedDB storage** with encrypted entries
- **Open source** — verify the privacy promises yourself

### Progressive Web App

- **Installable** on any device (iOS, Android, Desktop)
- **Works offline** after initial setup
- **No App Store** required — just add to home screen

## Tech Stack

- **Frontend**: React 18 + TypeScript + Vite
- **Styling**: Tailwind CSS + Custom CSS Variables
- **AI**: WebLLM (@mlc-ai/web-llm) with Phi-3 Mini model
- **Storage**: IndexedDB for encrypted journal entries
- **Encryption**: Web Crypto API (AES-256-GCM + PBKDF2)
- **Routing**: React Router v6
- **Icons**: Lucide React

## Design System

### Typography
- **Serif**: Cormorant Garamond (headings), Lora (body, italic)
- **Sans**: DM Sans (UI elements)

### Colors
- **Ink** (background): `#1c150d`
- **Parchment** (text): `#f5ede0`
- **Ember** (accent): `#c97d3a`
- **Sage** (secondary): `#7a8c72`

### Aesthetic
Warm, contemplative, with subtle texture. No purple/indigo tones. Every detail honors the practice of introspection.

## Development

```bash
npm install
npm run dev
```

Build for production:

```bash
npm run build
npm run preview
```

## Project Structure

```
src/
├── components/          # Reusable UI components
│   └── MoodCheck.tsx   # Mood check-in flow
├── context/            # React Context providers
│   └── AppContext.tsx  # Global app state
├── pages/              # Route components
│   ├── Splash.tsx      # Login/unlock screen
│   ├── Onboarding.tsx  # First-time setup flow
│   ├── Home.tsx        # Entry history and dashboard
│   ├── Write.tsx       # Writing interface
│   └── Reflection.tsx  # AI reflection view
├── utils/              # Core utilities
│   ├── ai.ts          # WebLLM integration
│   ├── database.ts    # IndexedDB wrapper
│   └── encryption.ts  # Web Crypto utilities
├── App.tsx            # Root component with routing
├── main.tsx           # Entry point + SW registration
└── index.css          # Global styles + design tokens
```

## AI Behavior

The AI adapts its reflections based on how long you've been journaling:

- **Days 1-7**: Warm but universal observations. Still learning.
- **Days 8-30**: Starting to reference patterns and recurring themes.
- **Day 30+**: Deep, specific observations that demonstrate genuine understanding.

The AI never:
- Gives advice
- Diagnoses
- Performs empathy

It only reflects — holding up a quiet mirror to what you've already written.

## Privacy Notes

- Your passphrase is never stored — it's the encryption key itself
- All entries are encrypted before being written to IndexedDB
- The AI model runs entirely in-browser via WebGPU/WASM
- No telemetry, analytics, or tracking of any kind
- Service worker only caches static assets for offline use

## Browser Requirements

- **Modern browsers** with IndexedDB and Web Crypto API support
- **WebGPU** support recommended for AI (falls back to WASM)


Tested on:
- Chrome/Edge 120+
- Safari 17+
- Firefox 120+

## License

MIT

---

*A quiet companion for the practice of turning inward.*
