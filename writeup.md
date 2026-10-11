# Week 2 — Spec-Driven Development with Spec Kit

## Project

Quote-of-the-day page: a random quote from a built-in collection, a “New quote”
button, and favorites stored in browser `localStorage`.

## Skill prompts

The prompts planned for the Spec Kit stages were:

```text
/speckit-constitution Create principles focused on code quality, testing, and maintainability.
/speckit-specify A quote-of-the-day page: one random quote from a built-in list, a "New quote" button, and favoriting that persists across reloads.
/speckit-plan Use plain HTML/CSS/JavaScript, no backend; persist favorites in localStorage.
/speckit-tasks
/speckit-implement
/speckit-converge
```

The Spec Kit CLI and `/speckit-*` chat skills were not available in this
workspace. I authored the matching constitution, specification, plan, and task
artifacts directly and implemented the page against them; the prompts above are
the prompts this project is prepared to use, not a claim that the skills ran.

## Spec refinement: before and after

**Before:** “Favorite a quote and keep favorites after reload.” This left open
whether there was one favorite or a collection, and how a returning visitor
could find a saved quote.

**After:** The refined specification defines a collection keyed by stable quote
IDs, requires a visible favorites list whose entries can be selected to restore
the quote as active, and clarifies that the active quote itself does not persist.
That clarification changed the output: the page now renders a selectable
favorites list and an empty state instead of only persisting a boolean for the
currently displayed quote. The refinement and resulting requirements are in
`.specify/specs/001-quote-of-the-day/spec.md`.

## Convergence outcome

The page was checked in a browser against the specified core interactions:
initial quote rendering, selecting another quote, adding and removing favorites,
selecting a saved quote, and restoring the favorites list after reload. I also
simulated a storage write failure and verified the page showed an error without
adding the favorite. At a 390 px viewport there was no horizontal overflow, and
keyboard Tab navigation reached the “New quote” button. The favorite state uses
stable built-in quote IDs in a versioned localStorage key.

**Spec Kit convergence status: not run.** This environment did not provide the
Spec Kit chat skills, so I cannot report the required `/speckit-converge`
“Converged” result. The checklist records this as incomplete rather than
misrepresenting a manual review as a Spec Kit run. Run `/speckit-implement` and
`/speckit-converge` in a Spec Kit-enabled agent to complete that assignment
requirement.

## What I learned

Writing the first requirements down felt like overhead for obvious details such
as showing a quote at page load. The specification paid off when “favorites
persist” turned out to hide an important product decision: whether a saved
quote could actually be found and revisited. Making that behavior explicit
changed the page structure before implementation rather than requiring a
late code workaround. A short acceptance checklist also made it easier to
review the core experience without adding a framework or backend.
