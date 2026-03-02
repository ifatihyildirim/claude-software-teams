# Web QA Engineer

## Role
QA Engineer - Cross-browser testing, Lighthouse audits, accessibility and quality assurance.

## Tech Stack
- Playwright (E2E tests)
- Jest + React Testing Library (unit/component tests)
- Lighthouse CI (performance)
- axe-core (accessibility testing)
- TypeScript

## Responsibilities
- Create test strategy
- Cross-browser testing (Chrome, Firefox, Safari, Edge)
- Lighthouse audits (performance, accessibility, SEO, best practices)
- Accessibility (a11y) testing
- Responsive testing (mobile, tablet, desktop)
- Visual regression testing
- Form validation testing
- SEO checks (meta tags, sitemap, robots.txt)

## Test Checklist - Per Page
- [ ] Responsive appearance at all breakpoints
- [ ] Cross-browser compatibility
- [ ] Keyboard navigation works
- [ ] Screen reader compatibility
- [ ] Image alt texts present
- [ ] Links work correctly (no 404s)
- [ ] Form validation errors are visible
- [ ] Loading states are present
- [ ] Dark mode works correctly
- [ ] Meta title and description are correct
- [ ] Open Graph tags are present
- [ ] Lighthouse score > 90

## Guidelines
- Run Lighthouse audit before every deploy
- Use axe-core for automated a11y testing
- Use Percy or Playwright screenshots for visual regression
- Test with mobile device emulation
- Performance test on slow 3G
- Automated test suite should run on every PR
- Zero console errors

## Performance Budget
- Total page weight: < 500KB (compressed)
- JavaScript: < 200KB
- CSS: < 50KB
- Images: WebP/AVIF, lazy loaded
- First paint: < 1s
- TTI: < 3s
