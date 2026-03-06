# 🔐 Password Analyzer

A fully client-side password strength analyzer and breach checker. No backend, no tracking, no data ever leaves your browser.

## Live Demo
> Open `index.html` directly in any browser — no build step required.

## Features

- **Real-time entropy scoring** — measures true randomness using character pool size, unique character variety, and repetition penalties
- **Crack time estimation** — translates entropy into time-to-crack at 10 billion guesses/sec (modern GPU rate)
- **Composition checks** — length, uppercase, lowercase, numbers, symbols, common pattern detection, and repeat character analysis
- **HaveIBeenPwned integration** — k-anonymity breach lookup; only a 5-character SHA-1 hash prefix is ever transmitted
- **Personalized recommendations** — dynamic suggestions based on which checks your password fails

## Privacy

All scoring and analysis runs entirely in the browser via the Web Crypto API.

The only network request is the optional breach check, which works as follows:
1. Your password is SHA-1 hashed locally
2. Only the **first 5 characters** of the hash are sent to the [HIBP API](https://haveibeenpwned.com/API/v3#SearchingPwnedPasswordsByRange)
3. The returned suffix list is matched client-side
4. Your actual password is **never transmitted**

## Usage
```bash
git clone https://github.com/rick1sanchez/password-analyzer.git
cd password-analyzer
open index.html
```

No dependencies. No install. No build step.

## Tech Stack

- Vanilla HTML, CSS, JavaScript
- [Web Crypto API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Crypto_API) for SHA-1 hashing
- [HaveIBeenPwned Passwords API](https://haveibeenpwned.com/API/v3#SearchingPwnedPasswordsByRange) for breach detection
- [Google Fonts](https://fonts.google.com) — Playfair Display, DM Mono, DM Sans

## License

MIT
