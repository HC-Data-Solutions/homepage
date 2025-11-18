# HC Scaling Solutions Design System

## Overview

This design system provides a comprehensive set of guidelines, components, and utilities for maintaining consistency across HC Scaling Solutions' digital products. It encompasses color palettes, typography, spacing, and component patterns.

## Color System

### Primary Colors

| Color              | Hex       | Usage                                       |
| ------------------ | --------- | ------------------------------------------- |
| **Primary Text**   | `#000080` | Headings, primary text, key brand elements  |
| **Primary Accent** | `#000064` | Interactive elements, accents, focus states |

### Secondary Colors

| Color                | Hex       | Usage                                       |
| -------------------- | --------- | ------------------------------------------- |
| **Secondary Accent** | `#000098` | Subheadings, secondary interactive elements |
| **Tertiary Accent**  | `#00008c` | Secondary buttons, subtle highlights        |

### Accent Colors

| Color             | Hex       | Usage                                        |
| ----------------- | --------- | -------------------------------------------- |
| **Bright Accent** | `#00c0fc` | Primary CTAs, important interactive elements |
| **Light Accent**  | `#0000b4` | Links, secondary accents, hover states       |

### Neutral Colors

| Color                 | Hex       | Usage                            |
| --------------------- | --------- | -------------------------------- |
| **Light Background**  | `#ffffff` | Primary light theme background   |
| **Subtle Background** | `#f3f4f6` | Hover states, subtle backgrounds |
| **Light Border**      | `#e5e7eb` | Borders, dividers, separators    |
| **Dark Border**       | `#374151` | Dark theme borders, hover states |
| **Dark Background**   | `#1a1a1a` | Primary dark theme background    |

### Color Usage Guidelines

- **Primary Text** should be used sparingly for the most important headings
- **Bright Accent** should be used for primary calls-to-action and important interactive elements
- **Neutral colors** provide the foundation - use them for backgrounds, borders, and subtle UI elements
- Maintain **WCAG AA contrast ratios** (4.5:1 for normal text, 3:1 for large text)
- **Dark theme** automatically applies appropriate color variants

## Typography System

### Font Families

#### Primary Font (Body Text)

```
System Font Stack:
system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI',
Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif
```

- **Usage**: All body text, paragraphs, UI elements
- **Line Height**: 1.6 (default)
- **Performance**: Uses system fonts for optimal loading speed

#### Display Font (Headings)

```
Orbitron (Google Fonts)
Weights: 400, 500, 600, 700
Fallback: sans-serif
```

- **Usage**: All headings (H1-H6), brand elements, navigation
- **Source**: Google Fonts with preconnect optimization

### Typography Scale

| Class        | Font Size  | Line Height | Usage                        |
| ------------ | ---------- | ----------- | ---------------------------- |
| `.text-xs`   | `0.75rem`  | `1rem`      | Small labels, captions       |
| `.text-sm`   | `0.875rem` | `1.25rem`   | Secondary text, metadata     |
| `.text-base` | `1rem`     | `1.5rem`    | Body text, default size      |
| `.text-lg`   | `1.125rem` | `1.75rem`   | Large body text              |
| `.text-xl`   | `1.25rem`  | `1.75rem`   | Small headings               |
| `.text-2xl`  | `1.5rem`   | `2rem`      | Card titles, section headers |
| `.text-3xl`  | `1.875rem` | `2.25rem`   | Page section titles          |
| `.text-4xl`  | `2.25rem`  | `2.5rem`    | Hero subtitles               |
| `.text-5xl`  | `3rem`     | `1`         | Hero titles, major headings  |
| `.text-6xl`  | `3.75rem`  | `1`         | Large display text           |
| `.text-7xl`  | `4.5rem`   | `1`         | Extra large display          |
| `.text-8xl`  | `6rem`     | `1`         | Maximum impact display       |
| `.text-9xl`  | `8rem`     | `1`         | Special use cases            |

### Font Weight Classes

| Class            | Weight | Usage           |
| ---------------- | ------ | --------------- |
| `.font-normal`   | `400`  | Regular text    |
| `.font-medium`   | `500`  | Medium emphasis |
| `.font-semibold` | `600`  | Semi-bold text  |
| `.font-bold`     | `700`  | Bold headings   |

### Orbitron Font Classes

| Class                | Weight  | Usage                  |
| -------------------- | ------- | ---------------------- |
| `.font-orbitron`     | Default | General Orbitron usage |
| `.font-orbitron-400` | `400`   | Light Orbitron         |
| `.font-orbitron-500` | `500`   | Medium Orbitron        |
| `.font-orbitron-600` | `600`   | Semi-bold Orbitron     |
| `.font-orbitron-700` | `700`   | Bold Orbitron          |

## Component Patterns

### Hero Section

- **Typography**: H1 with `.text-5xl`, Orbitron font
- **Colors**: Gradient text using Primary Text + Bright Accent
- **Layout**: Centered content with star decorations
- **Interactive**: CTA button with gradient background

### Navigation

