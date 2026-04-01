# 02 - Design System And Rules

This file is the most important one for recreating the same quality later.

## 1. Design objective

Build pages that feel:

- premium
- cinematic
- technical
- deliberate
- readable
- trustworthy

Avoid pages that feel:

- generic SaaS template
- flat and boxy
- over-animated
- noisy
- cramped
- visually inconsistent

## 2. Typography system

### Pairing used

- Heading: `Playfair Display`
- Body/UI: `Inter`

Why this pairing works:

- The serif heading gives the page authority and editorial polish.
- The sans body keeps dense technical content easy to read.
- The contrast creates immediate hierarchy.

### Rule

- Use serif for large hero and section titles only.
- Use sans for body copy, nav, cards, pills, labels, and UI controls.

## 3. Color system

### Guide page core colors

- Background: `#060816`
- Soft background: `#0d1226`
- Text: `#f5f7ff`
- Muted: `#b6c0e5`
- Accent 1: `#8ea2ff`
- Accent 2: `#7be7c7`
- Accent 3: `#f4c56c`

### Landing page core colors

- Background: `#050714`
- Surface: `rgba(12, 18, 38, 0.72)`
- Text: `#f6f7ff`
- Muted: `#bac4e7`
- Accent 1: `#8ea2ff`
- Accent 2: `#7be7c7`
- Accent 3: `#f4c56c`

### Color rules

1. Keep the base dark and neutral.
2. Use only 2 to 3 accent colors.
3. Use accent colors as highlights, not full-page fill colors.
4. Use muted text generously for secondary detail.
5. Keep important text close to white.

## 4. Surface system

The pages use a repeated panel language:

- dark translucent surfaces
- thin light borders
- large radii
- strong blur
- soft deep shadows

### Standard surface recipe

Use this pattern repeatedly:

```css
background: rgba(10, 15, 31, 0.72);
border: 1px solid rgba(255, 255, 255, 0.1);
backdrop-filter: blur(18px);
box-shadow: 0 28px 120px rgba(0, 0, 0, 0.38);
border-radius: 24px;
```

### Rule

If every component has a different panel look, the page stops feeling premium.

Use the same panel recipe everywhere, then vary only:

- size
- spacing
- emphasis

## 5. Radius system

Rounded corners are part of the identity.

Use only a few consistent values:

- `32px` for hero and major shells
- `24px` for main cards
- `18px` for chips, media, inner containers
- `999px` for pills and nav/button capsules

### Rule

Do not mix random values like `7px`, `13px`, `29px`, `18px`, `6px`.

Use a radius scale, not improvisation.

## 6. Layout system

### Container rule

Use a centered max-width container:

```css
width: min(calc(100% - 32px), 1200px or 1240px);
margin: 0 auto;
```

### Section rule

Each major section should have one clear role:

- orient
- persuade
- summarize
- navigate
- support action

### Grid rule

Use a 12-column grid for content sections.

This gives you easy combinations like:

- 4 / 4 / 4
- 6 / 6
- 8 / 4
- 12

## 7. Hero system

The hero must do five jobs quickly:

1. establish tone
2. explain what this page is
3. show the main value
4. provide the primary action
5. make the page feel premium immediately

### Hero formula

- Eyebrow
- Large serif headline
- One supporting paragraph
- Primary CTA and secondary CTA
- Supporting chips or signal pills

## 8. Motion system

### Motion used

- fade-lift on entry
- slow floating panel animation
- hover lift on interactive elements

### Rules

1. Animate only high-value elements.
2. Use slow, soft easing.
3. Avoid bouncing, spinning, or overly playful motion.
4. Respect `prefers-reduced-motion`.

### Example

```css
@keyframes fade-lift {
  from {
    opacity: 0;
    transform: translateY(20px);
  }

  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes float-panel {
  0%,
  100% {
    transform: translateY(0);
  }

  50% {
    transform: translateY(-8px);
  }
}
```

## 9. Content hierarchy rules

The pages look good partly because the content is layered correctly.

### Priority order

1. headline
2. orientation sentence
3. primary CTA
4. signal chips/cards
5. major sections
6. detailed tables and long-form content

### Rule

If everything has the same visual weight, the page feels amateur.

## 10. Accessibility rules

Always include:

- visible focus states
- adequate contrast
- reduced motion support
- full-width mobile actions where needed
- readable paragraph width
- hover states that do not shift layout aggressively

## 11. Anti-patterns to avoid

Do not use:

- too many gradients
- neon everywhere
- multiple unrelated accent colors
- too many tiny text sizes
- giant paragraphs without grouping
- hover scale effects on many elements at once
- framework runtime dependencies for plain HTML deployment

## 12. Golden rule

Premium UI usually comes from subtraction, not addition.

Make fewer, stronger decisions and repeat them consistently.
