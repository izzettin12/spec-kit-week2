# Data Model: Quote of the Day

## Quote

A built-in entry that can be displayed or saved as a favorite.

| Field | Meaning | Validation |
|---|---|---|
| `id` | Stable identity for a quote | Unique, non-empty string |
| `text` | Quote content | Non-empty string, displayed as text |
| `attribution` | Quote author or source label | Non-empty string, displayed as text |

The collection contains at least five quotes.

## Favorite

A visitor's saved selection, linked to a `Quote` by its stable `id`.

| Field | Meaning | Validation |
|---|---|---|
| `quoteId` | Identity of the saved quote | Must match a quote in the built-in collection |

Favorites form a set: a quote can appear at most once. Removing a favorite
removes its identity from the set. Persistence stores the set of identities;
unknown identities do not produce visible favorite entries.

## Page State

- `activeQuote`: one quote from the built-in collection.
- `favoriteIds`: the set of favorite quote identities.
- Storage error: a visitor-visible message when saved favorites cannot be
  loaded or updated; failed writes leave the prior favorite set unchanged.
