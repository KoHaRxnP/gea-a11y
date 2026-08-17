# Contributing to gea-a11y

Thank you for your interest in contributing to `gea-a11y`! We welcome all contributions that help make accessibility and focus management in Gea simpler, lighter, and more reliable.

## Core Philosophies

Before opening an issue or a pull request, please keep our core tenets in mind:

1. **Zero Hooks**: We strictly adhere to Gea's Class-based, Object-Oriented design. Do not introduce functional components, hooks (`use~`), or implicit reactive magic.
2. **Zero Dependencies**: Keep the bundle size microscopic. Do not install external libraries without an extensive architectural debate.
3. **Explicit over Implicit**: Resource management (cleanups, event listeners, focus traps, dynamic `aria-live` regions) must be explicit and deterministic.

## Development Setup

We use `pnpm` and `tsup` for development and bundling.

```bash
# Clone the repository
git clone https://github.com/KoHaRxnP/gea-a11y
cd gea-a11y

# Install dependencies
pnpm install

# Run build in watch mode for development
pnpm build --watch

# Run tests
pnpm test

```

## Pull Request Guidelines

1. **Create a branch**: Use clear naming like `feat/feature-name` or `fix/bug-name`.
2. **Write clean TypeScript**: Adhere to the strict TypeScript rules already set in the project.
3. **Ensure No Memory Leaks**: If your feature introduces global listeners (`document`, `window`) or modifies the global `trapStack`, verify they are flawlessly cleaned up in the `destroy()` life cycle or via `_clearA11yGlobalState()`.
4. **Write Tests**: Ensure your changes are covered by unit tests using Vitest, especially for keyboard interactions, focus trapping, and nesting edge cases.
5. **Update Documentation**: If you modify the API, update `README.md` accordingly.

## Code of Conduct

Be respectful, collaborative, and focused on maintaining high-quality code. Let's build the best accessibility ecosystem for Gea together!