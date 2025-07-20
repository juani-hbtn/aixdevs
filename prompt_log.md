# Prompt Evolution Log and Reflection

## Prompt Log

| Version | Prompt (with Context)                                                                                                                   | Impact                                                                                                    |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| v1      | “Using Material Design guidelines, generate three mobile screens for ExpenseTracker: 1) Dashboard with cards & FAB; 2) Add Expense form; 3) History list. Export as PNG.” | Produced basic layouts but lacked clear hierarchy, consistent spacing, and color accents.                  |
| v2      | “Revise v1 mockups: use Roboto 16sp body / 20sp headings; add bottom nav bar with icons; center FAB; full-width Save button; group History by date; enforce WCAG contrast. Export each as PNG.” | Improved typography and navigation bar; spacing and touch targets correct; still needed stronger color contrast. |
| v3      | “You are a senior designer. For ExpenseTracker screens, apply Material theming: primary/secondary color palette, elevation shadows, 48dp touch targets, and accessible color contrast (WCAG AA). Export separate PNGs.” | Achieved cohesive color scheme, clear shadows, and accessible contrast; some micro-interaction hints missing. |
| v4      | “You are a UX mentor. Annotate each screen with user flow notes (e.g., tap FAB opens Add, swipe to delete) and add micro-interaction callouts (e.g., ripple effect on buttons). Export annotated PNGs.” | Added useful callouts for next-step implementation; screens became crowded with annotations—trade-off noted. |

## What Worked Best

- **design System References**: Explicitly naming “Material Design,” Roboto font sizes, elevation and color roles immediately improved consistency and hierarchy.  
- **Role Framing**: Switching from a generic AI to “senior designer” or “UX mentor” enhanced the depth of suggestions (e.g., callouts, micro-interactions).  
- **Accessibility Constraints**: Calling out “WCAG AA contrast” and “48dp touch targets” ensured the mockups met real-world usability standards.

---

# Reflection (≈350 words)

Iterating on prompts to drive AI-generated mockups taught me that clarity and specificity are paramount. Initially, the AI understood basic layout instructions but missed fine details like consistent typography, accessible contrast, and platform-specific navigation patterns. Referencing a concrete design system (Material Design) with explicit token names (e.g., Roboto 16sp, primary/secondary colors) quickly aligned the output with industry-standard best practices.

What was easy: Getting the AI to produce rough wireframes and basic screen layouts. Simple prompts for “Dashboard with cards” or “form for expense entry” yielded immediately usable visuals. The AI’s ability to scaffold a multi-screen flow from a plain-language description was impressive and accelerated the prototype phase.

What was hard: Balancing visual clarity with annotation. When I asked for micro-interaction callouts, screens became cluttered, illustrating the trade-off between documenting every detail and maintaining a clean visual. It also took several iterations to perfect accessibility details; specifying “WCAG AA” once wasn’t enough until combined with “48dp touch targets” and precise color names (e.g., “#1E88E5 on white”).

Design system references proved invaluable. By invoking Material Design terms—such as “elevation,” “FAB,” and “bottom navigation”—the AI tapped into consistent component libraries, producing designs that would map directly to code components in React Native or Flutter. This cut down conceptual translation time and reduced ambiguity.

For a real team workflow, I’d recommend maintaining a **prompt library**: a living document of tested prompt fragments (e.g., “use Roboto 16sp”, “apply WCAG AA”) that designers and developers can reuse. Pairing AI iterations with quick user-testing snapshots (even informal hallway tests) would validate micro-interaction proposals. Finally, integrating this process into a Figma plugin or a design automation script can streamline updates: updating the prompt library automatically regenerates assets when design tokens or brand guidelines evolve.

Overall, AI-assisted mockup generation is a powerful way to jumpstart UI design, but it requires careful prompt engineering and human judgment to ensure clarity, accessibility, and development readiness.
