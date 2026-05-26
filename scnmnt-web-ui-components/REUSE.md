# scnmnt-web-ui-components — reusability notes

**Type:** `library`

## What the consumer must change to use this elsewhere

This capsule relies on a Tailwind CSS setup and `shadcn/ui` conventions. The `components.json` file defines aliases and styling configuration specific to `shadcn/ui` which would need to be adapted if moving to a different UI library or setup. `global.css` contains base styles that are part of the design system.

## Invariants you must not break

- All components must be accessible and responsive.
- Components must adhere to the established design tokens and visual style.
