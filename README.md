# Spam filtering

> 🌍 [简体中文](README.zh-CN.md) · [繁體中文](README.zh-TW.md) · [English](README.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Deutsch](README.de.md) · [Français](README.fr.md) · [Español](README.es.md) · [Português](README.pt.md) · [Русский](README.ru.md)

Keep your browsing clean. **Spam filtering** silently removes spam, popups, banners, trackers and other junk content from the pages you visit — everything runs locally and privately on your device.

## Highlights

- Blocks spam and junk content: popups, banners, trackers, analytics scripts
- Your own plain-text rules — import, edit and export anytime
- Whitelist trusted sites with one click
- Blocking statistics (today / total)
- 10 languages supported
- 100% local and private — no account, no cloud, no data collection
- Works at system level — no browser extension required

## Requirements

- Windows 10 / 11

## Getting started

1. Download the latest installer from the Releases page.
2. Install and launch the app.
3. Turn on **Take over system proxy** in Settings.
4. Browse — junk is filtered automatically.

## Editing rules

Rules are stored in plain text, one rule per line. Add rules in the app (**Rules** page) or import a rule file.

### Rule formats

| Example | Meaning |
| --- | --- |
| `\|\|example.com^` | Block a domain and all its subdomains |
| `\|\|example.com/path/page^` | Block a specific address (domain + path) |
| `example.com` | Block any address containing this text |
| `@@\|\|good.example.com^` | Exception — always allow this domain |
| `0.0.0.0 ad.example.com` | Hosts-format entry |
| `! comment` / `# comment` | Comments — lines starting with these are ignored |

### Tips

- `||` anchors the rule to the start of a domain; `^` means "end of domain or path" (a separator).
- Start simple: `||domain^` covers most cases. Add path rules only when needed, e.g. `||www.example.com/ads/banner^`.
- After saving a rule, check the blocking statistics to confirm it works.

### About HTTPS

By default, HTTPS requests are matched by **domain name only** (the full address is encrypted and cannot be seen). To match by **full address including path**, open Settings → turn on **HTTPS decryption (MITM)** → install the root certificate when prompted (one time only), then restart your browser. After that, path rules like `||www.example.com/ads/banner^` take effect on HTTPS sites too.

## How it works (brief)

- The app runs a local proxy and can take over the system proxy, so browser traffic flows through it.
- Every request is checked against your rules: matched requests are blocked, everything else is forwarded untouched.
- All filtering happens on your device — nothing is uploaded anywhere.

## Troubleshooting

**Cannot access the internet?** The most likely cause: the app was closed unexpectedly and left the system proxy pointing to a dead port.

- **Solution 1 — restart the app.** It automatically detects and cleans up leftover proxy settings on startup.
- **Solution 2 — turn the proxy off manually.** Open Windows Settings → Network & Internet → Proxy → turn off "Use a proxy server".
- Normally, exiting the app (tray icon → Exit) restores your proxy automatically. Leftovers only happen after abnormal exits (crash, force-kill, power loss).

## Privacy

Spam filtering is a local tool. All filtering happens on your device — your browsing data never leaves your computer.

## Support this project

If Spam filtering helps you, consider supporting future development:

![Donate](donate.jpg)

## License

All rights reserved. This software is **not open source**. Redistribution and modification are not permitted without explicit written permission.
