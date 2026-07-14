# Design QA

- Source visual truth: `/Users/gaoguangcai/.codex/generated_images/019f6066-c219-72a2-8c25-79d87d63bca9/exec-f0991034-1e60-44e3-a366-a7b73c608d2b.png`
- Implementation screenshot: `design/implementation-mobile-final.png`
- Combined comparison: `design/qa-comparison.png`
- Viewport: 390 x 844
- State: empty one-vehicle form, mobile Safari user-agent simulation

## Full-view comparison evidence

The combined comparison confirms the same core composition: white brand header, blue bridge/expressway hero, orange title accent, bilingual page title, green numbered sections, continuous white form surface, bordered vehicle block, and a prominent blue PDF action. The implementation intentionally replaces the source mock's forbidden group-name wordmark with the user-provided SDHS logo and the allowed `山高聚行 · 车险分期` label.

## Focused region comparison evidence

- Header and hero: checked at native 390 px width in `design/implementation-mobile-final.png`; supplied logo remains legible, title is not clipped, and the bridge asset leaves sufficient contrast for the copy.
- Form and vehicle controls: checked in `design/implementation-mobile-top.png` and `design/implementation-mobile-bottom.png`; field labels, required marks, select control, delete action, add-vehicle action, and fixed PDF action remain aligned and touchable.
- No additional crop was required because both focused regions are readable at native mobile resolution.

## Required fidelity surfaces

- Fonts and typography: Chinese system font stack, optical hierarchy, weights, wrapping, and line heights are consistent with the reference's formal corporate character. No clipping or truncation observed.
- Spacing and layout rhythm: header, hero, section gaps, input heights, dividers, and vehicle grouping closely match the selected source. The fixed mobile CTA is an intentional usability enhancement and keeps the primary action visible.
- Colors and visual tokens: official green/orange logo colors, blue hero/action color, pale gray dividers, red required/delete states, and white form surface match the reference direction.
- Image quality and asset fidelity: the exact user-provided logo crop is used. The hero uses a dedicated raster bridge/expressway asset generated for this design rather than a CSS drawing or placeholder.
- Copy and content: forbidden group-name text is absent from the UI. `山高聚行 · 车险分期`, form labels, vehicle controls, and PDF action copy are correct.

## Findings

- No actionable P0, P1, or P2 issues remain.

## Interaction and runtime checks

- Required-field validation exercised.
- Vehicle color native select exercised.
- Add and remove vehicle exercised; numbering and stale-PDF invalidation verified.
- iOS generation exercised: two-page A4 PDF, `application/pdf`, current insured-name filename, and share actions verified.
- Console errors and warnings checked: none.

## Comparison history

1. Initial implementation was too tall for the mobile reference and placed the primary action below the first viewport (P2). Reduced mobile header, hero, field, and section spacing while retaining touch targets.
2. Post-fix capture still left the primary action below the viewport (P2). Made the mobile generate panel fixed to the safe-area bottom and added page-bottom clearance.
3. Final comparison shows the primary action visible, no horizontal overflow, no clipped controls, and no remaining P0/P1/P2 mismatch.

## Follow-up polish

- P3: replace the supplied low-resolution logo with a higher-resolution version if one becomes available.

final result: passed
