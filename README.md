# Celluloid Dreams
<p align="center">
  <img src="https://raw.githubusercontent.com/ztffn/Jellyfin-Celluloid-Theme/main/Previews/celluloidD3.png" alt="Celluloid Theme banner" width="100%">
</p>




***A custom theme for <a href="https://jellyfin.org/">Jellyfin</a> inspired by light leaks, film grain, and the quiet magic of cinema. Designed for rich visuals, clean typography, and a minimal, immersive viewing experience.***

---
> [!NOTE]
> Beta Status: This theme was made for personal use. It has many rough edges, and might not look good on your system. Progress to make it public is slow, but you are invited to try it out and post issues to help bring it along - or better yet, contribute to it. It will leave beta when the roadmap is completed and the experience is satisfying.
    
## 📣 Roadmap / Status

- [x] Repository scaffolding & docs
- [ ] Clean up initial Celluloid CSS
- [ ] Move advanced features into desktop only
- [ ] Patch for Jellyfin 10.11
- [ ] Cross browser compatibility
- [ ] Publish preview gallery
- [ ] Tag v0.9.0 release & announce

---

## 🎬 Features

- Animated backgrounds inspired by light leaks and the organic glow of exposed film
- Vertical navigation menu with quick-access links to admin and settings pages
- Beautiful item highlights with a soft backlit glow 
- Minimal typography and simplified web elements. Posters and movie artwork take center stage
- Bold play buttons and clear info cues for interactable elements
- Multiple built-in color themes (Purple and Blue) with easy switching


---
> I like celluloid, I like film, I like the way that when a movie is projected it sort of breathes a little in the gate. That's the magic of it to me.
> 
> <sub>Gary Oldman</sub>
---

## 🎥 Preview

[coming]
---

## 🧩 Installation

Until the packaged release is published, you can preview the theme by referencing the CSS directly from this repository.

### Option 1 — Jellyfin Dashboard (Custom CSS)

1. Go to **Dashboard → General → Custom CSS**.
2. Paste one of the following snippets at the bottom of the box:

   **Stable build (recommended):**
   ```css
   @import url("https://rawcdn.githack.com/ztffn/Jellyfin-Celluloid-Theme/main/Theme/celluloid.css");
   ```

   **Nightly build (latest changes, may break):**
   ```css
   @import url("https://rawcdn.githack.com/ztffn/Jellyfin-Celluloid-Theme/main/Theme/celluloid-nightly.css");
   ```

   > We use rawcdn.githack.com so the files are served with the correct MIME type. Feel free to self-host or switch to jsDelivr once their cache picks up the repository.

3. Click **Save** and hard-refresh your browser/app (`Ctrl + Shift + R` / `Cmd + Shift + R`).

### Option 2 — Host Locally

1. Copy the content of `Theme/celluloid.css` 
2. In **Dashboard → Branding → Custom CSS**, paste in the full content of the css, with any modificatons you'd like:
3. Save and refresh.

> **Note:** You won't recieve any updates automatically this way, so its not recomended until the release is more stable.

### Theme Switching
> [!WARNING]
> I haven't gotten this to work as intended. Currently only way to swap themes is by editing css. 
> 
Celluloid Theme comes with two built-in color themes: **Blue** (default) and **Purple**.

> The stylesheet also listens for Jellyfin's own `data-theme="…"` attribute, so in 10.11+ you can trigger a switch by using Jellyfin's native theme toggles.

#### Method 1: URL Parameter

Add `?theme=blue` or `?theme=purple` to your Jellyfin URL:
```
http://your-jellyfin-server:8096/web/index.html?theme=blue
```

#### Method 2: Custom CSS

Add one of these lines to your Custom CSS in the Jellyfin Dashboard (after the theme import):

```css
/* For Blue Theme */
html { --theme-selection: blue; }

/* For Purple Theme */
html { --theme-selection: purple; }
```

~~This custom property override is used whenever Jellyfin doesn't set a `data-theme` attribute (older versions, or custom embed views).~~

~~For more customization options, see the [customization guide](docs/customization.md).~~


---

## 🎨 Customization

~~Celluloid is designed to be easily customizable. You can modify the theme's appearance by adjusting the CSS variables.~~

### Color Scheme

~~To customize the color scheme, add the following to your Custom CSS after importing the theme:~~

```css
:root {
    /* Change colors to your preference (RGB values) */
    --white: 255, 255, 255;           /* Text and highlights */
    --white-off: 230, 230, 230;       /* Secondary text */
    --jade-green: 0, 200, 100;        /* Success indicators */
    --honey-yellow: 255, 200, 0;      /* Stars and warnings */
    --cherry-red: 220, 50, 50;        /* Error states */
    --deep-blue: 50, 100, 255;        /* Links and focus states */
    
    /* Main accent color - use one of the above or define your own */
    --accent: var(--jade-green);      
}
```

### UI Rounding

~~To enable custom rounding throughout the UI, add:~~

```css
:root {
    /* Customize UI element rounding */
    --rounding: 12px;                 /* Default rounding for most elements */
    --rounding-alt: 9px;              /* Alternative rounding for smaller elements */
    --rounding-large: 24px;           /* Larger rounding for prominent elements */
    --rounding-circle: 100px;         /* Full circle rounding for avatar elements */
}
```

### Additional Customizations

~~For more advanced customizations, check out the `docs/` folder for additional recipes and examples.~~

## 🛠️ Development

Want to help shape the theme?

1. Clone the repo and create a feature branch.
2. Work out of `Theme/celluloid-nightly.css` (feel free to break auxiliary snippets into `docs/` as needed).
3. Run your changes locally by pointing Jellyfin to your branch copy via `@import url("https://rawcdn.githack.com/<username>/Jellyfin-Celluloid-Theme/<branch>/Theme/celluloid.css");`.
4. Submit a PR with before/after screenshots when possible.

Please keep new CSS tokens documented so we can maintain predictable customizations.

---

## 🐞 Troubleshooting

### Common Issues

- **Theme not applying**: Make sure you've added the import as the last line in your Custom CSS and performed a hard refresh (`Ctrl + Shift + R` / `Cmd + Shift + R`).
- **Vertical menu not showing**: The vertical menu is designed to be visible on desktop views. It will automatically hide during video playback.
- **Light leaks not visible**: The animated light leaks are subtle by design and may vary depending on your system (Does not currently work on Tizen TVs)

### Browser Compatibility

Celluloid Theme is tested and optimized for:
- ~~Chrome/Edge (latest)~~
- Firefox (latest)
- ~~Safari (latest)~~

If you encounter issues on a specific browser, please report them in the GitHub issues.

---
