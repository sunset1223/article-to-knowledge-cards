---
name: make-knowledge-cards
description: "Convert pasted articles or local Markdown and plain-text files into source-grounded knowledge cards, usually five to eight and always one knowledge point per card. Use for article notes, study cards, and knowledge distillation; do not use for web scraping, PDF extraction, Anki export, or graphical interfaces."
---

# Make Knowledge Cards

Transform source material into a compact set of self-contained knowledge cards.

## Acceptable Inputs

- An article or passage pasted directly into the conversation.
- A local `.md` or `.txt` file supplied by the user.
- Multiple files or passages when the user provides them as one source set.

Do not attempt web scraping, PDF extraction, Anki export, or GUI generation. If
the user requests one of those unsupported formats, state the boundary and offer
the supported alternative: make the cards in Markdown from pasted text or a
local `.md`/`.txt` file.

## Workflow

1. Read the complete source before selecting cards. For a local file, inspect its
   contents rather than guessing from the filename.
2. Identify candidate knowledge points: central claims, necessary definitions,
   mechanisms or causal relationships, conditions and boundaries, and principles
   that materially affect understanding.
3. Rank candidates by importance and source centrality. Prefer ideas that the
   source develops, depends on, or returns to over isolated details, anecdotes,
   and rhetorical examples.
4. Merge cards that express the same idea or where one point only supports
   another. Keep one independently useful knowledge point per card.
5. Produce five to eight cards when the source contains that many distinct,
   important points. If it contains fewer, produce fewer; do not split one point
   into several cards or add outside information to reach five.
6. Check every card against the source. Remove unsupported implications,
   invented facts, and examples that introduce information absent from the
   source.

## Card Requirements

Use the source language unless the user requests another output language.
Localize the field labels consistently with the output language; do not mix
English labels into a non-English card. The following example uses English
labels:

### 1. Card title

- **Core knowledge:** One concise, specific claim or principle.
- **Explanation:** A short explanation in the context of the source.
- **Example or self-test:** Reuse or closely condense an example from the source,
  or ask one question answerable from the card without introducing new facts.

Requirements:

- Keep one knowledge point per card.
- Make the title descriptive enough to identify the point at a glance.
- Ensure the core knowledge is a usable statement, not merely a topic label.
- Keep explanations concise and preserve important distinctions, conditions,
  and qualifications from the source.
- Keep labels and card content in the selected output language.
- Remove repeated material across cards.
- Do not add facts, interpretations, recommendations, or examples that the
  source does not support.

When fewer than five distinct points exist, output only the supported cards and
end with a brief note that the source does not contain enough separate important
points to reach five.
