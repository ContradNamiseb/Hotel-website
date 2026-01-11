## 2024-05-24 - [Skip Link Implementation]
**Learning:** Adding a "Skip to content" link is a high-impact, low-effort accessibility win for keyboard users.
**Action:** When working on pages with navigation bars, always check for a skip link. If missing, implement one that is hidden by default (`top: -40px`) and visible on focus (`top: 0`), pointing to the main content area (`id="main-content"`). ensure the contrast of the skip link meets WCAG AA standards (4.5:1) where possible, though design system constraints may sometimes force a trade-off (checked as acceptable in this specific context).

## 2024-05-24 - [Accessible Form Feedback]
**Learning:** Replacing `alert()` with inline, ARIA-live status messages significantly improves the user experience by maintaining context and not interrupting the workflow.
**Action:** For all future forms, use a dedicated status container with `aria-live="polite"` instead of browser alerts. Ensure success/error states have distinct visual styles (e.g., green/red backgrounds) and clear text.
## 2024-05-24 - [Navigation State Accessibility]
**Learning:** Visual indicators for "active" page states (like underlines) are invisible to screen readers.
**Action:** Always add `aria-current="page"` to the navigation link representing the current page. This standard attribute programmatically communicates the "active" state to assistive technologies, ensuring parity between visual and semantic information.

## 2024-05-24 - [Brand Color Contrast]
**Learning:** Brand colors (like Gold #d4a373) often fail contrast checks against white text.
**Action:** Don't default to white text on colored buttons. Always verify contrast ratios. In this case, switching to the brand's Dark Brown (#4a3728) for the text provided excellent contrast (4.97:1) while maintaining the visual identity, avoiding the need to muddy the gold color.

## 2024-05-24 - [Accessible Required Indicators]
**Learning:** Relying solely on the HTML5 `required` attribute is insufficient for visual users, but simply adding an asterisk can be redundant for screen readers if not handled carefully.
**Action:** Use a dual approach:
1. Add a visual indicator (e.g., `*`) wrapped in a span with `aria-hidden="true"` inside the label.
2. Provide a legend explaining the symbol (e.g., "Fields marked with * are required") where the symbol in the legend has `aria-label="asterisk"`.
This ensures visual clarity without cluttering the screen reader experience, as the input's `required` attribute handles the semantic announcement.
