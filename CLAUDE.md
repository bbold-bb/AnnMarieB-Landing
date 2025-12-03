# CLAUDE.md - AI Assistant Guide for AnnMarieB-Landing

## Project Overview

**AnnMarieB-Landing** is a professional landing page for AnnMarie Barrell, a licensed insurance agent at Legacy Agency of the Fingerlakes in Waterloo, NY. This is a single-page web application built with modern web technologies, designed to showcase insurance services and provide an easy way for potential clients to get in touch.

### Quick Facts
- **Type**: Static landing page
- **Primary File**: `index.html`
- **Technology**: HTML5, TailwindCSS, Vite
- **Design Philosophy**: Mobile-first, touch-optimized
- **Repository**: https://github.com/bbold-bb/AnnMarieB-Landing
- **Target Audience**: Local residents and businesses in the Finger Lakes region seeking insurance services (primarily mobile users)

## Repository Structure

```
AnnMarieB-Landing/
├── index.html              # Main landing page (single-page application)
├── package.json           # NPM dependencies and scripts
├── package-lock.json      # Locked dependency versions
├── .gitignore            # Git ignore rules (node_modules, dist, .env, .DS_Store)
├── GitHub.code-workspace # VS Code workspace configuration
└── CLAUDE.md             # This file - AI assistant guide
```

### Key Files

#### `index.html` (342 lines)
The entire application in a single, well-structured HTML file containing:
- Navigation bar with mobile-responsive menu
- Hero section with agent profile and call-to-action
- About section explaining the agency's value proposition
- Services section showcasing insurance offerings (Auto, Home, Business, Recreation)
- Contact section with contact form and business information
- Footer with copyright and links

**Notable Sections**:
- Lines 1-38: HTML head with meta tags, CDN imports (Tailwind, Font Awesome), and custom styles
- Lines 10-37: Custom CSS defining Legacy Agency brand colors and typography
- Lines 40-81: Fixed navigation with mobile menu
- Lines 83-138: Hero section with profile image and CTAs
- Lines 140-173: About section highlighting personal service
- Lines 175-225: Services grid
- Lines 227-321: Contact section with Netlify form integration
- Lines 323-338: Footer

#### `package.json`
- **Scripts**:
  - `npm run dev` - Start Vite development server
  - `npm run build` - Build production bundle
  - `npm test` - Not yet implemented
- **DevDependencies**: Vite v7.2.4

## Technology Stack

### Core Technologies
- **HTML5**: Semantic markup
- **CSS3**: Custom styles + utility framework
- **TailwindCSS v3.x**: Utility-first CSS framework (via CDN)
- **Font Awesome 6.0**: Icon library (via CDN)
- **Google Fonts**: Lato font family (300, 400, 700, 900 weights)

### Build Tools
- **Vite 7.2.4**: Modern build tool and dev server
- **Node.js/NPM**: Package management

### Deployment
- **Netlify Forms**: Contact form integration (data-netlify="true" on form element)
- Static hosting ready (designed for Netlify, but platform-agnostic)

## Brand Design System

### Color Palette
The site uses a professional insurance industry color scheme:
- **Navy Blue** (`#0f2b4c`): Primary brand color - `.bg-legacy-navy`, `.text-legacy-navy`
- **Gold** (`#c5a059`): Accent color - `.bg-legacy-gold`, `.text-legacy-gold`
- **Gray Scale**: Tailwind's default gray palette for text and backgrounds

### Typography
- **Font Family**: Lato (sans-serif)
- **Weights**: 300 (light), 400 (regular), 700 (bold), 900 (black)
- **Hierarchy**: Clear heading scales using Tailwind utilities

### Icons
- Font Awesome 6.0 icons used throughout
- Shield icon for brand identity
- Service-specific icons (car, house, store, sailboat)

## Mobile-First Design Principles

**CRITICAL**: This site is designed with a mobile-first approach. The majority of insurance clients will access this site from their phones, especially when searching for local agents or calling for quotes.

