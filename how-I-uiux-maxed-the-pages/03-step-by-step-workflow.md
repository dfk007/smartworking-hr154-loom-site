# 03 - Step By Step Workflow

Use this workflow exactly when building future high-quality pages.

## Step 1: Identify the page type

Before generating anything, decide what the page is.

Examples:

- landing page
- case study
- portfolio page
- documentation hub
- product detail page
- event page
- guide page

Why:

- Different page types need different section order and emphasis.

## Step 2: Identify the conversion goal

What should the user do?

Examples:

- read
- sign up
- contact
- book demo
- review material
- watch media
- download assets

Why:

- Good design is not decoration. It supports action.

## Step 3: Generate a design system first

If you have `ui-ux-pro-max` installed, start here.

### Commands used in this project

```bash
python3 .opencode/skills/ui-ux-pro-max/scripts/search.py "landing page technical portfolio cinematic dark premium motion" --design-system -p "OpenCode Loom" -f markdown

python3 .opencode/skills/ui-ux-pro-max/scripts/search.py "animation accessibility motion storytelling landing" --domain ux

python3 .opencode/skills/ui-ux-pro-max/scripts/search.py "landing page hero trust proof conversion" --domain landing

python3 .opencode/skills/ui-ux-pro-max/scripts/search.py "dark cinematic technical storytelling landing premium" --design-system -p "OpenCode Loom" -f markdown

python3 .opencode/skills/ui-ux-pro-max/scripts/search.py "dark premium modern editorial" --domain typography
```

### Why this step matters

This prevents random design drift.

You should decide up front:

- layout pattern
- typography pairing
- color direction
- motion strategy
- CTA placement

## Step 4: Decide deployment constraints early

Ask this before building:

- Is this a static HTML deployment?
- Is this GitHub Pages?
- Is there a framework build step?

### Rule used here

- Static HTML deployment => static-first implementation.

That means:

- HTML for visible content
- CSS for motion and styling
- local JavaScript for small interactions
- avoid framework runtime dependency for core rendering

## Step 5: Create the content hierarchy

Before writing code, group content into levels.

### Recommended order

1. hero
2. orientation summary
3. signals or summary cards
4. main narrative sections
5. detailed support content
6. final CTA or resource zone

### For long guide pages

Convert content into chapters or tabs instead of one endless scroll block.

## Step 6: Build the hero first

Do not start from tiny components.

Start from:

- page background
- shell/container width
- top nav
- hero layout
- hero typography
- primary actions

Why:

- The first screen sets the visual language for the whole page.

## Step 7: Create reusable visual primitives

In the CSS, define a small number of reusable building blocks:

- shell/container
- panel/card
- button
- ghost button
- eyebrow
- chips/pills
- overview cards
- section headings

Why:

- Repeatable primitives create consistency fast.

## Step 8: Add motion after the layout works

Never start by animating things.

The correct order is:

1. structure
2. hierarchy
3. readability
4. interaction
5. motion

### Motion added in this project

- section fade-lift
- panel float
- hover translation
- reduced-motion override

## Step 9: Make dense content easier to read

For heavy informational pages:

- break content into cards
- use tables only where comparison is needed
- use callouts for high-signal notes
- use monospace blocks for scripts and dense text
- use media embeds sparingly and clearly

## Step 10: Build responsive behavior intentionally

Do not wait for responsiveness at the end.

In practice:

- collapse multi-column hero to one column
- turn 4/4/4 card rows into stacked cards on small screens
- make major actions full width on mobile
- reduce title sizes using `clamp()`

## Step 11: Add reduced-motion support

Always include:

```css
@media (prefers-reduced-motion: reduce) {
  html {
    scroll-behavior: auto;
  }

  *,
  *::before,
  *::after {
    animation: none !important;
    transition-duration: 0.01ms !important;
    transition-delay: 0ms !important;
  }
}
```

## Step 12: Validate for deployment reality

Ask these questions:

- Will this page render with no build step?
- Will all relative links work after deploy?
- Does it still show content if external resources fail?
- Does it still look good on mobile?

## Step 13: Format and publish

Commands used here:

```bash
npx prettier --write "index.html" "2-opencode-loom/opencode-loom-script-final.html"
git add "index.html" "2-opencode-loom/opencode-loom-script-final.html"
git commit -m "Make GitHub Pages landing and guide static-first"
git push origin main
```

## Final workflow summary

Use this order every time:

1. page type
2. goal
3. design system
4. deployment constraints
5. content hierarchy
6. hero
7. reusable primitives
8. motion
9. responsive pass
10. reduced motion
11. QA
12. deploy
