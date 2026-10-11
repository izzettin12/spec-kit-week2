# Week 2 — Spec-Driven Development with Spec Kit

## Project

A static quote-of-the-day page with a built-in quote collection, a “New quote”
control, and favorites that persist across reloads.

## Skill prompts used

I used the assignment's prompts for the Spec Kit stages:

```text
/speckit-constitution Create principles focused on code quality, testing, and maintainability.
/speckit-specify A quote-of-the-day page: one random quote from a built-in list, a "New quote" button, and favoriting that persists across reloads.
/speckit-plan Use plain HTML/CSS/JavaScript, no backend; persist favorites in localStorage.
/speckit-tasks
/speckit-implement
/speckit-converge
```

The repository already contained the page and initial artifacts from the earlier
work. In this recovery pass I ran the stages against that feature, refined the
specification and plan, regenerated the task breakdown, and ran implementation
and convergence checks. The implementation pass verified the existing page
against the completed tasks; no application-source changes were needed.

## Spec refinement: before and after

**Before:** “Favorite a quote and keep favorites after reload.” This left open
whether there was one favorite or a collection, and how a returning visitor
could find a saved quote.

**After:** The specification defines a collection keyed by stable quote
identities, requires a visible favorites list whose entries can be selected to
restore the quote as active, and clarifies that only favorites—not the active
quote—persist. This changed the expected output from a favorite toggle alone to
a selectable favorites list with an empty state. The refinement is documented
in `.specify/specs/001-quote-of-the-day/spec.md`.

## Implementation and verification

The `/speckit-implement` pass completed all eight tasks in
`.specify/specs/001-quote-of-the-day/tasks.md`. In the browser I verified initial
quote rendering, a different quote from “New quote”, adding and removing
favorites, selection of a saved quote, and restoration after reload. I also
simulated storage read and write failures and confirmed the page showed errors
without claiming an unsuccessful save. At 320 px and 1280 px the page had no horizontal
overflow; keyboard navigation reached the controls with visible focus.

## Convergence outcome

**✅ Converged.** The final `/speckit-converge` pass found no gaps against the
specification, plan, tasks, or constitution, so it appended no convergence
tasks. The manual browser checks above cover the core interactions and the
storage write-failure path.

## What I learned

Writing down obvious behavior such as showing a quote on page load initially
felt like overhead. The specification paid off when “favorites persist” turned
out to hide a product decision: whether saved quotes could actually be found
and revisited. Defining a selectable favorites collection before implementation
changed the page structure rather than leaving the feature as a saved boolean.
The task breakdown and quickstart then made the implementation and review
criteria concrete without needing a framework or backend.