### Mobile-First Philosophy
- **Default styling is for mobile** - All base styles target mobile devices first
- **Progressive enhancement** - Desktop features are added via Tailwind breakpoints (`sm:`, `md:`, `lg:`)
- **Touch-first interactions** - All clickable elements sized for finger taps (minimum 44x44px)
- **Performance matters** - Fast load times on mobile networks are essential

### Mobile Breakpoints
```
Mobile (default):  < 640px  - Base styles, single column layouts
Tablet (sm:):      640px+   - Minor adjustments
Desktop (md:):     768px+   - Multi-column layouts, desktop nav
Large (lg:):       1024px+  - Maximum width constraints, enhanced spacing
```

### Mobile-Specific Features

#### 1. Mobile Navigation (Lines 40-81)
- **Hamburger menu** for mobile devices (< 768px)
- **Fixed position** navbar stays accessible while scrolling
- **Touch-friendly** tap targets with adequate spacing
- **Animated toggle** via simple JavaScript onclick handler

#### 2. Responsive Grid Patterns
The site uses mobile-first grid patterns:
```html
<!-- Services: 2 columns on mobile, 4 on desktop -->
<div class="grid grid-cols-2 md:grid-cols-4 gap-6">

<!-- About: Stacked on mobile, 3 columns on desktop -->
<div class="grid grid-cols-1 md:grid-cols-3 gap-8">

<!-- Contact: Stacked on mobile, 2 columns on desktop -->
<div class="grid grid-cols-1 lg:grid-cols-2 gap-16">
```

#### 3. Touch-Optimized CTAs
- **Phone number buttons** with `tel:` links for one-tap calling
- **Large tap targets** (px-8 py-4) on all primary buttons
- **Clear visual feedback** with hover/active states
- **Finger-friendly spacing** between interactive elements

#### 4. Mobile-Optimized Typography
- **Responsive text sizing**: `text-4xl lg:text-6xl` pattern
- **Readable line lengths** with max-width constraints
- **Adequate line height** for comfortable reading on small screens
- **Scalable font sizes** that work across all device sizes

#### 5. Mobile Performance
- **CDN-hosted assets** (Tailwind, Font Awesome, Google Fonts) for fast delivery
- **Minimal JavaScript** - Only ~5 lines for mobile menu toggle
- **No external images** except profile photo (optimized via LinkedIn CDN)
- **Single HTML file** - No additional HTTP requests for CSS/JS

### Mobile Testing Requirements

When making ANY changes to the site, you MUST verify:

1. **Viewport Meta Tag** (Line 6): Never remove or modify
   ```html
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   ```

2. **Mobile Menu Functionality**:
   - Toggle opens/closes smoothly
   - Links are easily tappable
   - Menu closes when selecting an anchor link

3. **Form Usability on Mobile**:
   - Input fields are easy to tap and type in
   - Form fits within viewport (no horizontal scrolling)
   - Submit button is prominent and tappable
   - Keyboard doesn't obscure form fields

4. **Phone Number Links**:
   - All phone numbers use `tel:` protocol
   - Format: `href="tel:3152208169"` (no spaces or hyphens in href)
   - Display format can be pretty: (315) 220-8169

5. **Text Readability**:
   - No text smaller than 14px on mobile
   - Adequate contrast ratios (WCAG AA minimum)
   - Line lengths don't exceed 75 characters on mobile

6. **Touch Target Sizes**:
   - Buttons minimum 44x44px (iOS guidelines)
   - Links have adequate padding for tap accuracy
   - Spacing between tappable elements (at least 8px)

### Mobile-First Development Workflow

When adding or modifying features:

```bash
# 1. Start with mobile styles (no breakpoint prefix)
class="text-lg px-4 py-2"

# 2. Add tablet adjustments if needed (sm:)
class="text-lg sm:text-xl px-4 py-2"

# 3. Add desktop enhancements (md:, lg:)
class="text-lg sm:text-xl md:text-2xl px-4 py-2 lg:px-6 lg:py-3"

# NEVER start with desktop styles and work down!
```

### Common Mobile Pitfalls to AVOID

❌ **Don't**:
- Use fixed pixel widths that don't scale
- Rely on hover states for critical interactions
- Use small tap targets (< 44x44px)
- Create horizontal scrolling on mobile
- Use viewport units (vw/vh) without thorough testing
- Forget to test on actual mobile devices
- Add desktop-only features without mobile alternatives

