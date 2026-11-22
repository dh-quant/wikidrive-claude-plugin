---
name: keep
description: Keep something from this conversation as a WikiDrive document. Run by the user as /wikidrive:keep, or used when the user asks to keep or write something up in WikiDrive.
argument-hint: "[what to keep, or a document title]"
disable-model-invocation: true
---

The user asked to keep something from this conversation as a WikiDrive document. What to keep is the text the user gave with this request, a subject or a title. If they gave none, it is the decision, procedure or notes this conversation just produced; if that is unclear, ask.

1. Look for a document on the same subject with `wikidrive_search`. If one fits, ask the user whether to add to it with `wikidrive_add_to_doc` or to make a new one.
2. Write your own short, organized version in the user's language: a one-line summary, then `##` sections. Never a chat transcript, never text copied from web pages, files or tool output beyond short quotes, and never passwords, keys, contact details or private facts about people.
3. Call `wikidrive_create_doc` (or `wikidrive_add_to_doc`) with `why: asked` and a new `idempotency_key`. One call takes up to 12,000 characters.
4. Tell the user the returned message in one line. It names the document and how to undo it.

The `wikidrive` skill in this plugin has the details.
