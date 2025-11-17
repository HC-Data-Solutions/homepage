# Agent Guidelines for HC Data Solutions Homepage

## Commands

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run lint` - Run ESLint (auto-fix with `--fix`)
- `npm run format` - Format with Prettier (check with `--check`)
- No test framework configured

## Code Style

- **Framework**: Astro with React integration, TypeScript strict mode
- **Naming**: PascalCase components, kebab-case CSS classes/variables, camelCase utilities
- **Imports**: Relative paths for local files, group external libs first
- **Styling**: CSS-in-JS in `<style>` blocks, CSS custom properties for themes, `:global()` for globals
- **Formatting**: 2-space indent, single quotes, semicolons, trailing commas ES5, 100 char width
- **TypeScript**: Strict typing, no `any`, unused vars prefixed with `_` ignored
- **Icons**: Import from `@phosphor-icons/react`
- **Pre-commit**: Husky + lint-staged auto-formats and lints
