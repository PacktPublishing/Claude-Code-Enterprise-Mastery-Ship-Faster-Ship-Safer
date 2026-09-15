# Package: Web (Frontend)

## Structure
- Components: `src/components/` — React functional components
- Hooks: `src/hooks/` — Custom React hooks
- Pages: `src/pages/` — Route-level components
- Styles: Tailwind CSS utility classes

## Conventions
- React functional components ONLY — no class components
- Components under 150 lines — extract sub-components if larger
- Custom hooks in `hooks/` directory with `use` prefix
- Tailwind CSS for all styling — no inline styles or CSS modules
- Props must have TypeScript interfaces defined

## State Management
- Local state: useState for component-level
- Shared state: [Context / Zustand / Redux — specify yours]
- API calls: [React Query / SWR / custom hooks — specify yours]

## Testing
- Component tests with React Testing Library
- Run: `npm test --workspace=packages/web`
