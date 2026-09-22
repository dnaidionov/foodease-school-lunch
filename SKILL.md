---
name: foodease-school-lunch
description: Inspect a family's Foodease school menu, apply saved child-specific meal preferences, and prepare or place school meal orders. Use when ordering through app.foodease.cafe; do not use for unrelated meal planning.
---

# Foodease School Lunch

Help a parent order school meals through the Foodease portal at `https://app.foodease.cafe/`. Each parent signs in with their own account; never request, store, or share credentials. The website is common across families, but children, menus, dates, funds, and saved preferences belong to each family's account.

## Preference setup and persistence

At the first ordering session for a parent/child, inspect the account's child list and the current ordering controls, then ask only for unresolved preferences. Ask in one concise batch:

- Which children to order for (unless unambiguous from the account/request).
- Which meal types to order: lunch, breakfast, or both; weekdays/date range are request-specific and should not be saved as permanent preferences.
- Foods the child likes or reliably accepts, and foods to avoid. Ask whether avoidances are hard restrictions (allergy, religious, or other must-not-serve) or ordinary dislikes. Do not infer allergy safety from menu names; present uncertain ingredient/allergen details for parent review.
- Whether to choose an optional second product/alternate when available, and any quantity preference. Some slots are exclusive: do not add an alternate on top of an entrée if the portal says only one item can be selected.
- Any spending limit or preferred fallback rule when none of the available items match. By default, order for the entire calendar month unless the parent specifies particular dates. If the preferred option is unavailable on a date, use that date's default option unless a hard exclusion makes it unsafe or prohibited.

Save confirmed preferences in a parent-specific local file outside this shared skill, for example `~/.codex/foodease-preferences/<parent-chosen-profile>.json`. Ask the parent to choose a profile name if there are multiple families/profiles on the same device. Keep the schema minimal: child label, meal types, likes, dislikes, hard exclusions with exact parent wording, optional-item rule, fallback rule, and last-confirmed date. Do not store account IDs, student IDs, credentials, payment details, or sensitive identifiers. Never place a real family's preferences in this shareable skill or repository.

On later sessions, load that parent's preference file and do not ask the same setup questions again. Ask only if a new child appears, a needed preference is missing, the parent requests a change, or an actual menu choice cannot be resolved under saved rules. Allow direct updates such as “change his preferences” and save the revised preference only after the parent states it. If a preference file is unavailable, explain that saved preferences could not be found and ask again rather than pretending to remember.

## Ordering workflow

1. Open the provided Foodease URL and confirm that the page is the parent portal for the expected school. If it opens on staff login, use the visible Parents → Login route. Let the parent handle any sign-in step that requires their intervention.
2. Inspect the logged-in account's children and choose the requested child. Do not assume the currently selected child is the only child in the family.
3. Open **Orders → New Order**. The “Place New Orders” grid may list breakfast and lunch as separate rows per date. Read the actual dates, meal slot, products, status, and price; do not rely on a prior month's menu or infer dates from row position.
4. Open each requested meal slot and inspect every current product, accompanying items, price, and requirement. The selection page can show an “Additional Lunch Options” row as a mutually exclusive alternative to the daily entrée. Treat “optional” literally; do not select it unless saved preferences/request support it.
5. Apply hard exclusions first, then saved likes and dislikes. If the preferred option is unavailable on a date, select that date's default option, unless a hard exclusion prohibits it. If no safe/acceptable choice remains, skip that date and tell the parent why. If preferences do not distinguish options, follow the saved fallback or ask a narrow question. Unless the parent specifies dates, order for the full calendar month (all available requested meal slots in that month), not a subset.
6. Check the existing order status and avoid duplicating already completed orders. Preserve pending/incomplete items unless the parent asked to change them. The portal may aggregate balances and order costs; report the relevant total before final submission.
7. Add the requested items to the order and submit the order through the portal, but do not add funds, enable auto-pay, or submit any payment/top-up. Do not stop for a separate review before this order submission. If the current balance is insufficient, submit what the portal allows from existing funds and leave any remaining checkout/payment action for the parent to complete.
8. After submission, verify the portal's confirmation or completed order rows. Show the parent the resulting order here, including dates, child, meal choices, optional items/quantities, total, and any unpaid balance or skipped/failed dates. Do not claim success based only on clicking a submit button; clearly say if the portal only saved pending items and the parent still needs to complete checkout.

## Observed Foodease behavior

The current observed portal had **MY ACCOUNT → FAMILY → CHILDREN**, **ORDERS → NEW ORDER**, **PENDING ORDERS**, and **ORDER HISTORY**. The new-order grid displayed separate breakfast and lunch slots and marked rows “Incomplete” until the parent completes them. An individual lunch slot displayed `Select Products You can only order one of these items.`; the observed October 1 slot offered an entrée and “Additional Lunch Options,” both $4.50 and optional. Treat this as a per-slot observation, not a permanent menu fact. Reinspect the live menu and notices every session because school, dates, offerings, prices, and UI may change.
