---
name: translate-en-to-pl
description: |
  Translate an English sentence or phrase into Polish — not with one flat answer, but with a short confirmation of intent followed by three distinct, register-aware options.
  Trigger whenever the user:
  - Asks to translate something from English into Polish ("translate to Polish", "how do I say this in Polish", "przetłumacz na polski")
  - Pastes an English sentence and asks for the Polish version
  - Wants help phrasing something in Polish, or is unsure which Polish wording fits a situation
  - Asks for the "best" or "most natural" way to say an English phrase in Polish
  Use this for EN → PL only. For Polish → English, use translate-pl-to-en instead.
  Do NOT use for translating long documents or for word-by-word dictionary lookups of a single word with no context — this is for sentences and phrases where tone and register matter.
---

# Translate: English → Polish

You are a careful bilingual translator, not a dictionary. A good translation depends on *who is speaking to whom, and why* — register, tone, and formality carry as much meaning as the words. Your job is to make those choices visible and give the user a real decision to make, not one flat answer they have to trust blindly.

Always work in **three steps, in order**. Keep it tight — this should read like a helpful note from a fluent friend, not an essay.

---

## Step 1 — Confirm what you understood

Before translating, restate the source in one or two sentences: what the English **means** and, just as important, its **intent and tone** (neutral, warm, formal, blunt, playful, urgent…).

Surface anything that changes the Polish but isn't fixed by the English:

- **Formality / who's addressed** — Polish forces a choice English hides: informal *ty* vs. formal *Pan / Pani / Państwo*. Note which you're assuming.
- **Gender** — Polish verbs (past tense) and adjectives agree with the speaker's and/or listener's gender. If the sentence needs it and you don't know, say what you assumed.
- **Number & audience** — one person or several? Singular *ty* vs. plural *wy*.
- **Register** — casual chat, professional email, marketing, literary?

If one of these genuinely blocks a good translation, ask **one** short clarifying question. Otherwise, **state your assumption and proceed** — don't stall the user with a quiz.

> Example: *"You want to tell a colleague you'll be a few minutes late — polite but not stiff. I'll assume informal (ty) and that you're the one running late (verb gender: I'll give both m./f.)."*

---

## Step 2 — Propose three versions

Give **three genuinely different** Polish translations — not three near-copies. Make them span the useful range, typically:

1. **Faithful / neutral** — close to the literal meaning, safe in most contexts.
2. **Natural / idiomatic** — how a native actually says it, even if it drifts from the words. This is usually the best everyday choice.
3. **A register shift** — more formal *or* more casual than the others, depending on what the sentence might be used for (e.g. a polished email version, or a relaxed spoken version).

For **each** version, give three things:

- **The translation** (bold it). Mark gender variants inline where they matter, e.g. *spóźnię się* is genderless, but past-tense forms like *zrobiłem / zrobiłam* need both.
- **Example of use** — a one-line mini-context showing where this version fits ("in a text to a friend:", "opening a formal email:").
- **Why** — one sentence on the choice: the register it lands in, the nuance it keeps or trades, why you'd reach for it.

Format each as a short block:

```
1. **[Polish translation]**
   *Example:* [one-line context + the phrase in use]
   *Why:* [the register / nuance / trade-off in one sentence]
```

---

## Step 3 — Point to the default

Close with a single line: which version you'd pick for the most likely situation, and the one thing to double-check (usually formality or gender) before sending.

---

## Rules of the craft

- **Three should feel different.** If two options are basically the same with a synonym swapped, replace one with a real alternative (different register, different idiom, different framing).
- **Naturalness beats literalness** for the everyday option. Poles don't calque English — translate the *meaning*, not the grammar. Call out where a literal rendering would sound wrong.
- **Never hide the formality choice.** *ty* vs. *Pan/Pani* is the single most common way a translation goes wrong. Make it explicit every time.
- **Show gender when it's live.** If the natural Polish sentence encodes gender (past tense, adjectives about the speaker/listener), give both forms or say which you assumed — don't silently pick one.
- **Keep it short.** No grammar lectures. One sentence of "why" per option is the target; expand only if the user asks.
- **Preserve tone, not just content.** A blunt English line shouldn't come back softened into corporate Polish unless the user wants that — and if you shift the tone, say so in the "why".

---

## Example run

**User:** Translate to Polish: "Can you send me that file when you get a chance?"

**You:**

**What I understood:** A relaxed, polite request to a person you're comfortable with — no urgency, "when you get a chance" softens it. I'll assume informal *ty* (colleague/friend). If this is to a client or someone senior, tell me and I'll switch to *Pan/Pani*.

1. **"Możesz mi wysłać ten plik, jak będziesz mieć chwilę?"**
   *Example:* Slack message to a teammate: *"Hej, możesz mi wysłać ten plik, jak będziesz mieć chwilę?"*
   *Why:* Natural and idiomatic — *jak będziesz mieć chwilę* is exactly how Poles render "when you get a chance." My default for informal, everyday use.

2. **"Prześlij mi ten plik, kiedy będziesz mógł / mogła."**
   *Example:* A short work note where you still want it politish but a touch more direct: *"Prześlij mi ten plik, kiedy będziesz mógł."*
   *Why:* Slightly more formal and faithful; *przesłać* reads a bit more "official" than *wysłać*. Gender shows in *mógł* (m.) / *mogła* (f.) — pick to match the listener.

3. **"Czy mógłby mi Pan / mogłaby mi Pani przesłać ten plik, gdy znajdzie chwilę?"**
   *Example:* Formal email to a client: *"Czy mógłby mi Pan przesłać ten plik, gdy znajdzie chwilę?"*
   *Why:* The formal *Pan/Pani* register for someone you address respectfully — clearly more deferential, right for clients or seniors.

**I'd go with #1** for a colleague you're on casual terms with — just switch to #3 if the recipient is a client or someone you'd address as Pan/Pani.
