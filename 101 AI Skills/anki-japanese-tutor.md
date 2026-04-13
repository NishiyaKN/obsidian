---
name: anki-japanese-tutor
description: Creates perfectly formatted Anki cards for Japanese vocabulary and grammar study. Use this skill whenever the user sends a Japanese word, expression, verb, adjective, noun, or grammar point and wants an Anki card or anki block created. Also triggers for batch card creation when the user sends a list of Japanese words/grammar points to be turned into an importable Anki .txt file. Trigger on any request involving Japanese vocab cards, Anki blocks, Japanese flashcards, or Japanese study cards — even if phrased casually like "make a card for 壊す" or "batch create these words for Anki".
---

# Anki Japanese Tutor Skill

Creates Anki-ready cards for Japanese vocabulary and grammar points, with two modes: **single** (copyable block) and **batch** (importable `.txt` file).

---

## Anki Note Type: 3 Fields

The user's Anki note type has exactly these fields, in this order:

| Field | Content |
|---|---|
| `Front` | The word/expression in kanji/kana as written (e.g. `壊す`) |
| `Back` | Hiragana reading + 他動詞/自動詞 tag (if applicable) + meaning + nuance + 2 example sentences with translations, formatted in HTML |
| `Example Sentence` | The **first Japanese example sentence from that card's Back field**, copied verbatim, no translation. **Populated for every card that belongs to a multi-card word** — if a word generates 2+ cards, each and every one of those cards must have this field filled. Never use a label, tag, or summary (e.g. never write `達者 (skilled)` — copy the actual sentence `彼女は口が達者で、どんな議論でも丸め込んでしまう。`). Leave empty only for single-meaning words that produce a single card. |

---

## Card Content Rules

### Front field
- Use the word's standard written form (kanji if it has one, otherwise kana)
- Do NOT include reading, meaning, or tags here

### Back field — HTML formatted
Use `<br>` for line breaks and `<b>` for the meaning line. Structure:

```
[hiragana reading] ([他動詞 or 自動詞, if applicable])<br><br>
<b>[meaning1], [meaning2], ...</b><br><br>
([nuance explanation])<br><br>
[example sentence 1 in Japanese]<br>
[translation of example 1]<br><br>
[example sentence 2 in Japanese]<br>
[translation of example 2]
```

### Formatting rules (strictly enforce)
- **Meanings**: all lowercase, comma-separated (e.g. `to break, to destroy, to wreck`)
- **Nuance**: inside parentheses, starts lowercase (e.g. `(actively causing something to break...)`)
- **Nuance style**: ultra-concise — use `e.g.` not `for example`, drop filler like `describes a situation where`, get to the point fast, but ensure it's complete enough to understand usage
- **Example sentences**: natural, clear Japanese. No furigana needed.
- **Translations**: natural English, not overly literal

### Transitive/Intransitive verbs
- If the verb is part of a transitive-intransitive pair, always tag it: `他動詞` (transitive) or `自動詞` (intransitive)
- If it's a verb but NOT part of such a pair, omit the tag

### Multiple meanings
- Create **one card per distinct meaning**, but only when meanings are genuinely distinct and non-inferable from each other
- If a meaning is easily inferred from another (e.g. a verb and its derived noun form with the same core sense, or a literal and mildly figurative use), keep them in one card or skip the redundant one
- Set phrases or compound expressions: only create a separate card if the meaning cannot be clearly inferred from the base word; if it can, skip it
- Each card is fully self-contained (full nuance + 2 examples relevant to that meaning)
- The `Example Sentence` field is populated for each card (different sentence per card)

### Grammar points

Grammar cards follow the exact same structure as vocab cards, with one key difference: the first line (where hiragana goes for vocab) becomes the **grammar specification line** instead.

#### Front field
- Use the pattern as typically cited, with `～` prefix if it attaches to something (e.g. `～たるもの`, `～に反して`)
- If it's a standalone particle or expression with no attachment, just write it as-is (e.g. `こそ`, `ものの`)

#### Grammar specification line (replaces hiragana in Back field)
This line must make the attachment rules immediately clear. Follow these conventions:

| Attaches to | Write |
|---|---|
| Noun | `N + たるもの`, `N + として` |
| Verb dictionary form | `V-ru + ものの` |
| Verb ta-form | `V-ta + とたん` |
| Verb te-form | `V-te + はじめる` |
| Na-adjective (with な) | `Adj-na + な + ものの` |
| Na-adjective (with に) | `Adj-na + に + 反して` |
| I-adjective (full form) | `Adj-i + くせに` |
| I-adjective (stem, drops い) | `Adj-i (stem) + さ` |
| Multiple attachment types | `N/Adj-na + である + ものの` or list each |
| Optional element | Use parentheses: `V-ru + (の) + なら` |

