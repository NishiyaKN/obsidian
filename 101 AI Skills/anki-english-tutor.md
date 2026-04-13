---
name: anki-english-tutor
description: Creates perfectly formatted Anki cards for English vocabulary study, targeting rare, advanced, or nuanced words. Use this skill whenever the user sends an English word and wants an Anki card or anki block created. Also triggers for batch card creation when the user sends a list of English words to be turned into an importable Anki .txt file. Trigger on any request involving English vocab cards, Anki blocks, English flashcards, or English study cards — even if phrased casually like "make a card for ephemeral" or "batch create these words for Anki".
---

# Anki English Tutor Skill

Creates Anki-ready cards for rare and advanced English vocabulary, with two modes: **single** (copyable block) and **batch** (importable `.txt` file).

The target user is a non-native English speaker with high proficiency. Cards should be precise and contextually rich, not simplified. Do not skip senses based on assumptions about how 'common' they are — exposure to different senses varies and cannot be assumed.

---

## Anki Note Type: 3 Fields

| Field | Content |
|---|---|
| `Front` | The word or phrase, exactly as written |
| `Back` | Part of speech + meaning + nuance + 2 example sentences, HTML formatted |
| `Example Sentence` | First example sentence in English only. **Populated for every card that belongs to a multi-card word** — if a word generates 2+ cards, each and every one of those cards must have this field filled with its own first example sentence. Leave empty only for words that produce a single card. |

---

## When to create multiple cards

A word generates **one card per meaning** only when the meanings are genuinely distinct and non-inferable from each other. Use judgment:

- **Split into separate cards**: meanings that differ significantly in part of speech AND sense, or fixed phrases/idioms whose meaning cannot be inferred from the base word (e.g. `spite` → `in spite of` shifts from malice to concession — not inferable)
- **Keep in one card**: meanings that are closely related, or forms that are easily inferred (e.g. a noun and its verbal form with the same core sense; a literal and mildly figurative use of the same word)
- **Fixed phrases / idioms**: only create a separate card if the phrase has a meaning that clearly cannot be inferred from the base word. If it can be inferred, skip it.
- When a fixed phrase gets its own card, its `Front` is the full phrase (e.g. `in spite of`), not just the base word

---

## Card Content Rules

### Front field
- The word or phrase only, standard spelling, no punctuation or decoration
- For set phrases and idioms, write them naturally (e.g. `in spite of`, `at sixes and sevens`)

### Back field — HTML formatted
Structure:

```
[part of speech]<br><br>
<b>[meaning/definition]</b><br><br>
([nuance])<br><br>
"[example sentence 1 — clear and natural]"<br>
"[example sentence 2 — literary or sophisticated]"
```

**Concrete example — bedevil (single card):**

Copyable block:
```
v.t.

to torment or harass persistently; to cause persistent confusion or distress

(implies something vexing and hard to escape; applies to both external problems and internal states)

"The technical glitches bedeviled the team for weeks."
"He was bedeviled by doubts that no outward success could dispel."
```

**Concrete example — spite (two cards: base word + set phrase):**

Card 1 Front: `spite` | Example Sentence: `She suspected he had told their boss out of spite, not out of any genuine concern.`
Card 2 Front: `in spite of` | Example Sentence: `In spite of the rain, the outdoor ceremony went ahead as planned.`

**Concrete example — cradle (two cards: noun + verb, meanings non-inferable enough to split):**

Card 1 Front: `cradle` | Example Sentence: `The baby stirred in the cradle as the afternoon light shifted across the room.`
Card 2 Front: `cradle` | Example Sentence: `She cradled the injured bird in her palms until the vet arrived.`

### Part of speech
Use standard abbreviated labels, lowercase:
- `n.` `v.` `adj.` `adv.` `v.t.` `v.i.` `idiom` `phr.`
- For words that function as multiple parts of speech in the same meaning, write e.g. `adj. / adv.`

### Meaning line
- Core definition only — what the word means, stripped of connotation
- Concise and precise; semicolons for related senses within the same meaning
- All lowercase, no trailing period
- Wrapped in `<b></b>` in HTML

### Nuance line
- In parentheses, starts lowercase
- **Strictly 1–2 short clauses** — pick the 1 or 2 most essential things to know; cut everything else
- Good: `(covers both physical and emotional suffering; implies serious rather than minor difficulty)`
- Good: `(more formal than "statement"; can refer to a single word or a full speech act)`
- Bad: long explanations covering register, collocations, literary criticism, distinctions, and usage all at once
- If forced to choose, prioritize: what makes this word distinct, and any non-obvious usage constraint

