# 04 - AI Prompts

Use these prompts directly in Claude, ChatGPT, OpenCode, Cursor, or similar tools.

## Prompt 1: Premium static landing page

```text
Build me a premium static HTML landing page with inline CSS and local JavaScript only.

Requirements:
- No framework runtime dependency for the visible content
- It must work reliably on GitHub Pages
- Use a static-first approach
- Use a premium dark editorial aesthetic
- Use one serif heading font and one sans body font
- Use large rounded glass-like panels
- Use subtle ambient gradients and restrained motion
- Add reduced-motion support
- Make desktop and mobile both feel polished
- Use strong content hierarchy and clear CTA placement
- Avoid generic SaaS template feel

Design language:
- dark cinematic background
- soft radial glows
- thin bright borders
- translucent panels
- strong typography contrast
- soft hover lift
- section reveal animations via CSS only

Implementation rules:
- Use a max-width shell container
- Use a strong hero
- Use overview cards
- Use a CTA band near the bottom
- Use only HTML, CSS, and local JS
- Prefer relative links
- Keep the code in a single deployable HTML file if possible

Before writing code:
1. Define the visual system
2. Define the section order
3. Explain the content hierarchy briefly

Then write the final HTML.
```

## Prompt 2: Long-form guide page with chapters

```text
Build me a premium static HTML guide page for dense content.

Requirements:
- Static HTML only for the actual rendered content
- Local JavaScript allowed for tabs/chapter switching
- No CDN framework dependency for core rendering
- Premium dark visual system
- Sticky topbar
- Cinematic hero
- Overview cards
- Story cards
- Chapter tabs
- Dense content displayed in clear panels
- Tables, callouts, code blocks, and media embeds must look polished
- Fully responsive
- Reduced-motion support required

Design goals:
- make heavy information feel premium
- avoid one long ugly document
- improve scanability
- preserve depth without clutter

Visual direction:
- deep navy background
- translucent panels
- serif section titles
- sans UI/body text
- soft accent colors only
- large radius system
- subtle fade-lift motion

Structure:
1. sticky nav
2. hero
3. overview cards
4. story summary cards
5. chapter shell with interactive tabs
6. footer resource zone

Before coding:
1. Define the design system
2. Define reusable CSS primitives
3. Explain how the chapter system will work

Then write the full HTML.
```

## Prompt 3: Design-system-first prompt

```text
Do not start by writing random UI code.

First, produce a design system for this page with:
- page type
- conversion goal
- section order
- typography pairing
- color palette
- radius scale
- panel style
- button style
- motion style
- accessibility rules
- anti-patterns to avoid

Then build the page using only that system.
Every component must visibly belong to the same system.
```

## Prompt 4: Static-first GitHub Pages prompt

```text
The final page will be deployed as a plain HTML file on GitHub Pages.

So:
- do not rely on React or Framer Motion to render the visible content
- do not assume a build step exists
- use HTML, CSS, and local JavaScript only
- use CSS keyframes for motion
- use local JS only for small interactions like tabs or accordions
- ensure the content still works if third-party script loading is blocked
```

## Prompt 5: Quality upgrade prompt for existing ugly pages

```text
Take my existing static HTML page and redesign it into a premium dark editorial page.

Keep:
- the content
- the relative links
- the file deployable as plain HTML

Improve:
- typography hierarchy
- color system
- spacing rhythm
- card system
- CTA clarity
- responsiveness
- motion quality
- visual polish

Constraints:
- no framework runtime needed for core rendering
- no generic template look
- no excessive animation
- must feel intentional and premium
```

## Prompt 6: If you do have a real React build setup

Use this only if the project is actually Vite/Next/React and has a proper build process.

```text
Build this page in React with Framer Motion.

Requirements:
- use Framer Motion for hero entrance, section reveal, tab transitions, and hover polish
- still keep motion restrained and premium
- respect prefers-reduced-motion
- keep the same design system: dark editorial, serif headings, glass-like surfaces, clear CTA hierarchy
- do not animate everything
- use Framer Motion only where it improves attention flow and clarity
```

## Best practice when using prompts

When sending prompts to AI tools, also include:

- the actual content
- the deployment context
- whether it is static HTML or React
- the desired visual mood
- examples of what to avoid

The more specific the constraints, the better the result.