✅ **Do**:
- Test on real mobile devices, not just DevTools
- Use Tailwind's responsive utilities
- Provide touch-friendly alternatives to hover effects
- Ensure all content is accessible without horizontal scroll
- Use relative units (rem, em, %) for flexible layouts
- Test on slow mobile networks (3G simulation)
- Verify iOS Safari AND Android Chrome compatibility

## Development Workflow

### Getting Started
```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build
```

### Development Server
- Vite serves the application on localhost (typically port 5173)
- Hot module replacement (HMR) enabled
- Fast refresh on file changes

### Production Build
- Output directory: `dist/` (gitignored)
- Optimized and minified assets
- Ready for static hosting deployment

## Git Workflow

### Branch Strategy
- **Feature Branches**: Named with `claude/` prefix followed by descriptive name and session ID
- **Current Branch**: `claude/claude-md-miowhfsppjm8qwvn-01D3VQUqcyh8SQZmMvUraaN9`
- **Remote**: Origin at GitHub (bbold-bb/AnnMarieB-Landing)

### Commit Message Conventions
Based on commit history, the project follows conventional commits style:
- `feat:` - New features
- `refactor:` - Code improvements without functional changes
- Use descriptive, concise messages
- Examples from history:
  - `feat: Initialize project with package.json, .gitignore, and Vite for development setup.`
  - `refactor: improve HTML and CSS formatting for readability`

### Git Commands for AI Assistants
```bash
# Always push to feature branches with -u flag
git push -u origin <branch-name>

# Fetch specific branches
git fetch origin <branch-name>

# Check status before committing
git status
git diff
```

## Code Style and Conventions

### HTML
- **Indentation**: 4 spaces
- **Comments**: Section headers for major page sections
- **Semantic HTML**: Proper use of `<header>`, `<nav>`, `<section>`, `<footer>`
- **Accessibility**: Alt text, semantic markup, focus states
- **Mobile-First**: Responsive design with mobile menu and breakpoints

### CSS
- **Utility-First**: Prefer Tailwind utilities over custom CSS
- **Custom Classes**: Only for brand-specific colors and repeated patterns
- **Naming**: BEM-inspired for custom classes (e.g., `.bg-legacy-navy`)
- **Responsive**: Use Tailwind breakpoints (`sm:`, `md:`, `lg:`)

### JavaScript
- Minimal JavaScript (only for mobile menu toggle)
- Inline event handlers for simplicity
- No external JS files currently

## Key Features and Components

### 1. Navigation Bar
- Fixed position with shadow
- Responsive with mobile hamburger menu
- Logo links to main agency website
- CTA button for "Get a Quote"

### 2. Hero Section
- Split layout with text and profile image
- Two CTAs: Contact form and phone number
- Background pattern with SVG
- Profile image loaded from LinkedIn CDN
- Experience badge overlay

### 3. About Section
- Three-column grid of value propositions
- Icons with hover effects
- Centered content with max-width constraint

### 4. Services Section
- Four-column grid (2x2 on mobile)
- Icon-based cards with hover states
- Categories: Auto, Home, Business, Recreation

### 5. Contact Section
- Two-column layout: info and form
- Contact methods: Phone, LinkedIn, Physical address
- Netlify form integration with spam protection
- Form fields: name, email/phone, message

### 6. Footer
- Agency branding and copyright
- Link to main agency website

## Common Tasks for AI Assistants

### Content Updates
When updating content in `index.html`:
1. Read the entire file first to understand context
2. Locate the specific section using HTML comments
3. Preserve indentation (4 spaces)
4. Maintain Tailwind class order (layout → spacing → colors → typography → effects)
5. Test responsive behavior across breakpoints

### Styling Changes
1. Check if Tailwind utility exists before adding custom CSS
2. Custom brand colors are defined in `<style>` tag (lines 10-37)
3. Maintain consistency with existing color scheme
4. Use existing custom classes: `.bg-legacy-navy`, `.text-legacy-gold`, etc.