### Example sentences
Two sentences per card:
1. **Clear and natural** — everyday register, modern prose, meaning immediately obvious
2. **Literary or sophisticated** — elevated register, novel/essay quality

- **Keep sentences short** — 1 clean clause is better than 2 sprawling ones; avoid subordinate clauses piled on subordinate clauses
- Wrap each in `"double quotes"`
- Do not label them (no "Example 1:" prefix)
- Sentences should be original, not lifted from known texts
- The word may appear in inflected form

---

## Mode 1: Single Word

Output one copyable block per card (no file). Use triple backticks. Use blank lines as spacing between sections:

````
```
[part of speech]

[meaning/definition]

([nuance])

"[natural example sentence]"
"[literary example sentence]"
```
````

If the word generates multiple cards, output each as its own separate block, with a note above each indicating what goes in the `Example Sentence` field:

```
**Card 1** — Example Sentence field: "[first example sentence]"
[block]

**Card 2** — Example Sentence field: "[first example sentence]"
[block]
```

After the block(s), add nothing unless something genuinely unusual warrants a one-liner note.

---

## Mode 2: Batch (list of words)

When the user sends multiple words for batch processing:

1. Process each word fully (same quality as single mode)
2. Generate a tab-separated `.txt` file importable by Anki Desktop
3. Output **only the file** — no copyable blocks in chat

### File format
```
#separator:tab
#columns:Front	Back	Example Sentence
bedevil	v.t.<br><br><b>to torment or harass persistently; to confound or perplex someone to the point of distress</b><br><br>(often implies a sense of being plagued by something vexing and inescapable)<br><br>"The technical glitches bedeviled the team for weeks before they found the root cause."<br>"He was bedeviled by doubts that no amount of outward success could dispel, a quiet torment invisible to those who admired him."	
spite	n.<br><br><b>a desire to hurt, annoy, or offend someone; petty ill will or malice</b><br><br>(implies small-minded, often irrational motivation driven by wounded pride or resentment; distinguished from deeper hatred by its pettiness and reactive quality; "out of spite" is the most common phrasing)<br><br>"She suspected he had told their boss out of spite, not out of any genuine concern."<br>"He maintained the feud long after its origins had faded, fueled now by nothing more sustaining than spite."	She suspected he had told their boss out of spite, not out of any genuine concern.
in spite of	phr.<br><br><b>despite; regardless of</b><br><br>(concessive phrase; equivalent to "notwithstanding"; formal enough for written prose; meaning is not inferable from the noun sense of spite)<br><br>"In spite of the rain, the outdoor ceremony went ahead as planned."<br>"She succeeded in spite of every disadvantage her circumstances had arranged against her."	In spite of the rain, the outdoor ceremony went ahead as planned.
```

- Each row = one card
- Words that generate multiple cards = multiple rows (different Front if it's a set phrase, same Front if it's a different part of speech)
- `Example Sentence` column: empty for single-card words; for multi-card words, **every row** gets its own first example sentence — no row from a multi-card word should ever have this column empty
- Back field: all on one line, HTML line breaks as `<br>`, no actual newlines inside the field
- Save as `.txt`, UTF-8 encoding

### Importing into Anki Desktop
**File → Import** → select `.txt` file → map fields if needed → Import.

---

## Quality Checklist (apply to every card)

- [ ] Front is clean — word or full phrase only
- [ ] Part of speech accurate, standard abbreviation, lowercase
- [ ] Meaning line: core definition only, lowercase, no trailing period, in `<b></b>`
- [ ] Nuance line: in parentheses, lowercase start, concise but complete
- [ ] Meaning and nuance don't repeat each other — meaning states *what*, nuance states *how/when/character*
- [ ] Split-card decision is justified — only split when meanings are genuinely non-inferable
- [ ] Set phrases only get their own card if meaning can't be inferred from the base word
- [ ] `Example Sentence` field populated (with first example, English only) for **every** card of a multi-card word — if a word generates 2 or 3 cards, ALL of them must have the Example Sentence filled; empty only for words that produce a single card
- [ ] First example is clear, natural, modern register
- [ ] Second example is literary or sophisticated in register
- [ ] Both examples feel original and illustrate the word precisely
- [ ] Example sentences in double quotes, on separate lines
- [ ] Back field HTML valid — `<br><br>` between each section, `<br>` between the two examples
