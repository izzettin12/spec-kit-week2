# Project Constitution

## Principles

### 1. Keep the solution simple
Use plain HTML, CSS, and JavaScript. Keep the page static and self-contained, with
no backend, framework, build step, or third-party runtime dependency.

### 2. Make behavior testable
Express user-visible behavior as observable acceptance criteria. Keep quote data,
selection, favorites, and rendering responsibilities clear enough to verify
independently.

### 3. Preserve user data predictably
Persist favorites in browser `localStorage`. Use stable quote identifiers rather
than quote text as identity, and make storage failures visible instead of silently
pretending data was saved.

### 4. Build an accessible interface
Use semantic HTML, keyboard-operable controls, visible focus, sufficient contrast,
and accessible labels and state for interactive controls.

### 5. Prefer maintainable changes
Avoid unnecessary abstractions and dependencies. Keep names descriptive and update
the specification when a requirement needs clarification rather than compensating
with undocumented implementation behavior.

## Quality Gate

Before considering a change complete:

- Verify every acceptance criterion against the running page.
- Verify favorites remain available after reload.
- Check the page at a narrow viewport and with keyboard navigation.
- Report any unverified behavior or environment limitation explicitly.
