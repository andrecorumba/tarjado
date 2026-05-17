# Tarjado · Document Watermark Tool

A free, open-source tool to add watermarks to document photos before sharing them. Everything runs locally in your browser — your image never leaves your device.

> **Try it:** open `index.html` directly in any modern browser. No install, no server, no account.

---

## Why this exists

Sending a photo of your ID, passport, or utility bill over WhatsApp or email is a common reality — for signing up with clinics, landlords, banks, and service providers. Once that image leaves your phone, you have no control over it.

A clean copy of your document can be used to open accounts, apply for credit, or impersonate you in scams. Adding a watermark specific to the recipient and date makes the copy much less useful for fraud: it can no longer be repurposed without obvious traces.

Tarjado makes this one-click easy.

---

## Features

- **Drag-and-drop upload** — JPG, PNG, WEBP
- **Watermark text** — multiline, fully customizable
- **Color picker** — presets (red, black, white, blue, orange, purple) plus any custom color
- **Opacity** — 5% to 80%
- **Font size** — 2% to 12% of the shorter image dimension
- **Angle** — −90° to +90°
- **Density** — five coverage levels (minimal → maximum)
- **Position** — 9-cell grid (corners, edges, center) or full-coverage tiling
- **Drag to reposition** — when using a single-copy position, click and drag the watermark anywhere on the preview canvas
- **Grayscale mode** — converts the image to gray tones, making color-based fraud harder
- **Download** — exports a PNG with the watermark baked in

---

## Privacy

| What happens | Detail |
|---|---|
| Image processing | 100% in the browser, via Canvas API |
| Server uploads | None — ever |
| Data stored | Nothing — not even in localStorage |
| Works offline | Yes, after the page loads |

You can verify this by opening DevTools → Network and watching zero requests fire after the page loads.

---

## Usage

1. Open `index.html` in your browser (or visit the hosted version).
2. Drop or select a document photo.
3. Type the watermark text — include the recipient and the date. Example:
   ```
   Copy for Bank XYZ
   Account opening · May 2025
   ```
4. Adjust color, opacity, size, angle, and coverage to your liking.
5. Choose a position or leave it on **full coverage** (recommended).
6. Click **Download protected** to save the result.

---

## Honest limitations

Tarjado is not a perfect solution. AI-based inpainting tools can remove watermarks with some effort. However, fraudsters look for easy targets — a watermarked copy raises the cost of misuse. A well-placed, high-opacity watermark is still a meaningful deterrent for casual fraud.

No client-side tool can guarantee document security once an image is shared. This is a practical first step, not a silver bullet.

---

## Running locally

This is a single self-contained HTML file with no build step and no dependencies beyond Google Fonts (loaded from CDN, optional).

```bash
git clone https://github.com/andrecorumba/tarjado.git
cd tarjado
open index.html          # macOS
# or
xdg-open index.html      # Linux
# or just double-click the file in your file manager
```

To serve it over HTTP (useful for testing on mobile):

```bash
python3 -m http.server 8080
# then open http://localhost:8080 on any device on the same network
```

---

## Tech stack

- Vanilla HTML, CSS, JavaScript — zero frameworks, zero dependencies
- Canvas API for image processing and watermark rendering
- `FileReader` + `canvas.toDataURL` for local-only file handling
- IBM Plex Sans / IBM Plex Mono (Google Fonts)

---

## Contributing

Issues and pull requests are welcome. Keep it simple — this tool is intentionally a single file with no build toolchain.

---

## License

MIT — free to use, modify, and distribute.
