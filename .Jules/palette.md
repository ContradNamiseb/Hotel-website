## 2024-05-24 - [Skip Link Implementation]
**Learning:** Adding a "Skip to content" link is a high-impact, low-effort accessibility win for keyboard users.
**Action:** When working on pages with navigation bars, always check for a skip link. If missing, implement one that is hidden by default (`top: -40px`) and visible on focus (`top: 0`), pointing to the main content area (`id="main-content"`). ensure the contrast of the skip link meets WCAG AA standards (4.5:1) where possible, though design system constraints may sometimes force a trade-off (checked as acceptable in this specific context).

## 2024-05-24 - [Accessible Form Feedback]
**Learning:** Replacing `alert()` with inline, ARIA-live status messages significantly improves the user experience by maintaining context and not interrupting the workflow.
**Action:** For all future forms, use a dedicated status container with `aria-live="polite"` instead of browser alerts. Ensure success/error states have distinct visual styles (e.g., green/red backgrounds) and clear text.
