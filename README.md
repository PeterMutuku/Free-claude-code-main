# Free-claude-code-main
A bright single-page guide built from claude-code.txt (77 sections). Open index.html or run python3 -m http.server 8080.
Design system (current)
Palette: Paper brutal / editorial light — cream page #f6f4ef, white cards, charcoal text #111, orange #ff4d00 primary CTA/accent, blue #0057ff links/secondary. Chapter colors are left-border stripes only. No pink–purple–cyan rainbow.
Type: Bricolage Grotesque 600–700 + Plus Jakarta Sans + JetBrains Mono. Hero title is solid dark on a white/cream hero — not gradient, not Syne.
Theme: Bright/light only (no dark mode toggle). Previously used Terminal night charcoal — removed per product requirement.
Performance
No Lenis or GSAP. Intersection Observer for reveals + nav spy; one rAF-throttled scroll handler. See script.js header comment.
Stack: vanilla HTML/CSS/JS + Lucide (CDN).
Responsive layout
Breakpoints in styles.css:
Width	Behavior
> 1024px	Fixed sidebar, main offset by --nav-width
≤ 1024px	Drawer nav, mobile header, floating TTS/back-to-top adjusted
≤ 768px	Shorter hero, loop steps stack vertically, 2-column concept grid
≤ 480px	Single-column grids, comparison table becomes cards, full-width CTA
≤ 360px	Tighter padding, compact TTS labels
Test locally: open the site, use Chrome DevTools device toolbar (iPhone SE 320px, iPhone 14 390px, iPad 768px), or resize the browser window. Rotate once to confirm the nav drawer closes on desktop width.
Listen (text-to-speech)
Free Web Speech API in the browser — no API keys, works on GitHub Pages. Use the bar at the bottom:
•	Listen here — reads main article text from the section you are viewing through the end (not the sidebar TOC)
•	Listen all — reads from section 1 through 77
•	Pause / Resume — stops speech and keeps your place; resume continues the same chunk (Chrome does not reliably support speechSynthesis.pause(), so playback uses cancel + queue index)
•	Stop — cancels playback and resets the queue
•	Follow-along highlight — the spoken word is highlighted in the section body (Chrome/Safari via onboundary; Firefox uses timed word steps or paragraph highlight)
Voice quality depends on your OS/browser (Chrome or Edge recommended for English).
Learn-Claude-Code
