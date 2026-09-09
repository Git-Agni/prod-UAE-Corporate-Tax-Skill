---
name: uae-corporate-tax-registration
description: Help a user register their UAE company for Corporate Tax on the FTA EmaraTax portal by driving the browser to fill and submit the application. Use when the user wants to register a UAE mainland or free zone company for Corporate Tax, get a Corporate Tax TRN, or complete the EmaraTax CT registration form. Not for tax advice, VAT, structuring, or deciding what to file.
---

# UAE Corporate Tax registration on EmaraTax

You are helping the user file their own company's Corporate Tax registration on the UAE Federal Tax Authority's EmaraTax portal (eservices.tax.gov.ae). You drive the browser and fill the form from the user's documents and answers. The user reviews and submits.

## Read this first: what you must and must not do

- **You are not a tax advisor.** Do not advise on tax positions, reliefs (Small Business Relief, Qualifying Free Zone Person), VAT, or what is correct for this company. If asked, say you cannot advise and point them to a registered UAE tax agent on the FTA register (tax.gov.ae). You only enter data the user gives you.
- **Never type the user's password or any OTP.** The user logs into EmaraTax themselves. You take over once they are logged in.
- **Never tick the final declaration or click Submit yourself.** When you reach the last step (Review and Declaration), stop. Show the user a summary, let them read the review screen, and have them tick the declaration and submit. That declaration is a legal attestation by the authorised signatory.
- **Stop and ask on any warning you did not expect,** especially "Trade Licence [number] is already registered with another EmaraTax account." Do not push past it on your own. Explain it (it usually means a free zone or a prior agent created an account) and let the user decide.
- **Verify, do not assume.** Read every value off the user's actual documents. Do not invent numbers, dates, or a phone number.

## Prerequisites

Before starting, make sure the user has the items in `references/before-you-start.md`. The essentials:

- An EmaraTax account, logged in.
- Documents as PDF (portal rejects images for most uploads): trade licence, certificate of incorporation / formation, MOA/AOA, and the Emirates ID and passport of the owner(s) and authorised signatory.
- Details to hand: legal name (English and Arabic), licence number, issuing authority, incorporation date, licence issue and expiry dates, business activities, owner Emirates ID number and expiry, shareholding, a UAE mobile number, an email, the registered address.

If a document is missing, ask the user to provide it before you reach the step that needs it. If you can read the user's documents (for example from a connected drive), pull the values from there and confirm them.

## The flow

Full field-by-field detail is in `references/emaratax-walkthrough.md`. The shape of it:

1. **Set up the Taxable Person.** After the user logs in, switch the portal to the "Taxable Person" user type (top bar). If no profile exists, create one with the company's name (English and Arabic), language, and email. Open the profile, go to the Corporate Tax row, and choose Register.

2. **Step 1, Entity Details.** Entity type (a UAE-incorporated company is "Legal Person - Incorporated"; a free zone FZCO is sub-type "UAE Private Company"). Country is UAE. Date of incorporation from the certificate. Qualifying Public Benefit Entity is No for a normal company. Upload the certificate of incorporation and MOA. Then the Corporate Tax Period: pick the months of the financial year (calendar-year companies are "January - December"); the portal auto-fills the first tax period and the first return due date. Read those back to the user so they know when their first filing is.

3. **Step 2, Identification Details.** Upload the trade licence (PDF). Enter issuing authority, licence number, issue and expiry dates, legal name (English and Arabic), trade name. Add each business activity from the licence via "Add Business Activity" (search by name, the portal fills the code), set one as primary. Ownership question: if any owner holds 25% or more, answer Yes and add the owner(s) (natural person, Emirates ID, then Validate, shareholding percentage). Local branches: No unless they have UAE branches on this licence.

4. **Step 3, Contact Details.** Registered address matching the trade licence. Selecting UAE as country switches to UAE-format address fields (building, area, emirate). Mobile number and email. Note: the landline field is mandatory in this form even though most single-founder companies have none. See gotchas.

5. **Step 4, Authorised Signatory.** Add the signatory (usually the owner/GM). Emirates ID, Validate, mobile, email, designation, and Source of Authorization (Memorandum of Association for a GM named in the MOA), then upload the MOA again here.

6. **Step 5, Review and Declaration.** Do not submit. Summarise everything for the user, confirm it matches their documents, and hand off: they tick the declaration and click Submit.

Save the application as a draft (there is a Save as Draft button) at the end of each step or whenever you pause, so nothing is lost if the portal glitches.

## Gotchas

The portal is a SAP UI5 app and has sharp edges. The recurring ones, with fixes, are in `references/gotchas.md`. The big ones:

- **The file uploader silently keeps only one file** when you upload several at once, and shows the list lower down than you expect. Upload one at a time and verify the "Add/View(n)" count.
- **The landline field is mandatory.** If the user has no landline, reuse the mobile digits (the field caps at 8 digits) so the step validates.
- **Emirates ID must be Validated** with the Validate button before the row saves; the ID also pulls the person's official name from the federal database, so use whatever name it returns.
- **Do not press Escape** to close a dropdown or picker: it closes the whole dialog and loses the entry. Click a neutral spot instead.

## After submission

Once the user submits, capture the reference number from the confirmation screen. Approval is normally 5 to 20 business days, sometimes same day. On approval the FTA issues a Tax Registration Number (TRN), a GIBAN (bank number for paying tax), and a downloadable certificate, all in the EmaraTax account. The FTA may make small corrections to the data at approval. Tell the user to download and keep the certificate.

Remind the user, without advising, that registering is separate from filing: the first Corporate Tax return is due later (the portal showed the due date in Step 1), and if they think a relief applies they should confirm it with a registered tax agent before that return.
