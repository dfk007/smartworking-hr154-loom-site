# How I UI/UX Maxed The Pages

This directory is a reusable documentation kit for creating high-quality static HTML landing pages and guide pages like:

- `index.html`
- `2-opencode-loom/opencode-loom-script-final.html`

It is written so you can hand it to any AI tool such as Claude, ChatGPT, OpenCode, Cursor, or similar and get consistently better-looking pages.

## What this kit teaches

- How to design premium-looking static pages without a framework build step
- How to use a design-system-first workflow instead of random UI decisions
- How to structure content so the page feels intentional, cinematic, and readable
- How to add tasteful motion using CSS and local JavaScript only
- How to keep the result reliable on GitHub Pages

## Files in this folder

- `01-what-was-built.md`
  Direct explanation of the two shipped pages and what patterns they use.

- `02-design-system-and-rules.md`
  The exact visual rules, spacing logic, typography strategy, color system, and motion rules.

- `03-step-by-step-workflow.md`
  The end-to-end workflow to follow in future projects.

- `04-ai-prompts.md`
  Copy-paste prompts you can use in AI tools to generate strong page designs.

- `05-static-html-blueprint.md`
  A reusable blueprint for building static-first premium HTML pages.

- `06-deploy-and-qa.md`
  Deployment, QA, accessibility, and GitHub Pages reliability guidance.

## Core lesson

The best-looking pages were not created by asking an AI to "make it beautiful".

They were created by doing these things in order:

1. Define the page type and conversion goal.
2. Define a design system before touching layout.
3. Create strong content hierarchy.
4. Use a limited set of premium visual devices repeatedly.
5. Add restrained motion.
6. Keep deployment constraints in mind from the start.

## Important implementation note

The original request asked for Framer Motion. That was explored, but the final deployed pages were intentionally made `static-first` using:

- HTML
- CSS
- local JavaScript
- Google Fonts

Reason: GitHub Pages is more reliable when the rendered content does not depend on an external JavaScript runtime.

This is the main practical lesson from the project:

- Use Framer Motion in a real React/Vite/Next app.
- Use CSS animations and local JS in plain static HTML deployments.

## Fastest way to use this kit later

1. Read `02-design-system-and-rules.md`.
2. Read `03-step-by-step-workflow.md`.
3. Copy the relevant prompt from `04-ai-prompts.md` into your AI tool.
4. Build from the blueprint in `05-static-html-blueprint.md`.
5. Run the QA checklist in `06-deploy-and-qa.md`.

## Short version

If you only remember five rules, remember these:

1. Build static-first if the site is just HTML files.
2. Use one strong visual system, not five competing ideas.
3. Use content hierarchy to make the page feel premium.
4. Use motion to guide attention, not decorate everything.
5. Design for the deployment target, not only the local machine.
