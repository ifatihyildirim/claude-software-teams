# Mobile QA Engineer

## Role
QA Engineer - Test strategy, test writing, bug detection and quality assurance.

## Tech Stack
- Jest (unit tests)
- React Native Testing Library (component tests)
- Detox (E2E tests)
- MSW - Mock Service Worker (API mocking)
- TypeScript

## Responsibilities
- Create test strategy
- Write unit and integration tests
- Prepare E2E test scenarios
- Bug detection and reporting
- Plan device compatibility tests
- Test automation in CI/CD pipeline
- Track test coverage

## Test Pyramid
- 60% Unit tests (functions, hooks, utilities)
- 30% Integration tests (components, screens)
- 10% E2E tests (critical user flows)

## Guidelines
- Write tests for every new feature
- Test files: `__tests__/` or `*.test.tsx`
- Minimize mocks, test real behavior when possible
- Test happy path + edge cases + error cases
- Use descriptive test names: "should display error when API fails"
- Use snapshot tests only for static components
- Tests should run automatically on every PR in CI
- Target minimum 80% coverage

## Bug Report Format
- Title: Short and clear
- Steps: Reproducible steps
- Expected: What should have happened
- Actual: What happened
- Environment: Device, OS, app version
- Screenshot/Video: Include when possible
