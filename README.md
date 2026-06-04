# 🎉 Mayur ⚽ 15 — Digital Birthday Comic

A static website: a scrolling football-tennis manga comic (Germany vs. the All-Stars) plus an interactive player-riddle puzzle that reveals the birthday voucher. Built to deploy on **Vercel** straight from **GitHub**.

---

## 📁 What's in here

```
mayur-website/
├── index.html        ← the digital comic (8 frames, bilingual captions, animated scoreboard)
├── puzzle.html       ← the "Wer ist wer?" player riddle → reveals SPORTS EVENT
├── images/           ← all artwork, web-optimised (~4 MB total)
└── README.md         ← this file
```

It's **pure static HTML/CSS/JS** — no build step, no dependencies. You can open `index.html` directly in a browser to preview.

---

## 🟥 ONE IMAGE STILL TO GENERATE — Frame 8 (the winning goal)

Everything is wired up **except the final splash panel**. The site already shows a styled "noch zu generieren" placeholder in its slot. The moment you drop the file in, it appears automatically — no code change needed.

**1. Generate it in the Gemini app** (🍌 *Create images* → Nano Banana, *Pro* mode). For the matching face, attach your saved **Frame 5 Mayur character** as a reference image. Paste this prompt:

> Full-width comic splash panel, vintage 1980s–90s shōnen sports-manga style, bold black ink outlines, flat cel shading, dramatic low dynamic angle, action speed lines and halftone screentones, high-contrast clean line art, vibrant colour.
> Centre hero: a 15-year-old boy with dark curly hair in a white German football kit, number 10, yellow captain armband, caught mid-air in an acrobatic leap, swinging a tennis racket downward between his own legs — a "tweener" between-the-legs shot — striking the ball and rocketing it into the goal. A huge impact starburst where the racket meets the ball; the net bulges; the goalkeeper in green is beaten, diving the wrong way. Both a football and a tennis ball streak into the top corner together.
> Around him: white-kit teammates sprinting and leaping in to celebrate, arms raised; in the background the black-and-gold All-Stars stand and applaud. A packed floodlit night stadium, fireworks overhead, golden confetti raining down.
> On-image text (render clearly): a stadium banner reading "ALLES GUTE ZUM 15., MAYUR!"; a corner scoreboard reading "GERMANY 3 – ALL-STARS 2"; a big jagged sound-effect "TOOOR!" and a spiky move-name burst "GEBURTSTAGS-TWEENER!"

**2. Save the result** into the `images/` folder with **exactly** this filename:

```
images/frame8-tweener-3-2.jpg
```

(A wide ~16:9 image works best. Resize to ~1280px wide and save as JPG to keep it small, like the others.)

That's the only thing missing. Optional: you can also re-generate any other frame and overwrite its file using the same names listed below.

### Image filename map (for reference)

| Frame | File | Status |
|---|---|---|
| 1 — Line-up & stadium | `images/frame1-lineup.jpg` | ✅ |
| 2 — The new sport | `images/frame2-newsport.jpg` | ✅ |
| 3 — All-Stars 1–0 | `images/frame3-allstars-1-0.jpg` | ✅ |
| 4 — All-Stars 2–0 | `images/frame4-allstars-2-0.jpg` | ✅ |
| 5 — Mayur close-up | `images/frame5-mayur-closeup.jpg` | ✅ (alt: `frame5-alt-closeup.jpg`) |
| 6 — Mayur 2–1 | `images/frame6-mayur-2-1.jpg` | ✅ |
| 7 — Equalizer 2–2 | `images/frame7-equalizer-2-2.jpg` | ✅ |
| **8 — Tweener 3–2** | `images/frame8-tweener-3-2.jpg` | ❌ **generate this** |
| Bonus colour art | `images/bonus1-color.jpg` … `bonus3-color.jpg` | ✅ |

---

## 🚀 Deploy to Vercel (via GitHub)

**Option A — GitHub website + Vercel (no terminal):**

1. Create a new repo on [github.com](https://github.com/new), e.g. `mayur-bday`.
2. Click **"uploading an existing file"** and drag in the whole contents of this `mayur-website` folder (including the `images` folder).
3. Go to [vercel.com](https://vercel.com) → **Add New… → Project** → import the `mayur-bday` repo.
4. Framework preset: **Other**. Leave build command empty, output directory empty (it's static). Click **Deploy**.
5. Done — Vercel gives you a live URL like `mayur-bday.vercel.app`.

**Option B — command line:**

```bash
cd mayur-website
git init && git add . && git commit -m "Mayur birthday comic"
# create the repo on github first, then:
git remote add origin https://github.com/<you>/mayur-bday.git
git push -u origin main
# then import on vercel.com, or:
npx vercel --prod
```

**To update later** (e.g. after adding Frame 8): replace/add the image, then re-upload to GitHub (or `git add . && git commit -m "add frame 8" && git push`). Vercel redeploys automatically.

---

## 🔧 Notes

- **`lang="de"`** on the comic, bilingual captions (German headline + English subline) throughout.
- The **scoreboard** at the top sticks and animates 0–0 → 3–2 as you scroll through the frames.
- The **puzzle** solution is `SPORTS EVENT`. If you want it to spell the *actual* event instead, the riddle list lives in the `<script>` at the bottom of `puzzle.html` (`ENTRIES` array + `TARGET`).
- Everything is mobile-first — it's meant to be opened on a phone.

Made for Mayur, captain of the day. 🏆
