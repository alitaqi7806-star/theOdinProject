

### Overview of Browsers on iOS

| Aspect                        | Details |
|-------------------------------|---------|
| **Dominant Rendering Engine** | Almost all browsers on iOS use **WebKit** (Apple's engine, the same as Safari). This is due to Apple's historical App Store policy. |
| **Main Browser**              | **Safari** (pre-installed, default browser) |
| **Popular Third-Party Browsers** | Chrome, Firefox, Edge, Brave, Opera, DuckDuckGo, Orion, etc. |
| **Rendering Engine for Third-Party Browsers** | Historically: All forced to use **WebKit** (Safari's engine) under the hood. They only provide their own UI/skins. |
| **Recent Change (EU Only)**   | Starting with iOS 17.4+ (2024), the EU's Digital Markets Act allows **alternative browser engines** (e.g., Chromium for Chrome, Gecko for Firefox). These are still limited and not widespread globally as of 2026. |
| **Global Reality (2026)**     | Outside the EU, and for most users even in the EU, nearly all iOS browsers still use **WebKit**. |

### Key Implications for Web Developers

| Implication                       | Explanation |
|-----------------------------------|-------------|
| **Feature Support**               | Test primarily in **Safari on iOS** — it represents the real behavior for most users. Third-party browsers often match Safari's capabilities closely. |
| **Bugs & Quirks**                 | Safari/WebKit-specific bugs (e.g., certain flexbox, position: sticky, or form behaviors) affect **all** iOS browsers. |
| **Vendor Prefixes**               | `-webkit-` prefixes are very common and often still needed for full compatibility on iOS. |
| **User-Agent Detection**          | Most iOS browsers report a Safari-like user agent. Detecting "Chrome on iOS" doesn't mean it uses Blink/Chromium. |
| **PWA & Installability**          | On iOS 16.4+, PWAs can be installed from the Share menu in Safari and many other browsers. Earlier versions required Safari. |
| **Performance & Capabilities**    | Limited by WebKit — some modern APIs (e.g., certain WebRTC features, advanced PWAs) may lag behind Android/Chrome. |

### Browser Engine Comparison on iOS

| Browser              | Rendering Engine (Typical) | Notes |
|----------------------|----------------------------|-------|
| **Safari**           | WebKit                     | Full control, best performance, most features. |
| **Chrome**           | WebKit (most cases) / Chromium (EU only, limited) | UI differences only in non-EU regions. |
| **Firefox**          | WebKit (most cases) / Gecko (EU only) | Same rendering as Safari for most users. |
| **Edge**             | WebKit                     | Microsoft UI on top of Apple's engine. |
| **Brave / Opera**    | WebKit                     | Privacy-focused skins over WebKit. |
| **Orion**            | WebKit                     | Lightweight browser with good extension support. |

### Important Gotchas for Developers

| Gotcha                            | Advice |
|-----------------------------------|--------|
| **"It works in Chrome on iOS"**   | Often means "it works in Safari/WebKit" — not true Chrome/Blink. |
| **Testing**                       | Always test on a real iOS device or Simulator with Safari. Use BrowserStack or similar for other browsers. |
| **Dark Mode & System Features**   | Use `@media (prefers-color-scheme: dark)` — works reliably across iOS browsers. |
| **Custom Properties & Modern CSS**| Excellent support (min/max/clamp, position: sticky, etc.) in current Safari/WebKit. |
| **Future Outlook**                | Alternative engines are slowly rolling out in the EU, but WebKit dominance is expected to continue globally for years. |

### Quick Recommendations
- **Primary testing browser** — Safari on the latest iOS.
- **For maximum compatibility** — Use feature detection instead of browser sniffing.
- **Progressive enhancement** — Provide fallbacks for any Safari/WebKit-specific quirks.
- **Modern features** — All the CSS we've covered (custom properties, `clamp()`, positioning, advanced selectors) have **excellent support** in current Safari on iOS.