**Real example — ～たるもの:**
```
N + たるもの
one in the capacity of, as a
(formal; implies that someone holding a specific role or high status must behave accordingly; "because you are X, you should naturally do Y"; used for roles like 教師, リーダー, 親)
教師たるもの、常に学生の模範となるべきだ。
As a teacher, one should always be a model for students.
一国のリーダーたるもの、国民の安全を第一に考える必要がある。
As a leader of a nation, one must put the safety of the people first.
```

#### Nuance for grammar points
- Explain the core meaning/feeling the pattern conveys
- Note register (formal/written/spoken/literary) if relevant
- Compare to similar patterns if it helps distinguish usage (e.g. "stronger than ～として, which is more neutral")
- Keep concise — same rules as vocab nuance

---

## Mode 1: Single Word or Grammar Point

Output a plain copyable block (no file). Use triple backticks for easy copy-paste.

**Format:**
````
```
[hiragana] ([他動詞/自動詞 if applicable])
[meaning1], [meaning2], ...
([nuance])
[example sentence 1]
[translation 1]
[example sentence 2]
[translation 2]
```
````

If the word has multiple meanings, output **one block per meaning**, clearly separated, each complete.

After the block(s), do NOT add lengthy explanations. A one-liner note is fine if something genuinely unusual needs flagging (e.g. "Note: this verb has no transitive counterpart").

---

## Mode 2: Batch (list of words/grammar points)

When the user sends multiple words/grammar points for batch processing:

1. Process each item fully (same quality as single mode)
2. Generate a tab-separated `.txt` file importable by Anki Desktop
3. Output **only the file** — no copyable blocks, no per-card text output in chat

### File format

```
#separator:tab
#columns:Front	Back	Example Sentence
壊す	こわす (他動詞)<br><br><b>to break, to destroy, to wreck, to damage (health)</b><br><br>(actively causing something to break, malfunction, or fail; applies to objects, relationships, or physical condition)<br><br>弟が私のお気に入りの時計を壊してしまった。<br>My younger brother broke my favorite watch.<br><br>働きすぎて体を壊さないように気をつけてください。<br>Please be careful not to ruin your health by working too hard.	
達者	たっしゃ<br><br><b>skilled, proficient, adept</b><br><br>(highly capable in a particular area; implies natural ease and polish; e.g. 口が達者 "has a way with words")<br><br>彼女は口が達者で、どんな議論でも丸め込んでしまう。<br>She has a real way with words and can talk her way out of any argument.<br><br>踊りが達者な祖母は、祭りになると必ず舞台に上がる。<br>My grandmother, a skilled dancer, always takes to the stage at festivals.	彼女は口が達者で、どんな議論でも丸め込んでしまう。
達者	たっしゃ<br><br><b>healthy, in good health, hale and hearty</b><br><br>(good physical condition esp. for the elderly; most common in お達者で; warmer than 健康)<br><br>祖父は八十を過ぎても達者に畑仕事をしている。<br>Even past eighty, my grandfather is hale and hearty and still tends the fields.<br><br>離れて暮らす親に「いつまでもお達者で」と手紙に書いた。<br>I wrote to my parents far away: "Please stay healthy always."	祖父は八十を過ぎても達者に畑仕事をしている。
```

**CRITICAL — Example Sentence column rules:**
- For a single-card word (壊す above): leave the Example Sentence column **empty**
- For a multi-card word (達者 above): every single row must have the **first Japanese sentence from that card's Back field copied verbatim** into the Example Sentence column
- `達者 (skilled)` ❌ — never a label
- `彼女は口が達者で、どんな議論でも丸め込んでしまう。` ✅ — the actual sentence
- Both 達者 rows get a sentence — not just one of them

- Each row = one card
- Multi-meaning words = multiple rows (same Front, different Back + Example Sentence)
- `Example Sentence` column: empty for single-meaning words, populated for multi-meaning
- Back field: all on one line, line breaks as `<br>`, no actual newlines inside the field
- Save as `.txt`, UTF-8 encoding

### Importing into Anki Desktop
User goes to: **File → Import** → select the `.txt` file → map fields if needed → Import.

---

## Quality Checklist (apply to every card)

- [ ] Meanings all lowercase, comma-separated
- [ ] Nuance in parentheses, starts lowercase, concise but complete
- [ ] 他動詞/自動詞 tagged correctly (only when part of a pair)
- [ ] Both example sentences are natural and clearly illustrate the meaning/nuance
- [ ] Multi-meaning words have separate cards, each with its own Example Sentence populated — the actual first Japanese sentence from that card's Back, copied verbatim, never a label or tag
- [ ] Grammar points: specification line uses correct shorthand (N, V-ru, V-ta, Adj-na, Adj-i (stem), etc.) and all required particles/copulas are explicit; optional elements in parentheses
- [ ] Grammar points: register (formal/written/spoken) noted in nuance if relevant
- [ ] Back field HTML is valid — `<br><br>` between each section (reading → meaning → nuance → examples), `<br>` between a Japanese sentence and its translation, `<br><br>` between the two example pairs
- [ ] No furigana in example sentences
