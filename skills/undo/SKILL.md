---
name: undo
description: Undo the latest WikiDrive save in this conversation. Run by the user as /wikidrive:undo, or used when the user asks to undo a WikiDrive change.
disable-model-invocation: true
---

The user asked to undo their latest WikiDrive change in this conversation.

- A rule save: call `wikidrive_revise` with each saved line exactly as the save message quoted it, and its topic or `prompt_id`, without `replace_with`.
- A document change: call `wikidrive_undo_doc` with the `prompt_id` and `version` the document message showed. To go back one more change, call it again with the new version.
- No WikiDrive change in this conversation: say so, and that everything can be reviewed and undone at wikidrive.app.

Tell the user the returned message in one line.