- **Typography**: Company name in Orbitron `.text-4xl .font-semibold`
- **Colors**: Primary Text color
- **Layout**: Fixed header with theme toggle

### Call-to-Action (CTA)

- **Typography**: H3 headings, body text
- **Colors**: Bright Accent gradients, Primary Text
- **Layout**: Card-style with form elements
- **Interactive**: Gradient buttons with hover effects

### FAQ Section

- **Typography**: H2 headings with gradient text effects
- **Colors**: Bright Accent gradients, Primary Text
- **Layout**: Accordion-style expandable items
- **Interactive**: Click to expand/collapse

## Spacing System

### Standard Spacing Scale

- `0.25rem` (4px) - Minimal spacing
- `0.5rem` (8px) - Small spacing
- `0.75rem` (12px) - Compact spacing
- `1rem` (16px) - Base spacing
- `1.5rem` (24px) - Comfortable spacing
- `2rem` (32px) - Generous spacing
- `3rem` (48px) - Large spacing
- `4rem` (64px) - Extra large spacing

## Implementation Guidelines

### CSS Architecture

- **Colors**: Centralized in `src/styles/colors.css`
- **Typography**: Centralized in `src/styles/typography.css`
- **Components**: Use CSS variables for theming
- **Import Order**: Colors first, then typography, then components

### CSS Variables Usage

```css
/* Theme-aware colors */
--bg-color: var(--color-light-background); /* Light mode */
--bg-color: var(--color-dark-background); /* Dark mode */

/* Direct color usage */
color: var(--color-primary-text);
background: var(--color-bright-accent);
```

### Component Styling

```astro
---
// Import styles in frontmatter
import '../styles/colors.css';
import '../styles/typography.css';
---

<div class="component">
  <h1 class="font-orbitron text-5xl">Title</h1>
  <p class="text-base">Body text with system fonts</p>
  <button class="cta-button">Action</button>
</div>

<style>
  .component {
    color: var(--color-primary-text);
    background: var(--bg-color);
  }

  .cta-button {
    background: linear-gradient(45deg, var(--color-primary-accent), var(--color-bright-accent));
  }
</style>
```

## Accessibility Guidelines

### Color Contrast

- **Normal text**: Minimum 4.5:1 contrast ratio
- **Large text**: Minimum 3:1 contrast ratio
- **Interactive elements**: Minimum 3:1 contrast ratio

### Typography

- **Line height**: Minimum 1.5 for body text
- **Font size**: Minimum 16px for body text
- **Readable fonts**: System font stack prioritizes readability

### Focus States

- **Visible focus**: Use Bright Accent for focus rings
- **Keyboard navigation**: All interactive elements keyboard accessible
- **Screen readers**: Semantic HTML with proper ARIA labels

## Dark Mode Implementation

### Automatic Theme Switching

- CSS variables automatically switch based on `.dark` class
- No manual color overrides needed in components
- Consistent theming across light and dark modes

### Dark Mode Colors

