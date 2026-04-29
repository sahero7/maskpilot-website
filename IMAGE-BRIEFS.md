# Image Briefs für Website (paste-ready Prompts)

**Ziel:** Bilder per Midjourney V7 / Open-Generative-AI / Flux generieren und in Website einsetzen
**Format:** JPG/PNG, optimiert <200KB

---

## 1. HERO IMAGE — index.html (Pre-Sales Advertorial)

**Position:** Direkt unter Sub-Headline, vor Article-Text
**Größe:** 1920×1080 (16:9)
**Datei:** `/website/assets/hero-dashboard.jpg`

### Midjourney-Prompt:
```
Realistic screenshot of YouTube Studio Analytics Dashboard, dark mode interface, showing monthly earnings of €8,430.17, large area chart with steady growth curve over 6 months, multiple metric cards (Subscribers: 287K, Watch time: 1.2M hrs, Revenue: €8,430), modern UI with dark blue (#1e3a5f) accents, minimalist design, photorealistic, ultra-detailed UI elements, on a white desk surface, soft natural light from left, MacBook Pro frame partially visible at bottom edge --ar 16:9 --v 6.1 --s 250
```

### Alternative (Open-Generative-AI):
```
Photo of laptop screen displaying YouTube Studio dashboard, monthly revenue €8,430.17 prominently visible, clean modern interface, soft window light, shallow depth of field, professional product photography style, neutral color palette
```

---

## 2. OG IMAGE (Social Share)

**Größe:** 1200×630 (Open Graph standard)
**Datei:** `/website/assets/og-image.jpg`

### Midjourney-Prompt:
```
Modern minimal social share image, dark navy background (#1e3a5f), centered text "MaskPilot Pro" in bold white sans-serif, subtitle "€8.430/Monat ohne dein Gesicht" in gold (#d4a849), small YouTube play icon in corner, premium B2B aesthetic, generous whitespace --ar 1200:630 --v 6.1
```

### Tool-Alternative:
- Canva Template: "Social Share Tech B2B"
- Custom: Figma 1200×630 mit Brand-Farben

---

## 3. PERSONA AVATAR — Marc (Author Section)

**Position:** Author-Block unter Headline
**Größe:** 80×80 (Round)
**Datei:** `/website/assets/avatar-michael.jpg`

### Open-Generative-AI-Prompt (Soul ID):
```
Professional headshot of European man, late 30s, short brown hair, light beard, navy blue shirt, neutral background, warm natural lighting, slight smile, looking directly at camera, professional photography, sharp focus, premium portrait style
```

---

## 4. PROOF SECTION — 3 Channel Dashboards

**Position:** Mid-article, Proof-Block
**Größe:** 3× 600×400
**Dateien:**
- `/website/assets/proof-marc.jpg` (€8.430)
- `/website/assets/proof-sabine.jpg` (€4.207)
- `/website/assets/proof-tom.jpg` (€12.890)

### Midjourney-Prompt-Template:
```
Realistic YouTube Studio dashboard screenshot, [REVENUE] in gold accent, monthly view, clean interface, [CHANNEL_NAME] in header, subscribers count visible, growth chart, photorealistic UI --ar 3:2 --v 6.1
```

Variable je Channel:
- Marc: REVENUE=€8.430, CHANNEL_NAME="Mystery Vault DE", SUBS=287K
- Sabine: REVENUE=€4.207, CHANNEL_NAME="Frauen der Geschichte", SUBS=124K
- Tom: REVENUE=€12.890, CHANNEL_NAME="Imperien Verfolgt", SUBS=487K

---

## 5. VSL THUMBNAIL — audit.html

**Position:** Hero Section, statt Video-Player
**Größe:** 1920×1080 (16:9)
**Datei:** `/website/assets/vsl-thumb.jpg`

### Midjourney-Prompt:
```
YouTube video thumbnail style, professional male presenter (early 30s, casual smart, navy shirt) sitting at modern desk with laptop, large bold text overlay "€8.430/MONAT — OHNE GESICHT", play button icon centered, dark navy background with subtle gradient, gold accent on text, ultra-high CTR design, photorealistic --ar 16:9 --v 6.1 --s 350
```

---

## 6. ICONS / DECORATIVE ELEMENTS

Diese werden via Tailwind/SVG inline gebaut — keine extra Bilder nötig:
- ✓ Checkmarks (HTML/CSS)
- 🛡️ Garantie-Shield (Emoji)
- 🎁 Bonus-Icons (Emoji)
- ⚡ CTA-Akzente (HTML/CSS)

---

## 7. TESTIMONIAL-BILDER (für später, Wo 4+)

Für jeden echten Inner-Circle-Member (sobald du welche hast):

**Format:** Headshot 200×200 + Quote
**Tool:** Open-Generative-AI mit echtem Foto-Reference oder echte Persona-Bilder

---

## QUICK-PRODUKTIONS-WORKFLOW

```bash
# 1. Open-Generative-AI/Midjourney öffnen
# 2. Prompts oben einzeln paste
# 3. Best Variant downloaden
# 4. Optimieren mit:

cd /Users/michael.systems/Documents/claude-workspace-template/outputs/maskpilot-pro/website/
mkdir -p assets

# JPG-Optimierung (falls cwebp installiert)
cwebp -q 80 hero-dashboard.png -o assets/hero-dashboard.webp

# Oder einfach mit ImageOptim, TinyPNG etc.
```

---

## WO BILDER EINGEFÜGT WERDEN

| HTML File | Element | Image |
|-----------|---------|-------|
| `index.html` | Hero-Image-Placeholder (line ~120) | `assets/hero-dashboard.jpg` |
| `index.html` | Author-Avatar (line ~110) | `assets/avatar-michael.jpg` |
| `audit.html` | VSL-Block (line ~75) | `assets/vsl-thumb.jpg` |
| Alle | OG/Twitter-Card | `assets/og-image.jpg` |

### Code-Beispiel für Replace:
```html
<!-- Vorher (Placeholder) -->
<div class="bg-slate-100 rounded-2xl aspect-video mb-12 flex items-center justify-center text-slate-400">
  <span class="text-sm">[YouTube Studio Dashboard — €8.430,17 April 2026]</span>
</div>

<!-- Nachher -->
<img src="/assets/hero-dashboard.jpg" alt="YouTube Studio Dashboard zeigt €8.430,17 monatliche Einnahmen" class="rounded-2xl aspect-video w-full mb-12 object-cover" loading="lazy" />
```

---

## BUDGET-OPTIONEN

### Free-Stack (€0):
- DALL-E 3 free tier (ChatGPT Plus, 50 Bilder/Tag)
- Bing Image Creator (kostenlos)
- Stable Diffusion local (kostenlos, brauche GPU)
- **Quality:** 7/10

### Standard (€10-€30):
- Midjourney Basic (€10/Mo, 200 Bilder)
- Flux 1.1 Pro via Replicate ($1 = 25 Bilder)
- **Quality:** 9/10

### Premium (€100+):
- Open-Generative-AI (€0/Mo, self-hosted via npm) — beste Persona-Konsistenz
- Midjourney Pro (€60/Mo, unlimited)
- **Quality:** 10/10

> **Empfehlung für Launch:** Midjourney Basic + Open-Generative-AI für Personas (~€140/Mo). Reicht für alle Marketing-Assets.
