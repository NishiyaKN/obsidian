---
name: jp-vocab-classifier
description: Classifies Japanese vocabulary lists from immersion (anime, manga, light novels, visual novels, etc.) into three frequency tiers — Common, Rare, Unusual — to help prioritize Anki card creation. Use this skill whenever the user sends a list of Japanese words and wants them classified, sorted, triaged, or prioritized by frequency or usefulness. Also triggers when the user says things like "classify these words", "sort this vocab", "which of these should I learn first", "triage this list", "prioritize these", or sends a raw list of Japanese words with the expectation of classification. Trigger even if the user just pastes Japanese words without explicit instructions — if a previous conversation established the classification workflow, assume they want classification.
---

# Japanese Vocab Classifier

Classifies Japanese vocabulary extracted from immersion material (anime, manga, light novels, VNs, etc.) into three priority tiers based on real-world frequency and immersion utility.

---

## User Profile (hardcoded context)

- **Current level**: JLPT N3 certified, working toward N2 → N1
- **Anki deck**: ~4.5k mature words
- **Source material**: Anime, manga, and other Japanese immersion content
- **Goal**: Efficient Anki prioritization — add the most useful words first

---

## The Three Tiers

### 🟢 Common
Words the user is **most likely to encounter again soon** in immersion and daily Japanese. These go into Anki first.

A word is Common if it meets **most** of these criteria:
- Appears in general-purpose frequency lists within the **top ~10,000–15,000** most used words
- Shows up **regularly across multiple genres** of anime/manga (not confined to one setting)
- Would be understood and used by an average Japanese adult in **everyday conversation, news, or writing**
- Falls within JLPT N3–N1 vocabulary lists (but JLPT alone is not sufficient — frequency in real usage matters more)
- Is the kind of word that, once learned, the user will see **multiple times per week** during active immersion

**Examples of Common words**: 覚悟 (resolve), 裏切る (to betray), 手遅れ (too late), 偶然 (by chance), 油断 (carelessness), 邪魔 (hindrance), 諦める (to give up)

### 🟡 Rare
Words that appear in immersion **occasionally** but are not everyday vocabulary. Add to Anki only when there are no Common words waiting.

A word is Rare if it meets **most** of these criteria:
- Falls roughly in the **15,000–30,000** frequency range, or is common only within specific domains
- Appears in anime/manga **periodically** — maybe a few times across a full series, not every episode/chapter
- A Japanese adult would recognize it but might not use it in casual conversation (more typical of **written language, formal speech, or specific genres**)
- Often genre-weighted: frequent in battle shonen, historical drama, or mystery but uncommon in slice-of-life or daily conversation
- Learning it adds depth but won't unlock frequent comprehension gains immediately

**Examples of Rare words**: 凛々しい (dignified/gallant), 采配 (command/direction), 暗躍 (scheming behind the scenes), 志 (ambition/aspiration, in its literary sense), 愚弄 (to make a fool of)

### 🔴 Unusual
Words that are **very infrequent** even within immersion. Lowest priority — add only when Common and Rare queues are empty.

A word is Unusual if it meets **most** of these criteria:
- Falls **beyond the top 30,000** in frequency, or is effectively absent from general-purpose frequency data
- Appears in anime/manga **rarely** — maybe once in an entire series, or only in very niche works
- Is **archaic, dialectal, highly literary, technical jargon, or character-specific catchphrases** that don't generalize
- A typical Japanese adult might not immediately recognize it, or would consider it obscure
- Often includes: classical/literary verb forms, obscure kanji compounds, ultra-specialized terminology (e.g., specific sword techniques, esoteric Buddhist terms, old military ranks)

**Examples of Unusual words**: 矜持 (pride, literary), 罷免 (dismissal from office), 忌憚 (reserve/hesitation, literary), 畢竟 (after all, archaic), 韋駄天 (incredible speed, Buddhist origin)

---

## Classification Method

For each word in the list, apply this decision process:

### Step 1 — Normalize to dictionary form
If the word is conjugated (past tense, volitional, te-form, passive, causative, etc.), convert it to its **dictionary/root form** before classifying.

**Exceptions — do NOT convert to root form:**
- Set phrases, idioms, or collocations where the conjugated form IS the standard expression (e.g., 言わんばかり, 目が覚める as a phrase, しょうがない)
- Compound expressions that lose meaning when decomposed (e.g., ～てたまらない, ～ざるを得ない)
- Words where the inflected form is lexicalized as its own entry (e.g., 慌てて used adverbially)

### Step 2 — Assess frequency
Consider these signals (in rough order of reliability):
1. **Corpus frequency**: Where does this word fall in Japanese frequency rankings? (newspapers, web corpora, subtitle corpora)
2. **JLPT level association**: N5–N3 words lean Common; N2–N1 lean Common-to-Rare; words beyond JLPT scope lean Rare-to-Unusual
3. **Genre breadth**: Does it appear across many genres or only in specific ones?
4. **Spoken vs. written skew**: Words common in speech rank higher for immersion usefulness than words confined to formal writing
5. **Anime/manga frequency specifically**: Some words are disproportionately common in fiction vs. real life (e.g., 魔王, 結界) — weight these toward Common if they genuinely appear often in immersion, even if rare in daily conversation

### Step 3 — Assign tier
Use the tier definitions above. When a word is borderline:
- Between Common and Rare → **lean Common** (it's better to prioritize a borderline word than to delay it)
- Between Rare and Unusual → **lean Rare** (same logic — when in doubt, promote)

### Step 4 — Deduplicate
If the same word appears multiple times in the list (possibly in different conjugations), include it **only once** in its dictionary form.

---

## Output Format

Present exactly **three copyable code blocks**, one per tier, in priority order. Each block contains only the words (one per line), no readings, no meanings, no numbering.

If a tier has zero words, still show the header but write `(none)` inside the block.

### Template:

```
🟢 Common — add to Anki first
```
```
[word1]
[word2]
[word3]
```

```
🟡 Rare — add when no Common words are pending
```
```
[word1]
[word2]
```

```
🔴 Unusual — lowest priority
```
```
[word1]
[word2]
```

### After the blocks

Add a **brief summary line** with counts only:
`Common: X | Rare: Y | Unusual: Z`

Do NOT add per-word explanations, translations, or justifications unless the user explicitly asks for them. Keep it clean.

---

## Edge Cases

### Words that are actually expressions or grammar points
If the user sends something that is more of a grammar pattern than a vocabulary word (e.g., ～ざるを得ない, ～に違いない), classify it as-is without decomposing. These still get tiered by frequency.

### Onomatopoeia (擬音語・擬態語)
Classify normally by frequency. Many onomatopoeia are extremely common in manga (ドキドキ, ぼんやり) while others are rare (おどおど). Don't auto-promote just because it's onomatopoeia.

### Katakana loanwords
Classify normally. Some are very common (サボる, テンション), others are niche.

### Proper nouns, character names, place names
**Exclude** these entirely from classification. If spotted, silently drop them — don't list them in any tier.

### Words the user likely already knows
Per user preference: classify all words equally regardless of perceived current knowledge. Do not flag or skip words that seem "too easy."

---

## What NOT to do

- Do NOT add readings (hiragana) to the output
- Do NOT add English meanings to the output  
- Do NOT number the words
- Do NOT add explanations per word (unless asked)
- Do NOT reorder words within a tier (keep the order they appeared in the input)
- Do NOT create files — output in chat only
- Do NOT second-guess the user's immersion source — if they send the word, classify it