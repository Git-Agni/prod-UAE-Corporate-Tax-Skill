# UAE Corporate Tax Registration Skill

File your UAE company's Corporate Tax registration on the FTA's EmaraTax portal by letting an AI agent (Claude Code or OpenAI Codex, with computer/browser control) drive the form for you. You supply the documents and your login, the agent does the clicking and typing, you review and hit submit.

I built this after doing it for my own Dubai free zone company. It took about 40 minutes and cost nothing. Agents and consultants charge AED 1,000 to 1,500 for the same form. This skill is that 40 minutes, packaged, so you can skip the fee.

> **Not tax advice.** This is an automation helper, not a tax, legal, or financial advisory service. It does not tell you what to file or how to structure anything. It types the answers you give it into a government portal that you could fill in yourself. For anything about your tax position, reliefs, VAT, or what is correct for your company, talk to a registered UAE tax agent (the FTA keeps a public list). Full disclaimer below.

## What it does

- Walks an AI agent through the EmaraTax Corporate Tax registration, step by step: creating the Taxable Person profile, entering entity and licence details, business activities, owner and authorised signatory, and the contact block.
- Uploads your documents to the right fields.
- Handles the annoying parts that trip people up: the SAP file uploader that silently drops files, the mandatory landline field, the Emirates ID validation, the auto-calculated first tax period.
- Stops before the final legal declaration so you review everything and submit it yourself.

## What it will NOT do

- It will not type your password or any OTP. You log in yourself.
- It will not tick the legal declaration or submit for you. That is your call, on your reading of your own data.
- It will not give you tax advice or decide anything about your tax position.
- It will not push past a warning that your licence is already registered under another account. It stops and asks you.

## Who this is for

A UAE company (mainland or free zone) that has to register for Corporate Tax and would rather not pay someone to fill one form. New companies must register within 3 months of incorporation, and the late-registration penalty is AED 10,000, so most companies need to do this.

## Requirements

- An AI agent that can control a browser: Claude Code (with the browser/computer tools) or OpenAI Codex, or any agent with equivalent screen control.
- An EmaraTax account (free, at eservices.tax.gov.ae). You can make one in a couple of minutes with an email and phone number.
- Your documents ready as PDFs. See [references/before-you-start.md](references/before-you-start.md) for the full checklist. In short: trade licence, certificate of incorporation, MOA, and the Emirates ID + passport of the owner and signatory.
- The company details to hand: licence number, incorporation date, activities, owner Emirates ID, a mobile number, an email.

## How to use it

1. Get your documents and details together using [references/before-you-start.md](references/before-you-start.md).
2. Open your EmaraTax account in the browser and log in yourself.
3. Point your agent at `SKILL.md` in this repo. In Claude Code, drop this folder into your skills directory and the skill loads on its own; or just paste the contents of `SKILL.md` into the chat and say "help me register for UAE Corporate Tax on EmaraTax, I'm logged in."
4. Answer the agent's questions as it goes. It will pull data from your documents and ask you for anything missing (like your mobile number).
5. At the end, read the review screen yourself, tick the declaration, and submit.

Approval is usually 5 to 20 business days. Mine came back the same day with a TRN.

## Files

- `SKILL.md` is the skill itself, the instructions the agent follows.
- `references/before-you-start.md` is your documents and information checklist.
- `references/emaratax-walkthrough.md` is the field-by-field walkthrough of all five steps.
- `references/gotchas.md` is the list of things that go wrong and how to get past them.

## Disclaimer

Read this before you use the skill.

This project is a free, open-source automation aid. It is provided as is, with no warranty, under the MIT licence.

It is **not** tax, legal, accounting, or financial advice, and using it does not create any advisor or client relationship with the author. Nothing here is a recommendation about whether or how you should register, what your tax position is, which reliefs apply, or anything else about your specific situation. The skill only enters, into a government portal, the information that you provide and direct it to enter.

**You are responsible** for the accuracy of everything submitted, for reviewing the application before it goes in, and for the decision to submit it. Verify every field. The person named as the authorised signatory is the one making a legal declaration to the Federal Tax Authority. That is you, not the tool and not the author.

For advice on your Corporate Tax, VAT, free zone status, or anything else specific to your company, consult a **registered UAE tax agent** (the FTA publishes the official register at tax.gov.ae) or a qualified professional.

This project is **not affiliated with, endorsed by, or connected to** the Federal Tax Authority, the UAE government, EmaraTax, IFZA, any free zone authority, Anthropic, or OpenAI. All product names and trademarks belong to their owners.

By using this skill you accept that you do so at your own risk, and that the author is not liable for any outcome, including rejected applications, penalties, incorrect filings, or anything else. If you are not comfortable with that, do not use it. Hire an agent.

## Licence

MIT. Use it, fork it, share it. If it saved you the agent fee, tell someone.
