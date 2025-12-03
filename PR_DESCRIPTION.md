# Add Mobile-First Documentation to CLAUDE.md

## Summary
Enhances CLAUDE.md with comprehensive mobile-first development guidelines. Insurance clients primarily access this site from mobile devices, so this ensures AI assistants always prioritize mobile users.

## What Changed

### New "Mobile-First Design Principles" Section
- Mobile-first philosophy and progressive enhancement approach
- Breakpoint guide (mobile default → tablet → desktop → large)
- 5 mobile-specific features with code examples
- Mobile testing requirements (viewport, menus, forms, phone links, touch targets)
- Development workflow (mobile → tablet → desktop, never reverse)
- Common pitfalls to avoid

### Enhanced "Important Constraints"
**Added DO NOTs:**
- Remove/modify viewport meta tag
- Break mobile-first responsive patterns
- Add hover-only interactions without touch alternatives
- Test only on desktop

**Added ALWAYS:**
- Test on mobile devices FIRST, then desktop
- Verify touch interactions work correctly
- Start with mobile styles, add desktop enhancements

### Enhanced "Testing & Validation"
- Separated mobile testing checklist (11 items, REQUIRED)
- Desktop testing checklist (8 items, after mobile)
- Browser priority: Mobile Safari → Mobile Chrome → Desktop browsers
- Mobile performance metrics (FCP < 1.8s on 3G)

### Enhanced "Notes for AI Assistants"
- 7-point mobile-first development checklist
- Touch-first interaction mindset
- Real device testing emphasis

## Stats
- **192 lines added** (349 → 541 total)
- **83 mobile/responsive/touch references** throughout
- **No code changes** - documentation only

## Impact
Future development will automatically prioritize:
- Mobile experiences over desktop
- Touch interactions over hover states
- Real device testing over DevTools
- Performance on mobile networks

---

**Ready to merge** - Documentation only, no impact on live site.
