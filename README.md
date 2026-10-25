# Schalowitsk

Schalowitsk is a made-up language. It mixes English-style sentences with German-style rules.

This repo holds the word list and the rule book for it. You can use them to learn the language, or to build a translator.

## Files

| File | What it is |
| :--- | :--- |
| `Dictionary.json` | The word list. 1,390 entries. |
| `Lexicon.md` | The rule book. It also works as a spec for an AI translator. Version 10.1. |

## Dictionary.json

Each entry has five fields:

| Field | Meaning |
| :--- | :--- |
| `english` | The English word. Close meanings are split with `/`. |
| `schalowitsk` | The Schalowitsk word. |
| `part_of_speech` | noun, verb, adj, adv, pron, num, and so on. |
| `pronunciation` | How to say it. |
| `notes` | Short usage note. |

Sample entry:

```json
{
  "english": "accept",
  "schalowitsk": "akzept",
  "part_of_speech": "verb",
  "pronunciation": "ak-zept",
  "notes": "Verbal root; follows Schalowitsk invariant verb pattern."
}
```

## Lexicon.md

The rule book is split into modules. Some of them:

- **Iron Laws:** rules that must never be broken.
- **Pipeline:** the steps to follow when translating a sentence.
- **Pronouns and helpers:** the small words that carry tense.
- **Clause frames:** word order for main and sub clauses.
- **Negation, questions, commands:** how to say no, ask, and request.
- **Noun phrases and morphology:** plurals, possessives, and how words are built.
- **Numbers:** a rule to build numbers up to 999,999,999.
- **Word coining:** how to make a new word when one is missing.
- **Gold suite:** test sentences with the right answers.
- **Open gaps:** things the language does not cover yet.

## How the language works

1. Word order is like English: subject, verb, object.
2. Verbs do not change. Tense comes from a small helper word, or a pronoun that already has it fused in.
3. A few parts are German-style: the verb goes second after a time or place word, the verb goes last in sub clauses, and modal verbs take an `-en` ending on the main verb.
4. Words are built by rules, such as plurals, agent nouns, and numbers. Do not guess them.
5. The word list is closed. A missing word can only be made with the coining rules.

## Example

| English | Schalowitsk |
| :--- | :--- |
| I play Roblox today. | `Yem spile Roblox heute.` |
| I played Roblox. | `Ya shoun spile Roblox.` |
| I will play Roblox. | `Yeht spile Roblox.` |
| Today I play Roblox. | `Heute doun Ya spile Roblox.` |
| Today I do not play Roblox. | `Heute doun Ya spilenu Roblox.` |
| I have to play with my brother. | `Yem muss mit briv av'mi spilen.` |
| If you go, then I go. | `Wehn Su gehk doun, dashe Yem gehk.` |

What to notice:

- `Yem` is "I" with present tense built in. `Ya` is plain "I", so it needs a helper in other tenses.
- `shoun` marks the past. `Yeht` means "I" plus the future.
- `spile` stays the same in every sentence.
- After `Heute` (today), the helper `doun` comes second and `Ya` comes after it.
- `-nu` on the verb makes it negative.
- With `muss` (have to), the main verb goes last and ends in `-en`.

## Pronunciation

| Letters | Sound |
| :--- | :--- |
| `jk` | A rolling "r" from the throat. |
| `j` | "y" as in *yellow*. |
| `ch` | A thick "sh" with round lips. |

More are in Module 5 of `Lexicon.md`.

## Basic words

| English | Schalowitsk |
| :--- | :--- |
| Hello | `Halo` |
| Goodbye | `Adjo` |
| Yes | `Jak` |
| No | `Nu` |

## Notes

- New words in recent versions were checked only against `Lexicon.md`.
- Check Module 26 for known gaps before you rely on a rule.
