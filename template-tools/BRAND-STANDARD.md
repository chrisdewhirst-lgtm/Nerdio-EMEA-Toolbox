# Nerdio EMEA Toolbox — Brand Standard

Use this file alongside any BUILD template to ensure your generated tool matches the team's brand standard. Upload this file **together** with the BUILD-*.md file when asking Claude to create your tool.

---

## Brand Colors

| Token | Hex | Usage |
|-------|-----|-------|
| Navy | #0B1B3D | Primary dark background, headers |
| Navy Light | #142952 | Gradient dark, hover states |
| Teal | #00B4D8 | Accent, links, CTAs, highlights |
| Green | #00C48C | Success, positive indicators, secondary accent |
| White | #FFFFFF | Text on dark, card backgrounds |
| Grey-50 | #F8FAFC | Page background |
| Grey-100 | #F1F5F9 | Card backgrounds, tag fills |
| Grey-200 | #E2E8F0 | Borders |
| Grey-600 | #475569 | Secondary text |

## Required CSS Variables

Every tool MUST include these at the top of its `<style>` block:

```css
:root {
  --navy: #0B1B3D;
  --navy-light: #142952;
  --teal: #00B4D8;
  --green: #00C48C;
  --white: #FFFFFF;
  --grey-50: #F8FAFC;
  --grey-100: #F1F5F9;
  --grey-200: #E2E8F0;
  --grey-600: #475569;
}
```

## Font Stack

```css
font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
```

## Required Brand Bar

Every tool MUST include a fixed nav bar at the top (48px height) with:
- **Left:** Nerdio logo (white horizontal variant, 22px height) + divider + tool name
- **Right:** "Toolbox Home" button linking to `../EMEA-Nerdio-Toolbox.html`
- **Background:** `linear-gradient(135deg, #0B1B3D 0%, #142952 100%)`
- **z-index:** 99999 (above all other content)

Below the brand bar, add a 48px spacer div to push content down.

Any sticky or fixed headers in the tool content should use `top: 48px` (not `top: 0`) to account for the brand bar.

### Brand Bar HTML Template

```html
<div class="nerdio-brand-bar">
  <div class="nerdio-brand-logo">
    <img src="data:image/png;base64,[LOGO_BASE64_HERE]" alt="Nerdio">
    <div class="nerdio-brand-divider"></div>
    <span class="nerdio-brand-tool-name">[TOOL NAME HERE]</span>
  </div>
  <a href="../EMEA-Nerdio-Toolbox.html" class="nerdio-brand-home">
    <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
      <path d="M3 9l9-7 9 7v11a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2z"/>
      <polyline points="9 22 9 12 15 12 15 22"/>
    </svg>
    Toolbox Home
  </a>
</div>
<div class="nerdio-brand-spacer"></div>
```

### Brand Bar CSS

```css
.nerdio-brand-bar {
  position: fixed; top: 0; left: 0; right: 0; z-index: 99999;
  height: 48px;
  background: linear-gradient(135deg, #0B1B3D 0%, #142952 100%);
  display: flex; align-items: center; justify-content: space-between;
  padding: 0 20px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.15);
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
}
.nerdio-brand-logo { display: flex; align-items: center; gap: 12px; }
.nerdio-brand-logo img { height: 22px; width: auto; }
.nerdio-brand-divider { width: 1px; height: 20px; background: rgba(255,255,255,0.2); }
.nerdio-brand-tool-name { color: rgba(255,255,255,0.85); font-size: 13px; font-weight: 500; }
.nerdio-brand-home {
  display: flex; align-items: center; gap: 6px;
  color: #00B4D8; text-decoration: none; font-size: 13px; font-weight: 600;
  padding: 6px 14px; border-radius: 6px;
  background: rgba(0,180,216,0.1); border: 1px solid rgba(0,180,216,0.2);
}
.nerdio-brand-home:hover { background: rgba(0,180,216,0.2); color: #FFFFFF; }
.nerdio-brand-home svg { width: 14px; height: 14px; }
.nerdio-brand-spacer { height: 48px; }
```

## Header Style

Tool headers should use:
- Background: `linear-gradient(135deg, var(--navy) 0%, var(--navy-light) 100%)`
- White text
- Optional decorative radial gradient accents (teal/green at low opacity)
- Sticky positioning with `top: 48px`

## Card/Panel Style

- Background: `var(--white)`
- Border: `1px solid var(--grey-200)`
- Border-radius: `12px`
- Hover: border-color changes to `var(--teal)`, subtle shadow

## Button Style

Primary buttons:
- Background: `var(--teal)`
- Color: `var(--white)`
- Border-radius: `8px`
- Hover: darken slightly

Secondary/ghost buttons:
- Background: `transparent` or `rgba(0,180,216,0.08)`
- Color: `var(--teal)`
- Border: `1px solid rgba(0,180,216,0.3)`

## Logo Base64

When asking Claude to create a tool, include this instruction:

> "Use the Nerdio Enterprise logo. Since I can't embed it, use a text-based logo fallback: a navy circle with 'N' in teal, next to 'nerdio' in the brand font."

Or if you have the logo PNG file, upload it alongside this file and ask Claude to embed it as base64.

## Do NOT Use

- Microsoft Azure blue (#0078d4) as primary — that's Microsoft's brand, not Nerdio's
- Bright/neon green — use the muted green (#00C48C)
- Any font other than the system font stack
- Rounded/pill buttons over 8px border-radius
- Drop shadows heavier than `0 4px 12px rgba(0,0,0,0.1)`
