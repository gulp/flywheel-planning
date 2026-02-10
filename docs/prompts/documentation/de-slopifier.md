---
icon: lucide/file-edit
tags:
  - writing
  - documentation
  - editing
  - style
  - ultrathink
---

# The De-Slopifier

Remove telltale AI writing patterns from documentation and text

## Prompt

```title="Copy and paste into agent session"
I want you to read through the complete text carefully and look for any telltale signs of "AI slop" style writing; one big tell is the use of em dash. You should try to replace this with a semicolon, a comma, or just recast the sentence accordingly so it sounds good while avoiding em dash.

Also, you want to avoid certain telltale writing tropes, like sentences of the form "It's not [just] XYZ, it's ABC" or "Here's why" or "Here's why it matters:". Basically, anything that sounds like the kind of thing an LLM would write disproportionately more commonly that a human writer and which sounds inauthentic/cringe.

And you can't do this sort of thing using regex or a script, you MUST manually read each line of the text and revise it manually in a systematic, methodical, diligent way.
```

## When to Use

- After generating documentation with AI
- When editing README files
- When polishing any AI-generated text for human readers

## Tips

- Pay special attention to em dashes -- they're a dead giveaway
- Watch for "Here's why" and similar AI-isms
- Read the output aloud to catch unnatural phrasing
- Must be done manually line-by-line, not with regex
