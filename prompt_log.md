# Prompt Evolution Log and Reflection

## prompt_log

| version | prompt                                                                                                                       | impact                                                                                                    |
|---------|------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| v1      | “Using Material Design guidelines, generate three mobile screens for ExpenseTracker: Dashboard, Add Expense, History. Export as PNG.” | Basic layouts generated, but lacked clear visual hierarchy and consistent spacing.                         |
| v2      | “Revise v1 mockups: apply Roboto 16sp/20sp, add bottom nav bar, center FAB, full-width Save button, group History by date.”    | Typography and navigation improved; spacing correct; still needed better color contrast for accessibility. |
| v3      | “You are a senior designer. Use Material theming: primary/secondary palette, elevation shadows, 48dp touch targets, WCAG AA contrast.” | Cohesive color scheme and shadows achieved; contrast and accessibility remained issues in some areas.     |
| v4      | “You are a UX mentor. Annotate screens with user flow notes and micro-interaction callouts (ripple effects, transitions).”    | Added useful annotations for developer handoff; screens became visually busy—trade-off noted.             |

## evolution and iteration

We observed a clear evolution in fidelity and usability with each iteration. The **impact** of adding design system references and role framing was significant:

- **v1 → v2**: Simple layout → improved structure and spacing  
- **v2 → v3**: Better color & contrast → enhanced accessibility  
- **v3 → v4**: Functional annotations → actionable developer guidance

## reflection

This **reflection** captures my experience guiding the **AI** through prompt engineering for UI design. 

What was easy:  
- Generating initial wireframes with simple prompts was straightforward. The **AI** quickly translated text into basic screens.  
- Embedding Material Design terms (e.g., “FAB”, “bottom nav”, “elevation”) consistently improved output quality.

What was hard:  
- Balancing information density: adding annotations cluttered screens, requiring further **iteration** to refine clarity.  
- Ensuring strict **accessibility** compliance demanded precise color contrast and touch target specifications.

How design system references improved results:  
- Referencing Material components and exact font sizes led to mockups that map directly to code components.  
- Using terms like “WCAG AA” and “48dp touch targets” made the **workflow** produce accessible, developer-ready assets.

Suggestions for using this workflow in a real **team**:  
1. Maintain a **prompt** library of tested fragments (e.g., typography, contrast rules).  
2. Pair AI cycles with quick user or stakeholder reviews to validate **usability**.  
3. Integrate prompt templates into a shared design automation plugin—this **workflow** scales design updates as brand guidelines evolve.  
4. Document each **iteration** and **impact** in a central repo for transparency and continuous improvement.

Overall, AI-assisted mockup generation accelerated prototyping, but it requires careful prompt engineering, **reflection**, and collaboration within the **team** to deliver polished, accessible UIs.  
