# Gotchas and troubleshooting

EmaraTax is a SAP UI5 app. Browser agents hit the same handful of snags every time. Here they are with the fix.

## The file uploader keeps only one of several files

When you upload multiple files to a field in one action, the uploader often registers only one, and the button shows "Add/View(1)" when you expected more. It also renders the attached-file list further down the page than the drop zone, so it looks empty at first.

**Fix:** upload one file at a time. After each, click the "Add/View(n)" button to open the attachments popover and confirm the file is listed and the count is right. Add the next from inside that popover with its Upload button.

## The landline field is mandatory

Step 3 (Contact Details) requires a landline number and its country code, even though most single-founder companies do not have a landline. Clearing the country code makes it worse (it then demands both fields).

**Fix:** put a number in. Reuse the mobile digits. The landline field caps at 8 digits, so it takes the first 8. Set the country code to +971 and enter the number, and the step validates.

## Emirates ID must be validated, and it renames the person

An owner or signatory row will not save until you click Validate next to the Emirates ID. Validation also fetches the person's official name from the federal database.

**Fix:** always click Validate and wait for "Emirates ID Validated!" Use whatever name it returns, even if it differs slightly from what you expected (for example a dropped middle name). That is the name of record.

## Do not press Escape

Pressing Escape to dismiss an open dropdown, date picker, or suggestion list closes the entire dialog and discards what you were entering.

**Fix:** to dismiss a dropdown or picker, click a neutral empty area of the form instead. Never Escape out of a modal you are mid-way through.

## Selecting UAE resets the address fields

In Step 3, choosing "United Arab Emirates" as the country switches the address block from free-text lines to UAE-specific fields (Building, Street, Area, Emirate) and clears anything you typed in the old fields.

**Fix:** pick the country first, then fill the address into the new UAE fields.

## Date fields

The DD/MM/YYYY fields accept a typed value, but typing then pressing Escape (to close the calendar) wipes the dialog. Setting the value programmatically (via a form-input action rather than keystrokes) avoids opening the picker at all.

**Fix:** prefer setting date values directly over typing plus Escape. If you must type, click a neutral spot to dismiss the calendar, not Escape.

## "Trade Licence already registered with another EmaraTax account"

A warning that your licence is already linked to a different EmaraTax account. Common causes: the free zone or a prior agent created an account for the company, or a VAT-related profile exists.

**Fix:** do not auto-continue. Stop and tell the user. It usually means an account exists elsewhere. Continuing can create a duplicate registration (administrative to unwind, but no penalty). The user decides whether to proceed, or to get access to the existing account instead. If they proceed and the FTA later flags a duplicate, they reconcile it with whoever holds the other account and keep the TRN under an account they control.

## The portal is slow to load

The SAP shell can take several seconds to render, and can flash blank or show broken "Icon" placeholders mid-transition.

**Fix:** wait and re-screenshot before deciding a page is broken. Navigate to the app's index URL (the deep `.../index.html?sap-client=100` path), not the bare domain, which does not render the app.

## Save often

Any glitch can lose the current step.

**Fix:** click Save as Draft at the end of each step. You can resume from the Corporate Tax row's Action menu on the Taxable Person dashboard.
