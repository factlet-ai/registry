# Example: react-frontend-conventions

A sanitized Factbook for a React + TypeScript frontend project.

## What this example illustrates

- **Stack-level decisions** (f001, f002): TanStack Query is in, Redux is out. An AI without this fact will happily generate a Redux slice. f002 captures the negative — "we explicitly retired Redux" — which is just as important as the positive.
- **Type-safety conventions** (f003): typed event handlers. Tiny but a constant friction point in code review.
- **Accessibility floor** (f004): aria-label requirement. Audit fails enforce this.
- **Styling discipline** (f005): Tailwind only, no custom CSS. AI suggestions to "add a stylesheet for X" should be rejected.
- **Form pattern** (f006): React Hook Form + Zod, not raw state. AI generating onChange handlers misses the validation layer.
- **Performance budgets** (f007, f008): bundle size and image components. AI suggesting `<img>` tags or unbounded imports trips CI.

## How to use

Copy `frontend-factbook.yaml` and ask:

- "Add a global state for current user." (Should cite f001/f002 and use Zustand or TanStack, not Redux.)
- "Build a contact form." (Should cite f006 — RHF + Zod schema.)
- "Style this card with a custom CSS file." (Should cite f005 and refuse, propose Tailwind classes instead.)

## Adapt to your project

Fill in your actual ADR references, eslint config paths, and CI scripts. The pattern of "we use X, we explicitly retired Y" is high-leverage — capture both sides.
