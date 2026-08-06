# Portfolio design QA

Date: 2026-08-07

## Reference and implementation

- Selected direction: systems portfolio proposal 2.
- Reference preview: `http://127.0.0.1:8765/outputs/previews/systems-portfolio.html`.
- Implementation: `http://127.0.0.1:8765/work/portfolio-source/docs/index.html`.
- State checked: initial page state at the top of the page.

The implementation follows the selected dark systems direction with a profile rail, oversized hero, numbered content sections, compact project rows, monospace labels, restrained borders, and pill-shaped actions. The profile-level GitHub address and GitHub profile action were removed after approval because project repository links already provide the relevant code paths.

## Viewports checked

- Desktop: 1440 x 900.
- Tablet: 1024 x 768.
- Mobile: 390 x 844.

## Checks

- Composition and spacing: passed. The profile, hero, selected work, focus, background, toolchain, and contact sections retain the selected hierarchy.
- Typography and color: passed. The implementation uses the selected high-contrast dark palette, large sans-serif hero type, muted body copy, and green monospace labels without decorative excess.
- Content fidelity: passed. Project descriptions, technologies, experience, education, and contact links use information present in the repository. Copy was tightened without adding results or achievements.
- Responsive behavior: passed. The browser reported no horizontal overflow at any checked viewport. The layout changes from two columns to a stacked mobile flow.
- Navigation: passed. All internal fragments resolve. The selected work and contact actions moved to their expected sections during browser interaction.
- Accessibility basics: passed. The page has a skip link, a single h1 followed by ordered h2 and h3 headings, semantic regions, English document language, descriptive link text, `rel="noreferrer"` on external links, visible `:focus-visible` styling, and a reduced-motion rule. The page has no images, so no alt text is required.
- Browser console: passed. No errors or warnings were reported during the checked states.
- Asset surface: passed. The page does not depend on image assets, inventory data, filter scripts, or external UI libraries.

## Link checks

- The three project repository links returned HTTP 200 from GitHub with a HEAD request.
- LinkedIn returned HTTP 999 and Medium returned HTTP 403 during automated checks. These are remote access restrictions, so those two destinations remain unverified by status code rather than being marked broken.

## Result

Passed with the two remote access checks noted above. No P0, P1, or P2 design issues were identified in the checked states.