### Form Modifications
The contact form (lines 286-317) uses Netlify Forms:
- **Required attributes**: `name="contact"`, `method="POST"`, `data-netlify="true"`
- **Hidden field**: `<input type="hidden" name="form-name" value="contact" />`
- Each input needs `name` attribute for Netlify to capture data
- Do NOT change to `mailto:` action or remove Netlify attributes

### Adding New Sections
1. Follow existing section structure: `<section id="..." class="py-20">`
2. Use max-width container: `<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">`
3. Add section to navigation if needed
4. Maintain alternating background colors (white/gray-50)

### Responsive Design
- Test at breakpoints: mobile (default), `sm:` (640px), `md:` (768px), `lg:` (1024px)
- Mobile menu: `hidden md:flex` pattern for desktop-only elements
- Grid layouts: Use `grid-cols-1 md:grid-cols-2 lg:grid-cols-3` pattern

## Important Constraints

### DO NOT
- Remove or modify Netlify form attributes
- Change brand colors without explicit approval
- Add external dependencies without using package.json
- Commit `node_modules/`, `dist/`, `.env`, or `.DS_Store` files
- Push directly to main branch (use feature branches)
- Use inline JavaScript beyond simple event handlers
- Remove accessibility features (alt text, semantic HTML, focus states)
- **Remove or modify the viewport meta tag**
- **Break mobile-first responsive patterns**
- **Add hover-only interactions without touch alternatives**
- **Use fixed widths that don't scale on mobile**
- **Create elements smaller than 44x44px tap targets**
- **Test only on desktop - mobile testing is MANDATORY**

### ALWAYS
- Read files before editing
- Preserve existing indentation and formatting
- **Test on mobile devices FIRST, then desktop**
- **Verify touch interactions work correctly**
- **Ensure no horizontal scrolling on mobile**
- **Test phone number links on actual mobile devices**
- Include descriptive commit messages
- Push to designated feature branches with `-u` flag
- Maintain brand consistency (colors, fonts, tone)
- Keep the single-page structure (no multi-page navigation)
- **Start with mobile styles, then add desktop enhancements**

## Testing and Validation

### Mobile-First Testing Checklist

**CRITICAL**: Always test on mobile FIRST, then verify desktop. The majority of users will access this site on mobile devices.

#### Mobile Testing (REQUIRED)
- [ ] **Viewport renders correctly** - No horizontal scrolling at 320px, 375px, 414px widths
- [ ] **Mobile menu works** - Opens/closes smoothly, all links tappable
- [ ] **Phone links work** - Tap to call functionality on iOS and Android
- [ ] **Form is usable** - Easy to tap inputs, keyboard doesn't hide submit button
- [ ] **Touch targets adequate** - All buttons/links minimum 44x44px
- [ ] **Text is readable** - No text smaller than 14px, good contrast
- [ ] **Images scale properly** - Profile photo displays correctly at all sizes
- [ ] **No fixed positioning issues** - Nav bar doesn't overlap content
- [ ] **Fast load time** - Tests on 3G network simulation
- [ ] **iOS Safari compatibility** - Tested on actual iPhone if possible
- [ ] **Android Chrome compatibility** - Tested on actual Android if possible

#### Desktop Testing (After Mobile)
- [ ] All links work (external and anchor links)
- [ ] Desktop navigation displays correctly (no hamburger menu)
- [ ] Multi-column layouts render properly
- [ ] Form submits to Netlify (check Netlify dashboard)
- [ ] Images load correctly
- [ ] Icons display properly
- [ ] Hover states function correctly
- [ ] Responsive breakpoints work (640px, 768px, 1024px)

#### Cross-Browser Testing Priority
1. **Mobile Safari (iOS)** - Primary mobile browser for insurance demographic
2. **Mobile Chrome (Android)** - Secondary mobile browser
3. **Desktop Chrome/Edge** - Primary desktop browsers
4. **Desktop Firefox** - Secondary desktop browser
5. **Desktop Safari** - macOS users

**Testing Tools**:
- Real devices (preferred): iPhone, Android phone
- Chrome DevTools device emulation (secondary)
- Responsive Design Mode in Firefox
- BrowserStack or similar (for comprehensive testing)

