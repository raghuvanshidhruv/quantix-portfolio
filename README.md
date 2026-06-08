# Quantix Solutions — Portfolio

A single-file, static portfolio site for Quantix Solutions. No build step, no framework, no dependencies. Just open `index.html` to preview locally, or push it to Vercel.

## Stack

- Plain HTML, CSS, vanilla JS
- Google Fonts (Bricolage Grotesque, Instrument Serif, Manrope, JetBrains Mono)
- All custom SVG mockups — no image files needed

## Local preview

Just open the file:

```bash
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

Or run any static server:

```bash
npx serve .
# or
python3 -m http.server 3000
```

## Deploy to Vercel — three ways

### Option 1: Drag and drop (fastest, ~30 seconds)

1. Go to [vercel.com/new](https://vercel.com/new)
2. Drag the whole `quantix-portfolio` folder into the dropzone
3. Click **Deploy**
4. Done — you'll get a `*.vercel.app` URL

### Option 2: Vercel CLI

```bash
npm install -g vercel
cd quantix-portfolio
vercel
```

Follow the prompts (project name → `quantix-portfolio`, framework → `Other`, no build command needed). Run `vercel --prod` when you're ready to ship the production URL.

### Option 3: GitHub + Vercel (recommended for ongoing edits)

```bash
cd quantix-portfolio
git init
git add .
git commit -m "Initial Quantix Solutions portfolio"
gh repo create quantix-portfolio --public --source=. --push
```

Then on [vercel.com/new](https://vercel.com/new) → **Import Git Repository** → pick `quantix-portfolio` → **Deploy**. Every future `git push` will auto-deploy.

## Customizing

Everything is in `index.html`. The site is split into clearly commented sections.

**Quick swaps:**

| What you want to change | Where to look |
|---|---|
| Contact email | Search `hello@quantixsolutions.studio` and replace |
| Stats in the hero (3 yrs, 25+ projects, etc.) | Hero `<div class="hero-meta">` block |
| Project case studies | Work section (`<section id="work">`) |
| Testimonial names & quotes | Testimonials section |
| Brand colors (gradients) | `:root` CSS variables at the top of `<style>` |
| Logo wordmark | `<a class="logo">` blocks (3 instances: nav, footer) |

**Brand color quick reference:**

```css
--blue:   #3b82f6
--violet: #8b5cf6
--pink:   #ec4899
--lime:   #a3e635
```

To shift the whole vibe (e.g. cyan/green instead of blue/pink), change the `--grad-primary` variable in `:root`.

## Custom domain on Vercel

1. Vercel dashboard → your project → **Settings** → **Domains**
2. Add your domain (e.g. `quantixsolutions.studio`)
3. Vercel will show DNS records — add them at your domain registrar
4. SSL is automatic

## Notes

- The site is fully responsive (mobile, tablet, desktop)
- All animations respect `prefers-reduced-motion` indirectly via subtle motion only
- No tracking, no cookies, no third-party scripts
- Lighthouse should score 95+ on performance out of the box

---

Built as a self-contained pitch asset. Swap the projects, testimonials, and contact email and it's ready to share.
