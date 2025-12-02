# CLAUDE.md - AI Assistant Guide for AnnMarieB-Landing

## Project Overview

**AnnMarieB-Landing** is a professional landing page for AnnMarie Barrell, a licensed insurance agent at Legacy Agency of the Fingerlakes in Waterloo, NY. This is a single-page web application built with modern web technologies, designed to showcase insurance services and provide an easy way for potential clients to get in touch.

### Quick Facts
- **Type**: Static landing page
- **Primary File**: `index.html`
- **Technology**: HTML5, TailwindCSS, Vite
- **Repository**: https://github.com/bbold-bb/AnnMarieB-Landing
- **Target Audience**: Local residents and businesses in the Finger Lakes region seeking insurance services

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

### ALWAYS
- Read files before editing
- Preserve existing indentation and formatting
- Test responsive behavior when changing layouts
- Include descriptive commit messages
- Push to designated feature branches with `-u` flag
- Maintain brand consistency (colors, fonts, tone)
- Keep the single-page structure (no multi-page navigation)

## Testing and Validation

### Manual Testing Checklist
- [ ] All links work (external and anchor links)
- [ ] Mobile menu toggles correctly
- [ ] Form submits to Netlify (check Netlify dashboard)
- [ ] Responsive design works at all breakpoints
- [ ] Images load correctly
- [ ] Icons display properly
- [ ] Phone number links work on mobile
- [ ] Hover states function correctly

### Browser Testing
- Chrome/Edge (primary)
- Firefox
- Safari (especially mobile Safari for iOS users)
- Mobile devices (actual devices preferred over DevTools)

### Performance
- Minimize custom CSS (leverage Tailwind utilities)
- Images optimized and properly sized
- CDN resources load reliably (Tailwind, Font Awesome, Google Fonts)

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

### Working Style
- Read files thoroughly before suggesting changes
- Provide specific line numbers when referencing code
- Explain reasoning for architectural decisions
- Ask clarifying questions before making significant changes
- Preserve existing patterns and conventions
- Test responsive behavior for all changes

### Communication
- Be concise and specific
- Use markdown for code examples
- Reference file paths and line numbers
- Explain trade-offs when multiple solutions exist
- Confirm understanding of requirements before implementing

---

**Last Updated**: 2025-12-02
**Repository**: https://github.com/bbold-bb/AnnMarieB-Landing
**Maintained By**: AI assistants working with project stakeholders
