# APEX

**APEX puts you on the map.**

A cinematic single-page studio site where the background itself is the
demo: five custom WebGL canvases paint hand-painted films as you scroll,
synchronized with every paragraph you read. Built end-to-end — concept,
copy, motion, shaders — by **Yashwanth** for the **3D Websites Hackathon**.

**Live demo → https://yashwanth07-debug.github.io/apex-studio/**

---

## What it is

APEX is a revenue-share growth studio's one-pager — but told as a moving
painting. Instead of images or video embeds, every scene is a scroll-scrubbed
film painted in real time:

- 5 flipbook film sequences (121 frames, 89 frames, …) hand-painted and
  scrubbed by the GPU as the page moves — with a lighter `/768` frame tier
  for mobile
- 4 model reels (`v28`, `v51`, `v61`, `renaissance` — up to 362 frames each)
  playing behind The Work chapters, each with its own `manifest.json`
- 3 MP4 video bridges (`signal`, `colossus`, `reveal`) + a footer loop,
  seamlessly composed next to the canvas films
- A scaffold shader in the hero (`art/scaffold_expand.jpg` as a plate
  texture), burn/tear/ring shaders for scene transitions
- Self-hosted type (Flecha + GT Standard) — the page makes **zero external
  asset requests**

The copy is fully original: the studio pitch (The Model / The Work /
The Terms / Questions) is written for APEX, and the only outbound link in
the page is the author's GitHub profile.

## Judge's quick tour

1. Open the live demo — hero paints the signal film; scroll.
2. **The Model** — the scaffold study ignites into the blueprint film.
3. **The Work** — three service cards over model reels (try mobile vs
   desktop: different frame tiers load).
4. **The Terms** — the golden pear colossus rises behind the copy.
5. **Questions → Apply** — the tree film grows into the coda; the page
   ends on the brand mural with the restore loop.

~2,600 assets check in on every visit, all of them serving one goal:
**the page is downloadable and works identically offline.**

## Tech

Static HTML · the React/Vite bundle driving the canvases · custom GLSL
(film compositor, burn/ring transition shaders, scaffold plate shader) ·
WebP flipbook pipelines · adaptive frame tiers (1440 desktop / 768 mobile).

## Run it

No build step. Any static server works:

```bash
python3 -m http.server 3000
# → http://localhost:3000
```

## Repo structure

```
index.html            the page (copy + structure)
assets/               js + css bundles
films/                flipbooks, model reels, videos, posters (2,607 files)
fonts/                Flecha + GT Standard webfonts
art/                  shader plate texture
docs/screenshots/     desktop + mobile QA shots
```

## What the hackathon taught

Five simultaneous WebGL canvases need discipline: per-frame budgets, tiered
assets for phones, and scrubbed preloading so 2,600 files never stall the
first paint.

## What's next

Apply-form endpoint wiring, alternate coda mural, and a scene that reacts
to pointer input.
