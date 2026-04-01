# 06 - Deploy And QA

This file is about keeping beautiful pages actually working after deployment.

## 1. Deployment rule

Build for the real deployment target.

For plain GitHub Pages:

- prefer static HTML
- prefer relative links
- prefer local JavaScript only
- avoid runtime dependencies for core rendering

## 2. Packages and tools involved in this project

### Design/research tools

- `ui-ux-pro-max` skill
- Python skill search script

### Formatting and publish tools

- `prettier`
- `git`
- `gh`

### Fonts/assets

- Google Fonts

### Final production runtime

- none beyond browser-native HTML/CSS/JS

## 3. Useful commands

### Generate a design system

```bash
python3 .opencode/skills/ui-ux-pro-max/scripts/search.py "dark cinematic technical storytelling landing premium" --design-system -p "Project Name" -f markdown
```

### Format files

```bash
npx prettier --write "index.html" "path/to/page.html"
```

### Check git status

```bash
git status --short --branch
```

### Push to GitHub Pages source branch

```bash
git add .
git commit -m "Your commit message"
git push origin main
```

### Check Pages config

```bash
gh api repos/OWNER/REPO/pages
```

## 4. QA checklist before deploy

### Visual QA

- Does the hero look strong on desktop?
- Does the page still look intentional on mobile?
- Are the panels visually consistent?
- Are the type sizes clearly hierarchical?
- Are the CTAs visually obvious?

### Interaction QA

- Do all buttons and links have hover states?
- Do focus states show clearly?
- Do tabs or local JS interactions work without errors?
- Do media embeds load?

### Accessibility QA

- Is there enough text contrast?
- Is `prefers-reduced-motion` respected?
- Are buttons and links keyboard reachable?
- Are iframes, media, and links clearly labeled?

### Deployment QA

- Are all links relative where they should be?
- Are there any broken asset paths?
- Does the page render even if external script imports fail?
- Does the root page act as a real entry point?

## 5. Common failure modes

### Failure: blank page with only background

Cause:

- content depends on failed JS runtime/import

Fix:

- move visible content into static HTML
- use local JS only for enhancement

### Failure: page looks good locally but broken after push

Cause:

- wrong paths
- framework assumptions in static hosting
- runtime import/network dependency

Fix:

- use relative links
- use static-first rendering
- verify actual GitHub Pages path structure

### Failure: page feels generic

Cause:

- no design system
- weak typography contrast
- too many unrelated colors
- random spacing

Fix:

- define system first
- enforce one visual language consistently

## 6. Final quality standard

Do not consider the page finished until all of these are true:

1. It looks premium above the fold.
2. It remains readable when content gets dense.
3. It feels consistent across all sections.
4. It works on mobile.
5. It survives the actual deployment environment.

## 7. Short reusable rule set

If you want a single quality standard to give an AI tool, use this:

```text
Build a premium static-first HTML page.
Use a strong design system first.
Use dark editorial styling, clear hierarchy, restrained motion, and reliable deployment-safe implementation.
Do not rely on framework runtime for the visible content unless the project is a real built React app.
```
