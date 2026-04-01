# 05 - Static HTML Blueprint

Use this as the default architecture for premium static pages.

## File structure recommendation

If the project is simple:

```text
index.html
about.html
guide.html
assets/
```

If the project has a main landing page plus a detail page:

```text
index.html
section-name/
  detail-page.html
  asset-1.md
  asset-2.mp4
```

## Base HTML shape

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Your Page Title</title>
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link href="YOUR_FONT_URL" rel="stylesheet" />
    <style>
      /* design system */
      /* layout */
      /* components */
      /* motion */
      /* responsive */
      /* reduced motion */
    </style>
  </head>
  <body>
    <main class="shell">
      <!-- nav -->
      <!-- hero -->
      <!-- overview -->
      <!-- content sections -->
      <!-- footer / CTA -->
    </main>

    <script>
      // small local interactions only
    </script>
  </body>
</html>
```

## CSS primitives you should always define

### 1. Design tokens

```css
:root {
  --text: #f6f7ff;
  --muted: #bac4e7;
  --accent: #8ea2ff;
  --accent-2: #7be7c7;
  --accent-3: #f4c56c;
  --shadow: 0 28px 100px rgba(0, 0, 0, 0.36);
  --max: 1200px;
}
```

### 2. Shell container

```css
.shell {
  width: min(calc(100% - 32px), var(--max));
  margin: 0 auto;
  padding: 20px 0 64px;
}
```

### 3. Panel system

```css
.panel,
.card,
.feature {
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 24px;
  background: rgba(10, 15, 31, 0.78);
  backdrop-filter: blur(18px);
  box-shadow: var(--shadow);
}
```

### 4. Eyebrow label

```css
.eyebrow {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 8px 14px;
  border-radius: 999px;
  letter-spacing: 0.12em;
  text-transform: uppercase;
}
```

### 5. Motion

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
```

## Section blueprint

### Landing page

Use this order:

1. sticky nav
2. hero
3. overview cards
4. path/features section
5. CTA band

### Long guide page

Use this order:

1. sticky nav
2. hero
3. summary cards
4. chapter shell
5. support resources

## How to keep HTML files beautiful

### Rule 1

Use sections with purpose.

Each section should answer one question only.

### Rule 2

Use a small component vocabulary.

Examples:

- hero
- card
- panel
- chip
- CTA band
- tab button

### Rule 3

Never let content become one giant uninterrupted block.

Break it using:

- cards
- headings
- callouts
- tables
- chapter tabs

### Rule 4

Use hover motion only when it helps interactivity.

### Rule 5

Keep the visual language consistent across files.

If `index.html` and the inner page feel unrelated, the project feels weaker.

## Local JavaScript pattern

Keep JS narrow and purposeful.

Example use cases:

- chapter tabs
- accordions
- small nav toggles
- active state switching

Do not use JS for:

- rendering the whole page when static HTML would work
- layout that should be done in CSS
- decorative behavior that adds fragility

## When to use Framer Motion instead

Use Framer Motion only when all of these are true:

1. the project is React-based
2. a build process exists
3. deployment supports the built app
4. motion meaningfully improves the experience

If those are not true, use CSS motion instead.
