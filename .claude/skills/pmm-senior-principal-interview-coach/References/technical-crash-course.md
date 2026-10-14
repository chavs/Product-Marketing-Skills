# Technical Crash Course

A layered way to learn how a company's product works, fast enough to talk about it in an interview. The user steers the depth. Do not dump everything at once.

## Layers

Teach one layer at a time. After each layer, stop and ask which way to go next. Do not continue on your own.

1. **What it is.** Two or three sentences: who uses it, what problem it solves, how it is sold.
2. **Architecture.** The main components, how data or requests flow between them, and where the product sits next to what the customer already runs. Offer a diagram if a diagram tool is available.
3. **Deeper.** Real systems vocabulary and mechanisms. If the user says "no analogies", use none. Use the terms an engineer on the team would use.
4. **Edge cases.** What happens when it fails, when it is attacked, when it is misconfigured, and when a dependency is down. Say what the vendor documents for each and what it does not.

The user may jump to any layer or ask a single question. Answer only that question (working rule 1).

## Rules for the content

- **Capabilities apart from use cases.** List what the product can do. Then, separately, list the use cases customers apply it to. Do not offer a use case as if it were a capability.
- **Vendor docs first.** Read the vendor's documentation, architecture pages and API docs before any third-party summary. Then read practitioner write-ups. Cite every claim inline.
- **Flag the gaps.** Mark anything the vendor does not document as "not documented". Mark anything you inferred as inferred. Never fill a gap with a plausible guess.
- **Precision on definitions.** Before building on a definition (for example two terms that sound alike but mean different things), list it in one "assumptions to confirm" block and get a yes (working rule 3). The user often knows the domain better than a search does.

## Where it goes

Short answers stay in the chat. If the user wants to keep one, add it to the "How it works" section of the prep guide (see `prep-guide.md`).

## Out of scope

Competitor comparison (use `/analysts` or the live assistant's competitive research) and answer coaching (use `/practice` or `/drill`).