### Performance Testing

#### Mobile Performance Metrics
- **First Contentful Paint**: < 1.8s on 3G
- **Time to Interactive**: < 3.5s on 3G
- **Largest Contentful Paint**: < 2.5s
- **Cumulative Layout Shift**: < 0.1
- **Total Page Size**: < 1MB (currently ~200KB)

#### Optimization Checklist
- [ ] Minimize custom CSS (leverage Tailwind utilities)
- [ ] Images optimized and properly sized
- [ ] CDN resources load reliably (Tailwind, Font Awesome, Google Fonts)
- [ ] No render-blocking resources
- [ ] Efficient font loading (font-display: swap)
- [ ] Minimal JavaScript execution time

## Contact Information

### Agent Contact
- **Name**: AnnMarie Barrell
- **Phone**: (315) 220-8169
- **LinkedIn**: https://www.linkedin.com/in/annmariebarrell/
- **Office**: 59 Washington St, Waterloo, NY 13165

### Agency
- **Name**: Legacy Agency of the Fingerlakes
- **Website**: https://mylegacyins.com/
- **Quote System**: https://mylegacyins.com/online-insurance-quotes

## Project History

### Recent Commits
1. `4baef98` - Create GitHub.code-workspace
2. `4c527dc` - refactor: improve HTML and CSS formatting for readability
3. `e996723` - feat: Initialize project with package.json, .gitignore, and Vite for development setup
4. `91aec47` - Rename initialCommit to index.html
5. `d0f0e61` - Create initialCommit

### Evolution
- Started as a basic HTML file
- Added Vite for modern development workflow
- Integrated Netlify Forms for contact functionality
- Formatted for readability and maintainability

## Future Considerations

### Potential Enhancements
- Add Google Analytics or similar tracking
- Implement testimonials section
- Add FAQ section for common insurance questions
- Blog or resources section
- Photo gallery of local community involvement
- Integration with quote system API
- Multi-language support for diverse Finger Lakes community

### Technical Improvements
- Move from CDN to npm packages for Tailwind (better optimization)
- Add TypeScript for type safety if JavaScript grows
- Implement automated testing
- Set up CI/CD pipeline
- Add lighthouse CI for performance monitoring
- Progressive Web App (PWA) capabilities

## Notes for AI Assistants

### Context Awareness
- This is a professional business website for a real person and business
- Maintain professional tone in all content
- Insurance industry has specific regulations - avoid making claims or promises
- Local focus: Finger Lakes region, Waterloo, NY
- Personal touch is key - AnnMarie's direct relationship with clients is the main value prop
- **Mobile-first mindset**: Most insurance clients search on mobile while driving, at home, or during emergencies

### Working Style
- Read files thoroughly before suggesting changes
- Provide specific line numbers when referencing code
- Explain reasoning for architectural decisions
- Ask clarifying questions before making significant changes
- Preserve existing patterns and conventions
- **ALWAYS test mobile first, then desktop**
- **Think touch-first for all interactions**
- **Verify phone links work on actual mobile devices**

### Mobile-First Development Reminders
When implementing ANY feature or change:

1. **Start mobile, enhance desktop** - Never work backward from desktop to mobile
2. **Touch over hover** - Assume no mouse, design for fingers
3. **Test on real devices** - DevTools is for quick checks, not validation
4. **Performance matters** - Mobile users may have slow connections
5. **One-tap actions** - Phone calls, form submissions should be effortless
6. **Readable without zoom** - Text must be legible at default zoom level
7. **No horizontal scroll** - Content must fit in viewport at all widths

### Communication
- Be concise and specific
- Use markdown for code examples
- Reference file paths and line numbers
- Explain trade-offs when multiple solutions exist
- Confirm understanding of requirements before implementing
- **Always mention mobile testing in implementation plans**

---

**Last Updated**: 2025-12-03
**Repository**: https://github.com/bbold-bb/AnnMarieB-Landing
**Maintained By**: AI assistants working with project stakeholders
**Mobile-First**: This documentation emphasizes mobile-first development - always test on mobile devices first!