- **Backgrounds**: Dark Background (#1a1a1a)
- **Text**: Light Background (#ffffff)
- **Borders**: Dark Border (#374151)
- **Accents**: Bright Accent (#00c0fc) for visibility

## Performance Considerations

### Font Loading

- **Google Fonts**: Preconnect optimization
- **System fonts**: Zero-latency loading
- **Font subset**: Only necessary weights loaded

### CSS Optimization

- **CSS variables**: Runtime theming without rebuild
- **Import strategy**: ES6 imports for reliable loading
- **Minimal CSS**: Utility-first approach reduces bundle size

## Maintenance

### Adding New Colors

1. Add to `content/color-palette.md`
2. Add CSS variable to `src/styles/colors.css`
3. Update usage documentation

### Adding New Typography

1. Add utility class to `src/styles/typography.css`
2. Document in this guide
3. Test across components

### Component Updates

- Use existing CSS variables and utility classes
- Maintain consistency with established patterns
- Update this guide when introducing new patterns

## Logo Usage Guidelines

### Logo Variations

- **Primary Logo**: Full color version for light backgrounds
- **White Logo**: For dark backgrounds
- **Icon Only**: Circular logo for favicons, app icons, social media profiles

### Clear Space

Maintain a clear space around the logo equivalent to the height of the "H" in "HC" to ensure visual separation.

### Minimum Size

- **Digital**: 32px height minimum
- **Print**: Not applicable (digital-only company)
- **Social Media**: 200px height minimum for profile images

### Color Variations

- **Full Color**: Use on white/light backgrounds
- **Monochrome**: Black logo for documents, white for dark backgrounds
- **Accent**: Cyan accent version for special uses

### Prohibited Uses

- Don't modify the logo design or proportions
- Don't place on busy backgrounds that reduce readability
- Don't use as a watermark or background pattern
- Don't combine with other logos or graphics

## Email Branding Guidelines

### Email Signature Template

```html
<div style="font-family: system-ui, sans-serif; color: #000080;">
  <strong>Hendrik Crause</strong><br>
  Founder & Lead Data Engineer<br>
  HC Scaling Solutions<br>
  <a href="mailto:info@hcscalingsolutions.com" style="color: #00c0fc;">info@hcscalingsolutions.com</a><br>
  <a href="https://hcscalingsolutions.com" style="color: #00c0fc;">hcscalingsolutions.com</a>
</div>
```

### Email Templates

- **Header**: Use Orbitron font for company name, primary color
- **Body**: System font stack, primary text color
- **CTAs**: Bright accent buttons with gradient backgrounds
- **Footer**: Include unsubscribe link, contact info, social links

### Best Practices

- Use inline CSS for email client compatibility
- Test across Gmail, Outlook, Apple Mail
- Keep images under 1MB total
- Include alt text for images
- Use web-safe fonts with fallbacks

## Brand Voice & Tone

### Voice Characteristics

- **Professional**: Technical expertise with approachable language
- **Confident**: Demonstrate deep knowledge without arrogance
- **Helpful**: Focus on solving client problems
- **Direct**: Clear, concise communication

### Tone Guidelines

- **Website**: Authoritative yet accessible, use "we" and "you"
- **Emails**: Personal and professional, warm but not casual
- **Social Media**: Educational and engaging, share insights
- **Client Communications**: Solution-focused, build trust

### Language Style

- Use active voice
- Avoid jargon or explain technical terms
- Short sentences for web, longer for detailed content
- Positive, forward-looking language

## Photography & Imagery Guidelines

### Style Preferences

- **Clean & Modern**: Minimalist compositions, plenty of white space
- **Tech-Focused**: Data visualizations, servers, clean workspaces
- **Professional**: High-quality, well-lit images
- **Diverse**: Show different industries and team compositions

### Image Treatment

- **Filters**: Slight desaturation for tech images
- **Colors**: Incorporate brand colors where natural
- **Composition**: Rule of thirds, balanced layouts
- **Editing**: Subtle adjustments only, maintain authenticity

### Usage Guidelines

- **Hero Images**: Abstract tech patterns, data visualizations
- **Team Photos**: Professional headshots, diverse representation
- **Backgrounds**: Subtle patterns, gradients using brand colors
- **Icons**: Flat design, consistent with logo style

## Iconography Guidelines

### Icon Style

- **Design**: Flat, geometric shapes inspired by logo
- **Colors**: Primary colors, accent for highlights
- **Weight**: 2px stroke, consistent across all icons
- **Size**: Scalable SVG format, 24px base size

### Icon Library

- **Technology**: Database, cloud, pipeline icons
- **Business**: Growth, analytics, consulting icons
- **Navigation**: Menu, arrow, search icons
- **Social**: LinkedIn, Twitter, GitHub icons

### Usage Rules

- Maintain consistent stroke width and corner radius
- Use brand colors for primary icons
- Neutral colors for secondary elements
- Ensure 24px minimum touch targets for accessibility

## Social Media Branding

### Profile Setup

- **Profile Picture**: Icon-only logo (circular)
- **Cover/Banner**: Gradient using primary and accent colors
- **Bio**: "Scaling data infrastructure for growing businesses | Data Engineering Consulting"
- **Handle**: @hcscalingsolutions

### Content Types

- **Educational Posts**: Data engineering tips, industry insights
- **Case Studies**: Client success stories (anonymized)
- **Thought Leadership**: Articles, threads on scaling challenges
- **Engagement**: Questions, polls about data challenges

### Visual Guidelines

- **Graphics**: Use brand colors, Orbitron for headings
- **Hashtags**: #DataEngineering #ScalingSolutions #TechConsulting
- **Posting Schedule**: 3-5 posts per week
- **Engagement**: Respond within 24 hours

### Platform-Specific

- **LinkedIn**: Professional networking, article shares
- **Twitter**: Industry news, quick tips
- **GitHub**: Code samples, open-source contributions

## Brand Assets Library

### File Organization

```
branding/
├── logo/
│   ├── hc-logo.svg (primary)
│   ├── hc-logo-white.svg
│   ├── hc-logo-icon.svg
│   └── variants/ (color variations)
├── fonts/
│   ├── orbitron.woff2
│   └── system-fonts.css
├── icons/
│   ├── technology/
│   ├── business/
│   └── social/
├── templates/
│   ├── email-signatures/
│   ├── social-media/
│   └── presentations/
└── guidelines/
    ├── design-guide.md
    └── color-palette.md
```

### Naming Conventions

- **Logos**: `hc-logo-[variant]-[size].[ext]`
- **Icons**: `icon-[category]-[name].svg`
- **Templates**: `template-[type]-[name].[ext]`
- **Images**: `img-[type]-[description]-[size].[ext]`

### File Formats

- **Logos**: SVG preferred, PNG for web use
- **Icons**: SVG for scalability
- **Fonts**: WOFF2 for web, with fallbacks
- **Templates**: Native formats with PDF exports

### Version Control

- Store in Git repository under `/branding/`
- Use semantic versioning for major updates
- Document changes in commit messages
- Tag releases for brand updates</content>
  <parameter name="filePath">content/design-guide.md
