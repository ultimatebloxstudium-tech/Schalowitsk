# Schalowitsk Master Lexicon & AI Translation Specification

**Edition:** 10.1 "Roles Edition" (built on 10.0)
**Revision note (10.1):** New Module 28 (roles and identity). A new verb `bist` ("to be [someone]") is required for identity predicates: nationality, job, title, role, name and relationship (`ROL-1` to `ROL-12`). Female role nouns take `-in` / `-ka` by ending letter (`ROL-4`). Role compounds such as `sicherbremol` are fixed (`ROL-12`). The hortative "Let's" is now `lez Yal` (`HRT-1`, closes G-11). "Who are you?" now takes `bist` (QST-5, `ROL-7`). `-in` was added to the GEN-4 female endings. Modal subject tokens by tense (`MOD-17`, `MOD-18`, closes G-13). General compounds are plain glue, two elements maximum, no apostrophe (`MOR-4`, `MOR-4e`, closes G-05). Decimals (`mavud`), fractions (ordinal + `halb`) and percent (`prozent`) are generated (`NUM-11` to `NUM-13`). Millions (`[1-999] milion`) and negatives (`minus`) were added (`NUM-14`, `NUM-15`), so G-04 is closed up to 999,999,999. "No X" is the new determiner `kein` / `keine` (`NEG-11`) and plain copula negation is `nucht` after the helper (`NEG-12`), closing G-10. `lyuba` is negated with `-nu` on `lyuba` itself (`LNEG-1`, closes G-33). Capitalization was tightened (`ORT-4`, `NUM-5`): tens are lower-case, demonym nouns are capitalized and demonym adjectives are lower-case, and new-sentence capitals follow colons, quotes and bullets but not commas. Past unreal: `shoun konj` in the if-clause and `shoun wurd` in the result (`SBJ-2`, closes G-41). Gaps G-05, G-10, G-11, G-13, G-27 updated; G-42 to G-45 added.
**Edition history:** 10.0 "Completion Edition" (built on 9.5)
**Revision note (10.0):** Eight open gaps were closed by owner decision (new Module 27, rules `MNEG-1`, `MFUT-1`, `PREP-N1`, `PAS-1`, `CND-1`, `NUM-10`, `ORD-1`, `SUF-1`, `RFL-7`, `POSF-1`). Modal negation is now a `-nu` suffix on the modal; modals take `geht` for the future; six prepositions were coined (`radi`, `na`, `posle`, `ohne`); a subjunctive helper `konj`; a passive helper; a conditional helper `wurd`; numbers to 999,999 and regular ordinals; `esselb` / `etselb` (itself); free-standing possessives; the suffixes `-heit` (-ness) and `-isk` (-ish). Rules MOD-4, MOD-10, MOD-11, PRP-1, NUM-6, TNS-6 and gaps G-01 to G-04, G-08, G-19, G-35 were updated. All new words are fixed text and were checked only against this file (G-40).
**Revision note (9.5):** Built from a review of `translation_log.json`. New Module 2.7 (lemma-first lookup: an inflected English form never gets its own word, so `has` = `haben`); a stricter coining gate (COIN-1 items 4 to 6); Iron Laws L27 to L31; `Su` / `Ben` always take `doun` (FIN-5a); `Yeht` and the other fused forms belong to one pronoun each (FIN-11); `tyern` = do (FIN-12); `lyuba` + `-en` frame (MOD-16); adjectives are never verbs (ADJ-5); subject-WH, copular-WH and embedded-manner questions (QST-14 to QST-16); acronym and name rules (NAM-7, NAM-8); non-English input (OUT-7); anti-patterns 81 to 112; Gold tests G-118 to G-148; audit section H.
**Revision note (9.4):** The question system was rebuilt (Module 12). Every question now needs one **question helper** in both registers (HLP-1 to HLP-8): Yes/No `chez`/`kez`, WH `chel`/`kel`, How `chaz`/`kaz`, Tag `chom`/`kom`. New constructions: tag questions (QST-9), embedded questions with `obe` (QST-10), quantity and degree questions with `viel`, `melok`, `grad` (QST-7), standalone "which" with `wehl` and "whose" (QST-12). Rules L16, REG-2, REG-3, QST-1 to QST-8, MOD-9, POS-6 and COIN-1 changed; every question example was re-written; Modules 19 to 26 were updated.
**Revision note (9.3):** Two-gender articles were added (Module 10.2A, rules GEN-1 to GEN-8). `den` is neutral-male, `deny` is female, `ein` becomes `eine` for female nouns, and the three fused prepositions gain `tu'deny`, `en'deny`, `zu'deny`. Gender comes from the noun's ending (or a person's natural gender); plurals keep the singular's gender. Examples throughout were re-gendered. Rules L13, NP-2, PRP-2, ORT-2, PLU and gap G-18 were updated.
**Revision note (9.2):** Module 16A (Controlled Word Coining) was added. A missing content word is now coined by a fixed procedure instead of being output as `[UNKNOWN]`. The Luau reference code was removed; Module 14.9 now holds plain-language test vectors. Rules L21, LEX-2, LEX-4, DIC-2, OUT-3, STEP 3 and Audit G1 were updated to match.
**Revision note (9.1):** The eight indefinite pronouns were respelled as one systematic set (`alkto`/`mankto`/`irgkto`/`nimkto`, `alscht`/`manscht`/`irgscht`/`nikscht`). The old forms are retired (Module 19.2).
**Supersedes:** Lexicon v9.1, v8.0 (Machine Execution), v7.0 (Ultimate), v6.0, v5.0 (Inseparable Prefix Update) and Guide V3.0. Every rule from every earlier file is merged here. Rules that later versions silently dropped have been restored.
**Lexical authority:** `Dictionary.json` (a separate file, 1,762 entries). This file teaches the **rules**; the dictionary supplies the **words**. Where they disagree on a word, the dictionary wins (Module 2.3).
**Audience:** Generative AI translators, validators and parsers. Humans may read it too.
**Design goal:** An AI that follows this file literally cannot produce an English-syntax leak, a double helper, a misplaced `Schalowit`, a broken V2/modal/subordinate frame, or an uncontrolled invented word.

---

## MODULE 0 - READING PROTOCOL (READ THIS FIRST)

### 0.1 What Schalowitsk is, in five lines
1. Word order is **English-like SVO by default**. You map Schalowitsk words onto English order unless a rule below says otherwise.
2. Verbs **never inflect**. Tense lives in a small **helper** (`doun`, `dorn`, `shoun`, `shorn`, `geht`) or its fused pronoun forms (`Yem`, `Yeht`, `Yalm`, `Yahlt`, `Dehyt`).
3. Five structural behaviours are **Germanic, not English**: V2 fronting, verb-final subordinate clauses, modal framing with an `-en` infinitive, terminal `Schalowit`, and targeted imperatives.
4. Words are **built by algorithm** (plurals, nominalization, agents, numbers, prefixes). Do not guess; run the algorithm.
5. The vocabulary is a **controlled list**: `Dictionary.json` first, then the few guide-only words in Module 19. A missing content word may be coined **only** through Module 16A. Never invent roots any other way.

### 0.2 Mandatory read order
**Always load:** Module 1 (Iron Laws), Module 4 (Pipeline), Module 24 (Audit).
**Load on demand** with this router:

| If the English input contains... | Read |
| :--- | :--- |
| any clause at all | Module 6 (finite core) and Module 7 (frames) |
| "not", "n't", "never", "no one", "nothing", "nobody" | Module 8 |
| "must", "have to", "need to", "can", "want to", "going to + verb" | Module 7.4 and Module 9 |
| a time word / place phrase at the start of the sentence | Module 7.2 |
| "if", "when", "because", "that", "while", "who", "which" | Module 7.3 and 7.8 |
| a question | Module 12 |
| a command / request | Module 13 |
| "it", "there", "here" | Module 11 |
| "'s", "of", "my", "your", "their", "our", "his", "her" | Module 10.3 |
| plural nouns, "-s" | Module 10.6 and Module 14 |
| any number | Module 15 |
| a word you cannot find, or any dictionary lookup | Module 2.4-2.6, Module 16 and Module 16A |
| an inflected word ("-ing", "-ed", "-s", "has", "does") or any coining decision | Module 2.7 (LEM-1 to LEM-6), then Module 16A |
| a person, brand, game, product, place name | Module 17 |
| "I am a ...", "he is the ...", nationality, job, title, name, "my friend / brother", "Let's ..." | Module 28 |
| slang, greetings, idioms, body pain, comparatives | Module 18 |

### 0.3 Notation legend
| Symbol | Meaning |
| :--- | :--- |
| ✔ | Correct output. |
| ✘ | Forbidden output. Never produce it. |
| `[Slot]` | A position in a template. |
| Index 0 | The first token of a clause. Index 1 is the second token, and so on. |
| `S` / `H` / `V` / `O` | Subject / Helper (or finite core) / Action verb / Direct object. |
| `V-en` | The action verb in infinitive form (Module 14.3). |
| `Core` | The finite core: the subject + helper unit (Module 6). |
| Hyphens in `-nu`, `-en`, `-zung`, `-mann`, `-eni`, `an-`, `wieder-`, `aus-` | **Notation only.** Real words contain no hyphen: `spilenu`, `spilen`, `angehk`. The only literal hyphen in the language is the noun-possessor prefix `av-` (Module 10.3). |

### 0.4 Certainty tags
An example or rule with **no tag** is **CANON** (stated in at least one source file and contradicted by none).

| Tag | Meaning | What the AI does |
| :--- | :--- | :--- |
| **[RESOLVED]** | Source files disagreed. The winner was chosen by Module 2 precedence. | Follow the rule as written here. |
| **[DERIVED]** | Not stated in any source. Inferred by strict analogy from CANON rules. | Follow it. It is the best available answer. |
| **[GAP]** | Not defined anywhere. | Apply the fallback written next to it. Never improvise. |

### 0.5 Rule IDs
Every rule has an ID (`FIN-1`, `V2-3`, `NEG-2`...). Modules 21, 22 and 24 cite these IDs. In EXPLAIN or VALIDATE mode, cite them.

### 0.6 ISO-1: the Default Isomorphism Principle
> Wherever **no rule in this file overrides it**, keep the English order of clause elements and substitute Schalowitsk words one-for-one.

ISO-1 is what keeps unlisted situations safe. Adverbials stay where the English put them; modifiers stay before nouns; objects follow verbs.

### 0.7 The three questions asked of every clause
1. **What frame is this clause?** (imperative / subordinate / question / modal / V2 / plain SVO)
2. **What is the exact finite core for this person, tense and frame?** (Module 6 table lookup; never improvise)
3. **Does anything in the clause need an algorithm?** (negation, plural, derivation, number, prefix)

---

## MODULE 1 - THE IRON LAWS

These 31 laws are the failure points of earlier AI outputs. They override everything else except Module 2's precedence rules. Each is expanded later; the cited module has the full rule.

### Group A - Finite core and verbs
| # | Law | ✔ / ✘ |
| :--- | :--- | :--- |
| **L1** | **One finite core per clause.** A fused form *is* the core. Never stack a subject, a fused form and a helper. (FIN-1) | ✘ `Ya yem spile` ✘ `Yem doun spile` ✘ `Ben doun doun spile` ✔ `Yem spile Roblox.` |
| **L2** | **Fused forms (`Yem`, `Yeht`, `Yalm`, `Yahlt`, `Dehyt`) are legal only when subject and helper stay adjacent in a main clause.** In V2 and subordinate clauses use the standalone pronoun (`Ya`, `Yal`, `Dehye`) and a separate helper. (FIN-3, FIN-4) | ✘ `Heute Yem spile` ✘ `Heute doun Yem spile` ✔ `Heute doun Ya spile Roblox.` |
| **L3** | **Action verbs never inflect.** No `-s`, `-ed`, `-ing`, `-ly`. Only `-nu` (negation), `-en` (modal frame) and glued prefixes may touch a verb. (FIN-6, TNS-3) | ✘ `Yem spileing` ✔ `Yem spile` |
| **L4** | **Future uses `geht` or a fused future form. Never `gehk tu`.** (FIN-2, TNS-2) | ✘ `Yem gehk tu mek eine spilezung` ✔ `Yeht mek eine spilezung.` |

### Group B - Clause order
| # | Law | ✔ / ✘ |
| :--- | :--- | :--- |
| **L5** | **V2 fronting.** If a time word, adverbial or prepositional phrase opens a main clause, the helper moves to Index 1 and the subject to Index 2. (V2-1) | ✘ `Heute Ya spile Roblox` ✔ `Heute doun Ya spile Roblox.` |
| **L6** | **Subordinate clauses are verb-final.** After `wehn`, `wahn`, `dass`, `whilst` or a relative `Seckeh`, the helper sits at the absolute end of that clause. (SUB-1) | ✘ `Wehn Su doun gehk` ✔ `Wehn Su gehk doun` |
| **L7** | **Modal frame.** `S + modal + [every object, preposition phrase and adverbial] + V-en`. The `-en` verb is the very last word. (MOD-1, MOD-2) | ✘ `Yem muss spilen mit briv av'mi` ✔ `Yem muss mit briv av'mi spilen.` |
| **L8** | **No English infinitive.** There is no `tu + verb`. `tu` means only the preposition "to". (MOD-5) | ✘ `Yem haben tu gehk` ✔ `Yem muss verlassen!` |

### Group C - Negation
| # | Law | ✔ / ✘ |
| :--- | :--- | :--- |
| **L9** | **Negation by transitivity.** Direct object present: `V+nu O`. No direct object: `V nucht`. `alsitnu`, `nikscht`, `nimkto` already negate; add nothing. (NEG-1 to NEG-4) | ✘ `Yem spile nucht Roblox` ✔ `Yem spilenu Roblox.` ✔ `Yem spile nucht.` ✔ `Ya alsitnu iz apeleni.` |
| **L10** | **`nu` is a suffix, `nucht` is a particle, `Nu` is the word "No".** Never use standalone `nu` inside a clause. (NEG-6) | ✘ `Yem spile nu Roblox` |

### Group D - Noun phrase
| # | Law | ✔ / ✘ |
| :--- | :--- | :--- |
| **L11** | **No `'s`. Ever.** Possession uses `av`: `briv av'mi`, `deny aufsita av den konig`, `den konig av-aufsita`. (POS-1) | ✘ `konig's aufsita` |
| **L12** | **Two bifurcations.** `Et` = abstract / weather / time. `Es` = tangible object. `Dah` = existential "there is". `Daz` = physical "there". (REF-1 to REF-4) | ✔ `Et doun regen.` ✔ `Stevad Ben es!` ✔ `Dah doun ein konig.` ✔ `Gehk daz!` |
| **L13** | **Article fusion for exactly three prepositions:** `tu'den`/`tu'deny`, `en'den`/`en'deny`, `zu'den`/`zu'deny`. Nothing else fuses. (PRP-2) | ✘ `tu den aufsita` ✘ `mit'den key` ✔ `tu'deny aufsita` ✔ `tu'den konig` |
| **L14** | **Plurals by algorithm:** `-eni` / `-zeng`. Never English `-s`. After a number, the noun is plural. (PLU-1 to PLU-4) | ✘ `apels` ✔ `apeleni` ✔ `spilezeng` |

### Group E - Questions and commands
| # | Law | ✔ / ✘ |
| :--- | :--- | :--- |
| **L15** | **Interrogatives.** WH words = `Seckeh` + domain noun at Index 0. "How" = `Schalowit`, and it is the **last token before the final punctuation**. Never `Seckeh` for how; never `Schalowit` anywhere else. (QST-2, QST-4) | ✘ `Schalowit Ben doun?` ✔ `Ben doun Schalowit?` |
| **L16** | **Register.** Default = formal: `Su` and formal question helpers. Informal/gaming/casual: `Ben` and informal question helpers. (REG-1, REG-2) | ✔ `Seckeh penk chel Su doun bist?` ✔ `Seckeh penk kel Ben doun bist?` |
| **L16A** | **Question helper.** Every direct question has exactly one helper from the HLP-2 table, in both registers. No helper is an error. (HLP-1 to HLP-8) | ✔ `Kez Ben doun spile Roblox?` ✘ `Ben doun spile Roblox?` |
| **L17** | **Imperatives.** Addressed to a specific person: `V + Ben/Su + O`. General announcement: `V + O`. No subject, no helper, no V2. (IMP-1 to IMP-3) | ✔ `Stevad Ben es!` ✔ `Stevad es!` |

### Group F - Morphology
| # | Law | ✔ / ✘ |
| :--- | :--- | :--- |
| **L18** | **Verb prefixes are inseparable:** `an-`, `wieder-`, `aus-` stay glued to the verb in every position. (MOR-6) | ✘ `Yem gehk an` ✔ `Yem angehk.` |
| **L19** | **Numbers are generated, not looked up** (1-99). Tens = digit + `ik` (10 = `dezi`). Join with `n` + space, unit capitalized. (NUM-1 to NUM-3, NUM-8) | ✔ `doiwikn Nein` (29) ✔ `doiwikn Ein` (21) |
| **L20** | **Derivation algorithms.** `-zung` on a verb drops a final `e t z x d r a i`, but a **dictionary headword always wins** (`spilezung`); `-mann` attaches directly; infinitive: roots already ending in `-en` are unchanged, roots ending in `e` add `n`, all others add `en`. (MOR-1 to MOR-3) | ✔ `spilemann` ✔ `spilen` ✔ `verlassen` (unchanged) ✔ `spilezung` (headword) |

### Group G - Vocabulary and names
| # | Law | ✔ / ✘ |
| :--- | :--- | :--- |
| **L21** | **Never invent a root outside Module 16A.** Missing word: `Dictionary.json` (non-empty entry) -> Module 19 -> phrasing solution (Module 16) -> **coining (Module 16A)** -> `[UNKNOWN:word]`. A dictionary entry whose `schalowitsk` field is empty is not yet a word, so coin it under Module 16A. (LEX-1 to LEX-4, COIN-1 to COIN-9) | ✘ inventing `gamen` for "game" (the dictionary has `spilezung`) ✘ coining a word without running COIN-6 |
| **L22** | **Proper names pass through verbatim:** people, brands, games, software, products, fictional characters. (NAM-1) | ✔ `Roblox`, `Microsoft`, `John` |
| **L23** | **Zero English leakage.** Contractions are expanded and translated. No English function word (`the`, `to`, `is`, `of`, `not`...) may remain in the output. (OUT-3) | ✘ `Yem don't spile` |

### Group H - Output
| # | Law | ✔ / ✘ |
| :--- | :--- | :--- |
| **L24** | **Output contract.** Emit only the translation, keep the input's end punctuation, give one canonical translation. (OUT-1 to OUT-4) | |
| **L25** | **Capitalization.** Sentence-initial word, all subject pronouns (`Ya Yem Yeht Yal Yalm Yahlt Su Ben Er She Dehye Dehyt`), `Schalowit`, `Seckeh`, and proper names are capitalized. Everything else is lower-case mid-sentence. (ORT-4) | ✔ `Wehn Su gehk doun, dashe Yem gehk.` |
| **L26** | **Gender articles.** Two genders. `den` = neutral-male, `deny` = female; `ein` / `eine`. Gender is decided by a person's natural gender, else by the noun's last letters (vowel, `y`, `-en`, `-ung`, `-zeng`, `-heit`, `-ik` = female; `-mann`, `-er`, other consonants = `den`). Plurals keep the singular's gender. (GEN-1 to GEN-8) | ✔ `deny aufsita` ✔ `den konig` ✔ `eine key` ✔ `ein konig` ✘ `den aufsita` ✘ `ein key` |

### Group I - Added in 9.5 (found in the translation log)
| # | Law | ✔ / ✘ |
| :--- | :--- | :--- |
| **L27** | **`Su` and `Ben` always take `doun` / `shoun`.** Never `dorn` / `shorn`. `dorn` belongs only to `Yal`, `Dehye`, plural nouns and `Dehysseni`. (FIN-5a) | ✘ `Su dorn Schalowit` ✘ `Ben dorn tyern` ✔ `Su doun` ✔ `Ben doun` |
| **L28** | **Lemma first, coin last.** Reduce every English word to its dictionary form before lookup. An inflection (`-ing`, `-ed`, `-s`, `-ly`, `has`, `does`) never gets its own word, coining or dictionary entry. Coin only when the necessity test fails. (LEM-1 to LEM-6, COIN-1) | ✘ `habe` for "has" ✔ `haben` ✘ a new word for "trolling" ✔ the `troll` root |
| **L29** | **Helper matches pronoun, every time.** `Su` takes `chez` / `chel` / `chaz` / `chom`. `Ben` takes `kez` / `kel` / `kaz` / `kom`. `chez` is Yes/No only. (HLP-2, HLP-6, REG-5) | ✘ `Kez Su` ✘ `Seckeh chel Ben` ✘ `Seckeh plas chez Su` ✔ `Chez Su` ✔ `Seckeh chel Su` |
| **L30** | **The `-en` infinitive exists only at the end of a modal or `lyuba` frame.** Finite clauses and commands use the root. (MOD-16, IMP-1, MOR-3) | ✘ `Dehye dorn tu'den duvad gehken` ✘ `Schreiben Ben dehyss` ✔ `Dehye dorn gehk tu'den duvad` ✔ `Schrei dehyss` |
| **L31** | **Dictionary words beat borrowed words.** Never output a German, Russian or English word the dictionary does not list. Acronyms (`AI`, `UI`) pass through verbatim; names are not coined. (NAM-7, COIN-5, OUT-3) | ✘ `Schreiben` (dictionary: `schrei`) ✘ `verruckt` (respelled: `verrukt`) ✘ `ui` ✔ `UI` |

---

## MODULE 2 - METADATA, PRECEDENCE AND SOURCE POLICY

### 2.1 Metadata
| Field | Value |
| :--- | :--- |
| Language | Schalowitsk |
| Edition | 9.5 Dictionary-Aligned Master |
| Scope | Translation, generation, validation, parsing, morphology |
| Primary mandate | Total suppression of English syntactic structures ("English leaks") |
| Lexical authority | `Dictionary.json` (separate file) |
| Test method | Plain-language test vectors (Module 14.9) and the Gold suite (Module 22). |

### 2.2 Order of rule precedence
1. **Tier 1 - Structural constraints:** finite core and fusion rules, V2, subordinate verb-final, modal `-en` framing, negation algorithm, targeted imperatives, terminal `Schalowit`, Iron Laws.
2. **Tier 2 - Morphology and vocabulary:** inseparable prefixes, number algorithm, `-zung`, `-mann`, plurals, `Et/Es`, `Dah/Daz`, lexicon.
3. **Tier 3 - Registers and idioms:** question helpers (`chez`, `kez`, `chel`, `kel`, `chaz`, `kaz`, `chom`, `kom`), `Plis`, medical expressions, idioms, slang.

A higher tier always beats a lower tier when two rules collide.

### 2.3 Source reconciliation policy
Two different kinds of conflict exist, and each has its own ladder.

**Words (lexemes):**
1. A **non-empty `Dictionary.json` entry** beats every guide or lexicon version. (Example: the Guide's `kastelv` for "castle" is superseded by the dictionary's `aufsita`.)
2. If the dictionary is **silent**, the form attested in the guide/lexicon files is kept (`konig`, `key`, `schluessel`, `kvik`...). These are listed in Module 19.1.
3. If the dictionary entry is **empty**, there is no word yet; coin one under Module 16A (Module 2.5).
4. A **lexicalized form** (a dictionary headword or a Module 19 form) overrides any morphology algorithm. (Example: `spilezung`, not the rule-derived `spilzung`.)

**Grammar rules:**
1. **Latest source beats older source** (v8.0 > v7.0 > v6.0 > v5.0 > Guide V3).
2. **Rule text beats a contradicting example inside the same file** (the example is treated as a typo).
3. A rule or example that a newer file merely *omitted* (without contradicting it) is **kept**.
4. The dictionary may **confirm** a rule (it does for numbers, prefixes and past forms) but never overrides a grammar rule on its own notes alone (see C-30).

All resolutions are logged in Module 25.

### 2.4 Lookup order
1. Query `Dictionary.json` by the English headword (see 2.5 for how to read an entry).
2. If the dictionary has no usable entry, check Module 19.1 (guide-only words).
3. If the concept is still missing, use Module 16 (phrasing solution, LEX-3).
4. If that fails, coin a word under Module 16A.
5. If coining is excluded or fails every check, output `[UNKNOWN:word]` (LEX-4).

### 2.5 Reading a `Dictionary.json` entry
Each entry has the fields `english`, `schalowitsk`, `pronunciation`, `part_of_speech`, `notes`; names also carry `entity_type`.
- **DIC-1 Matching.** The `english` field can hold several senses separated by ` / ` (`leave / depart`). Match the input against **any** of them. Several entries can share one English word; choose by `part_of_speech` and `notes`.
- **DIC-2 Empty entries are not yet words.** If `schalowitsk` is `""`, the dictionary has no Schalowitsk word for that headword yet. Do not fill it in by guessing or by copying German/English. Use the Module 16A coining protocol instead; if coining is excluded or fails, output `[UNKNOWN:word]`. Exceptions: numerals the Module 15 algorithm generates (`ten`, `twenty`, `thirty`, `eight` are deliberately empty), `quick` (`kvik`, Module 19.1), `anything` (`irgscht`, Module 19.1).
- **DIC-3 Multi-word headwords are one unit.** `Seckeh zeit`, `shoun gehk`, `shoun trink`, `ferjed derzheni` are copied whole. Do not re-derive them.
- **DIC-4 Hyphenated headwords are verbatim.** A hyphen inside a dictionary headword (`kahn-plas`, `high-security`, `success-ful`) is part of the word (see ORT-3).
- **DIC-5 Respect sense limits in `notes`.** Examples: `volium` is volume, never loudness; `fon` is not "sound"; `stolv` is a single unit; `bofik` (wanna) is casual only. A word marked slang or casual implies the informal register (REG-1).
- **DIC-6 Lexicalized pasts and participles.** The dictionary lists some English past forms as headwords: `went` = `shoun gehk`, `drank` = `shoun trink`. These confirm the rule *helper + invariant root* (TNS-9). Participle/state entries (`built` = `urzbau`, `made` = `favr`) name a **state or participle**, not the finite past; for the finite past always use `shoun` + root.
- **DIC-7 Lexicalized loanword plurals.** Some English-derived nouns are listed with their own plural headword (`sistemz`, `strukturz`, `skilz`). If a plural **is** a headword, use it; otherwise run the plural algorithm (PLU-1).
- **DIC-8 Entities.** Entries with `entity_type` (country, continent, language, demonym) are looked up like words and never constructed (NAM-2).
- **DIC-9 Verb roots.** Many dictionary verbs already end in `-en` (`haben`, `sehen`, `denken`, `verlassen`). That is the dictionary root; it is used unchanged in every finite position and, because it already ends in `-en`, it is also its own infinitive (MOR-3).

### 2.7 Lemma-first lookup and the ban on coining inflections (new in 9.5)
- **LEM-1 Reduce first.** Before any lookup, reduce every English word to its dictionary form: plural and third person `-s` / `-es` / `-ies`, past `-ed` / `-ied`, `-ing`, adverb `-ly`, and irregular forms (`has`, `had` -> `have`; `does`, `did`, `doing` -> `do`; `was`, `were`, `been` -> `be`; `went` -> `go`; `ate` -> `eat`; `wrote` -> `write`). If the dictionary itself lists the inflected form as a headword (`went`, `drank`, `built`, `states`), DIC-6 and DIC-7 apply instead.
- **LEM-2 No word for an inflection.** An inflected English form never gets its own Schalowitsk word, coined word or dictionary entry. `has` = `haben`. `doing` = `tyern`. `chatting` = `zirkus`. `trolling` = the `troll` root. Tense, number and aspect come from the core (Module 6), the plural algorithm (PLU-1) or the frame, never from a new root.
- **LEM-3 Coin the lemma, not the surface form.** If the lemma itself is missing, coin one word for the lemma, reuse it for every inflection, and save it under the lemma.
- **LEM-4 Necessity test.** Coin only when every answer is no: (a) is the lemma in the dictionary? (b) is it a guide-only word (19.1)? (c) does a listed near-synonym keep the exact meaning? (d) can existing words express it (LEX-3, LEX-6)? (e) is it an acronym or a name (NAM-1, NAM-7)?
- **LEM-5 Verbs that must never be coined.** `have`, `has`, `had` = `haben` (past `shoun haben`; "has to" and "have to" = `muss`). Main-verb `do`, `does`, `did`, `doing` = `tyern`. `mek` means "make" only.
- **LEM-6 Dictionary defects.** If `Dictionary.json` has an entry whose English field is an inflected form while the lemma has its own entry (`has` = `habe` beside `have` = `haben`), the lemma's entry wins and the inflected entry is never output.

---

## MODULE 3 - OUTPUT CONTRACT AND MODES

### 3.1 Modes
| Mode | Trigger | Output |
| :--- | :--- | :--- |
| **TRANSLATE** (default) | Any English text with no other instruction | Only the Schalowitsk translation. |
| **EXPLAIN** | "explain", "why", "break it down", "gloss" | Three lines: (1) Schalowitsk, (2) word-by-word gloss, (3) rule IDs applied. |
| **VALIDATE** | The user supplies Schalowitsk and asks to check/fix it | List every violated rule ID with the offending token, then the corrected sentence. |
| **GENERATE** | "make a sentence/dialogue using..." | Schalowitsk sentences that pass Module 24; English glosses only if requested. |

### 3.2 Output rules
- **OUT-1** In TRANSLATE mode output the translation **only**. No greeting, no preface, no notes, no English.
- **OUT-2** Preserve the input's terminal punctuation (`.`, `!`, `?`). Preserve commas that separate clauses. Preserve line breaks; translate sentence by sentence.
- **OUT-3** The output may contain **no English words** except verbatim proper names (Module 17) and `[UNKNOWN:word]` tokens. Coined words (Module 16A) are Schalowitsk words and are legal.
- **OUT-4** Produce **exactly one** canonical translation per sentence. Use the defaults in this file (formal register, default word order variants) unless the user asked for alternatives.
- **OUT-5** Never add words that the English did not contain (no extra pronouns, no extra `Plis`; the one question helper that HLP-1 requires is not extra). Never delete content words.
- **OUT-6 Coinage log.** Only when the user writes "log new words": after the translation, add one line per coined word: `english = schalowitsk | route (A1/A2/A3/B-language) | parts`. In EXPLAIN mode, tag coined words [COINED] in line 3. Otherwise OUT-1 applies unchanged.
- **OUT-7 Non-English input.** Translate the meaning, then run the normal pipeline. German `Sie` = formal `Su`; `du` = informal `Ben`. Never copy a German word and never fuse two words into one. `Haben Sie?` -> `Chez Su doun haben?`, not `Habensu?`.

---

## MODULE 4 - THE DETERMINISTIC PIPELINE

Run these steps in order for **every** sentence. Do not skip. Do not reorder.

```
STEP 0  NORMALIZE ENGLISH
STEP 1  SEGMENT AND CLASSIFY CLAUSES
STEP 2  RESOLVE REGISTER
STEP 3  LEXICAL LOOKUP (lemmas, names, unknowns)
STEP 4  SEMANTIC CLASSIFICATION (it/there, modal, going-to, negation type, numbers)
STEP 5  MORPHOLOGY (plural, derivation, prefix, number, infinitive)
STEP 6  FRAME SELECTION AND ASSEMBLY (core lookup + slot filling)
STEP 7  NEGATION AND PRAGMATIC INSERTIONS (-nu / nucht / Ben-Su / question helper / Plis)
STEP 8  AUDIT (Module 24) AND EMIT
```

### STEP 0 - Normalize English
1. Split into sentences. Keep each sentence's end punctuation.
2. Expand contractions: `I'm` -> `I am`, `don't` -> `do not`, `won't` -> `will not`, `it's` -> `it is`, `let's` -> `let us`, `I'll` -> `I will`.
3. Mark proper names for pass-through (Module 17). Protect them from translation.
4. Reduce every inflected word to its dictionary form first (LEM-1: `has` -> `have`, `trolling` -> `troll`, `sizes` -> `size`), then reduce each verb group to **lemma + tense** (`ate`, `eaten`, `eating`, `eats` -> `eat`; past/present/future recorded separately). Continuous aspect is discarded (TNS-3). If the dictionary lists the inflected English form as its own headword (`went`, `drank`), use that headword (DIC-6).
5. Convert possessive `'s` into an `of`-relation (POS-1).
6. Strip English "do-support" (`do`, `does`, `did` used as negation/question auxiliaries). They carry no meaning in Schalowitsk.

### STEP 1 - Segment and classify clauses
For each clause decide:

```
Is it a command (no subject, base verb)?  ............ IMPERATIVE   -> Module 13
Is it introduced by if/when/because/that/while?  ..... SUBORDINATE  -> Module 7.3
Is it a relative clause (who/which/that + verb)?  .... RELATIVE     -> Module 7.8
Is it a question?  ................................... QUESTION      -> Module 12
Does it contain must/have to/can/want to + verb?  .... MODAL        -> Module 7.4
Does it open with a time/adverbial/prep. phrase?  .... V2           -> Module 7.2
None of the above  ................................... SVO          -> Module 7.1
```
A sentence can combine frames (a main clause + a subordinate clause). Classify **each clause separately**, then apply the priority table in Module 7.9.

### STEP 2 - Resolve register
Apply Module 12.1 (REG-1). Output: `FORMAL` (default) or `INFORMAL`. This chooses `Su`/`Ben`, the formal or informal question helper, `schluessel`/`key`.

### STEP 3 - Lexical lookup
Look up each lemma (Module 2.4 order). Coin missing content words under Module 16A and record them in the session coinage table (COIN-8). Record `UNKNOWN` only for words coining cannot handle. Never translate proper names.

### STEP 4 - Semantic classification
- "it": abstract/weather/time -> `Et`; tangible object -> `Es` (Module 11).
- "there": existential -> `Dah`; physical location -> `Daz` (Module 11).
- "going to": followed by a **verb** -> future helper; followed by a **place** -> motion verb `gehk` + `tu` (TNS-4).
- "must / have to / need to + verb" -> modal `muss`; "can" -> `kahn`; "want to" -> `wolt` (Module 7.4).
- "need + noun" -> ordinary verb `brauch` + object (not a modal).
- Negation words: classify as transitive / intransitive / absolute (Module 8).
- Numbers: mark for the generator (Module 15).

### STEP 5 - Morphology
- **Article gender (GEN-1 to GEN-8):** after building each noun (singular form), choose `den`/`deny` and `ein`/`eine` by Module 10.2A. Do this before any fusion with `tu`/`en`/`zu`.
Apply, in this order: **derivation** (`-zung`, `-mann`) -> **noun prefix** -> **plural** -> **verb prefix** -> **infinitive `-en`** (only inside modal frames) -> **negation suffix `-nu`** (Step 7). Numbers via Module 15.

### STEP 6 - Frame selection and assembly
1. Choose the frame (Module 7.9 priority).
2. Look up the **finite core** for person x tense x frame in Module 6.
3. Fill the slots of the frame template exactly (Module 7). Keep ISO-1 for everything the template does not mention.

### STEP 7 - Negation and pragmatic insertions
1. Apply the negation algorithm (Module 8).
2. Imperatives: insert `Ben`/`Su` if targeted (Module 13).
3. Questions: insert exactly one helper from HLP-2 (formal or informal form, by type and slot); place `Schalowit` last in how-questions (Module 12).
4. Politeness: `Plis` start (formal) or end (casual) only if the English had "please".

### STEP 8 - Audit and emit
Run Module 24 on the finished string. If any item fails, repair and re-run. Emit only when every item passes.

---

## MODULE 5 - PHONETICS AND ORTHOGRAPHY

Pronunciation does not change spelling. Translate with the written forms in this file only.

### 5.1 Consonants
| Letters | Sound |
| :--- | :--- |
| `jk` | Rolling guttural "r" (French / German style). |
| `j` | "y" as in *yellow* or *yacht*. |
| `sh` | "E-sk": slight hiss before a hard "k". |
| `ch` | Thick "sh" with rounded lips (as in *shoe*). |
| `th` | "Jeh-sky" sound. |
| `w` | Variable by accent: hard "v", aspirated "wh", or soft "shoe-wa". |
| `Nm` | Humming nasal "mm / mmeh", held slightly longer than English "m". |

### 5.2 Vowels
| Letter | Sound |
| :--- | :--- |
| `A` | "Ah" (as in *father*) |
| `E` | "Eeh" (as in *see*) |
| `I` | "Iay" (as in *play*) |
| `O` | "Oh" (as in *boat*) |
| `U` | "Uh" or "Uj" (as in *cut*, or a soft "oo") |

### 5.3 Survival vocabulary
| English | Schalowitsk |
| :--- | :--- |
| Hello | `Halo` |
| Goodbye | `Adjo` |
| Yes | `Jak` |
| No | `Nu` |
| Ok | `Ok` |
| Thank you | `Grahdtuhd` |
| Please | `Plis` |

### 5.4 Orthographic rules
- **ORT-1** Spell every word exactly as listed. Do not "improve" spelling (no `Heute` -> `Heutte`, no `aufsita` -> `kastel`).
- **ORT-2 Apostrophe.** The apostrophe is legal in exactly three constructions and nowhere else:
  1. Preposition + article fusion: `tu'den`, `en'den`, `zu'den`, `tu'deny`, `en'deny`, `zu'deny` (PRP-2).
  2. Pronoun possessive: `av'mi` (POS-2).
  3. The lexicalized compound `jad'ze` (MOR-4b). New compounds are glued with no apostrophe (MOR-4).
  Never use an apostrophe for English possession (`'s`) or English contractions.
- **ORT-3 Hyphen.** The only literal hyphen is the noun-possessor prefix `av-` (`den konig av-aufsita`, POS-3). All other hyphens in this file are notation (see 0.3). **Exception:** a hyphen that is part of a `Dictionary.json` headword (`kahn-plas`, `high-security`) is copied verbatim (DIC-4).
- **ORT-4 Capitalization.**
  1. The first word of every sentence is capitalized. This also applies to a word that opens a number, e.g. `Foiwik prozent` at the start of a sentence.
  2. These are **always** capitalized, even mid-sentence: `Ya`, `Yem`, `Yeht`, `Yal`, `Yalm`, `Yahlt`, `Su`, `Ben`, `Er`, `She`, `Dehye`, `Dehyt`, `Schalowit`, `Seckeh`.
  3. Proper names keep their original capitalization (`Roblox`). A multi-word country name capitalizes every word (`Ferjed Derzheni`, NAM-8).
  4. Digit words and the unit part of a numeral are capitalized (`Dry`, `doiwikn Nein`). **Tens, `dezi`, `hundert`, `tausend`, `milion` and ordinals are lower-case** (`foiwik`, `neinik`, `hundert`, `dryte`) except at a sentence start (10.1, NUM-5).
  5. **Everything else is lower-case mid-sentence**, including derived nouns (`spilezung`, `spilemann`), role words (`bist`, `sicherbremol`, `bremolin`), the new 10.1 words (`lez`, `halb`, `prozent`) and the object/dative pronoun forms (`mi`, `ben`, `su`, `er`, `she`, `dehyr`, `yemvyeni`). [RESOLVED]
  6. `Et`, `Es`, `Dah`, `Daz`, `Heute`, `Morgen`, `Plis` are lower-case mid-sentence (`et`, `es`, `dah`, `daz`, `heute`, `morgen`, `plis`) and capitalized only at the start of a sentence.
  7. **Nationality, language and country words (10.1).** Nouns are capitalized: country (`Dojtska`), language (`Deutsch`), person-demonym (`Deutschmann`) and every form built on it: the female form (`Deutschin`, ROL-4), the plural (`Deutschmaneni`, `Deutschieni`) and a role compound whose head is the demonym. Adjectives of nationality or continent are lower-case (`europanisk`, `spanisk`, NAM-8). ✔ `Yem bist Deutschmann.` ✔ `Yem spile Deutsch.` ✔ `Dojtska doun eine stark europanisk derzhe.` ✘ `Yem bist deutschmann.` ✘ `Europanisk` mid-sentence
  8. **New-sentence capitalization (10.1).** A capital opens (a) every sentence after `.` `!` `?`, (b) the text after a **colon**, (c) the first word inside an opening **quotation mark**, and (d) every **list item or bullet**. A **comma** (including the comma after a vocative or after a fronted clause) and a **semicolon** [DERIVED] do **not** start a new sentence, so the word after them stays lower-case. ✔ `Dah doun eine spilezung: Roblox doun xnekst.` ✔ `John, stevad Ben es!` (`stevad` stays lower-case) ✔ `Wehn Su gehk doun, dashe Ya wurd gehk.` ✘ `John, Stevad Ben es!`
- **ORT-5 Punctuation.** Terminal `.`, `!`, `?` attach to the last word with no space. `Schalowit` is the last token **before** that mark. Commas attach to the preceding word.

---

## MODULE 6 - PRONOUNS, HELPERS AND THE FINITE CORE

### 6.1 Pronoun inventory
| Role | Standalone subject | Present fused | Future fused | Past | Object / Dative / Experiencer | Possessive (`av'` + this) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1SG "I" | `Ya` | `Yem` (`Ya`+`em`) | `Yeht` (`Ya`+`geht`) | `Ya shoun` | `mi` | `av'mi` |
| 2SG informal "you" | `Ben` | - | - | `Ben shoun` | `ben` | `av'ben` [DERIVED] |
| 2SG formal "you" | `Su` | - | - | `Su shoun` | `su` | `av'su` [DERIVED] |
| 3SG masculine "he" | `Er` | - | - | `Er shoun` | `er` | `av'er` [DERIVED] |
| 3SG feminine "she" | `She` | - | - | `She shoun` | `she` | `av'she` [DERIVED] |
| 1PL "we" | `Yal` | `Yalm` (`Yal`+`em`) | `Yahlt` (`Yal`+`geht`) | `Yal shorn` | `yemvyeni` | `av'yemvyeni` [DERIVED] |
| 3PL "they" | `Dehye` | - | `Dehyt` (`Dehye`+`geht`) | `Dehye shorn` | `dehyr` | `av'dehyr` [DERIVED] |
| "you" plural | `Su` / `Ben` (same forms as 2SG) | | | | | |

Fused forms are **lexicalized**. Copy them from the table; do not derive them.

**Dictionary notes on this table.** (1) `sein` is the numeral **six** in `Dictionary.json`; the Guide's "your = `sein`" is superseded, so informal object/possessive is `ben` / `av'ben` [RESOLVED]. (2) `er` is also the noun "ear"; context decides. (3) `mi` is listed as the dative/experiencer form, which confirms EXP-2. (4) Reflexives (`yaselb`, `suselb`, `benselb`, `erselb`, `sheselb`, `yalselb`, `dehyeselb`) are in 6.1a; the old dictionary forms `sebm` and `reflektk` are superseded (RFL-5).

### 6.1a Reflexive pronouns
| English | Schalowitsk | Pronunciation | Etymology / Breakdown |
| :--- | :--- | :--- | :--- |
| Myself | `yaselb` | /ˈjɑːzɛlp/ | `Ya` (I) + `selb` (self) |
| Yourself (formal) | `suselb` | /ˈsuːzɛlp/ | `Su` (formal you) + `selb` |
| Yourself (casual) | `benselb` | /ˈbɛnzɛlp/ | `Ben` (casual you) + `selb` |
| Himself | `erselb` | /ɛrˈzɛlp/ | `Er` (he) + `selb` |
| Herself | `sheselb` | /ʃɛˈzɛlp/ | `She` (she) + `selb` |
| Ourselves | `yalselb` | /ˈjɑːl.zɛlp/ | `Yal` (we) + `selb` |
| Themselves | `dehyeselb` | /deɪ.jɛˈzɛlp/ | `Dehye` (they) + `selb` (supersedes the clunky `sebm`) |

- **RFL-1 Formation.** Reflexive = standalone subject pronoun, lower-cased, + `selb`, written as one word: `Ya` -> `yaselb`, `Dehye` -> `dehyeselb`. Copy the forms from the table.
- **RFL-2 Use.** When the object (or dative / experiencer) is the same person as the subject, use the reflexive, not the Object / Dative form of 6.1. ✘ `mi`, `er`, `she`, `dehyr` standing for the subject itself. ✔ `yaselb`, `erselb`, `sheselb`, `dehyeselb`. [DERIVED]
- **RFL-3 Position.** The reflexive sits where the object would sit. It counts as a direct object (NEG-5), so a negated transitive verb takes `-nu` (NEG-2). [DERIVED]
- **RFL-4 Capitalization.** Lower-case mid-sentence, like the other object forms (ORT-4). No reflexive starts a clause.
- **RFL-5 Superseded.** `sebm` (themselves) and `reflektk` (herself) are never output. Use `dehyeselb` and `sheselb`.
- **RFL-6 Plural "you".** "Yourselves" uses the same forms as the singular (`suselb` formal, `benselb` casual), like "you" plural in 6.1. [DERIVED] [GAP: `itself`; no form is defined. Fallback: `[UNKNOWN:itself]` (DIC-2).]

### 6.2 The helpers
| Helper | Meaning | Used with |
| :--- | :--- | :--- |
| `doun` | present singular: is / am / do / does (the dictionary lists `am` = `doun`) | 2SG, 3SG, singular noun subjects, `Et`, `Es`, `Dehyss`; 1SG only in V2 and subordinate clauses |
| `dorn` | present plural: are / do | 1PL, 3PL, plural noun subjects, `Dehysseni`; 1PL and 3PL in V2 and subordinate clauses |
| `shoun` | past singular: was / did | all singular subjects |
| `shorn` | past plural: were / did | all plural subjects |
| `geht` | future: will / is going to | **all** persons |
| `em` | present component of `Yem` / `Yalm` | never used alone |

`doun`, `dorn`, `shoun`, `shorn` also work as **full verbs**: `Su doun es.` = "You are doing it." (FIN-7)

### 6.3 FINITE-CORE LOOKUP TABLES (use these, do not improvise)

The *core* is the token group that carries person and tense. There are four tables, one per frame. **Pick the table by frame first, then the row by person and the column by tense.**

#### Table A - Main clause, normal order (SVO). Shape: `[Core] [V] [O ...]`
| Person | Present | Past | Future |
| :--- | :--- | :--- | :--- |
| 1SG | `Yem` | `Ya shoun` | `Yeht` |
| 2SG informal | `Ben doun` | `Ben shoun` | `Ben geht` |
| 2SG formal | `Su doun` | `Su shoun` | `Su geht` |
| 3SG masc | `Er doun` | `Er shoun` | `Er geht` |
| 3SG fem | `She doun` | `She shoun` | `She geht` |
| "it" abstract | `Et doun` | `Et shoun` | `Et geht` |
| "it" physical / this | `Es doun` / `Dehyss doun` [DERIVED] | `Es shoun` | `Es geht` |
| 1PL | `Yalm` | `Yal shorn` | `Yahlt` |
| 3PL | `Dehye dorn` | `Dehye shorn` | `Dehyt` |
| singular noun | `den konig doun` | `den konig shoun` | `den konig geht` |
| plural noun | `den konigeni dorn` | `den konigeni shorn` | `den konigeni geht` |

#### Table B - V2 clause (a fronted element exists). Shape: `[Front] [H] [S] [V] [O ...]`
The helper separates from the subject. **Fused forms are forbidden here (FIN-4).**
| Person | Present | Past | Future |
| :--- | :--- | :--- | :--- |
| 1SG | `doun Ya` | `shoun Ya` | `geht Ya` |
| 2SG informal | `doun Ben` | `shoun Ben` | `geht Ben` |
| 2SG formal | `doun Su` | `shoun Su` | `geht Su` |
| 3SG masc | `doun Er` | `shoun Er` | `geht Er` |
| 3SG fem | `doun She` | `shoun She` | `geht She` |
| 1PL | `dorn Yal` | `shorn Yal` | `geht Yal` |
| 3PL | `dorn Dehye` | `shorn Dehye` | `geht Dehye` |
| singular noun | `doun den konig` | `shoun den konig` | `geht den konig` |
| plural noun | `dorn den konigeni` | `shorn den konigeni` | `geht den konigeni` |

#### Table C - Subordinate / relative clause. Shape: `[Sub] [S] [O / PP ...] [V] [H]`
The standalone pronoun comes first; the helper is the **last** word of the clause. **Fused forms are forbidden here (FIN-4).**
| Person | Present (last word) | Past (last word) | Future (last word) |
| :--- | :--- | :--- | :--- |
| `Ya` | `doun` | `shoun` | `geht` |
| `Ben` / `Su` | `doun` | `shoun` | `geht` |
| `Er` / `She` / `Et` / singular noun | `doun` | `shoun` | `geht` |
| `Yal` / `Dehye` / plural noun | `dorn` | `shorn` | `geht` |

#### Table D - Modal clause. Shape: `[Subject token] [Modal] [O / PP ...] [V-en]`
The modal is the finite verb, so **no separate helper is added.** Use the *present core with any separable helper (`doun`, `dorn`) removed*; the lexicalized fused forms stay whole. [DERIVED from the CANON pair `Yem muss ...`]
| Person | Subject token before the modal |
| :--- | :--- |
| 1SG | `Yem` |
| 1PL | `Yalm` |
| 2SG | `Ben` / `Su` |
| 3SG | `Er` / `She` / `Et` / noun |
| 3PL | `Dehye` |
In V2, the modal replaces the helper in Table B and the subject is standalone: `Heute muss Ya ...` [DERIVED] (MOD-7).

### 6.4 Rules
- **FIN-1 One core per clause.** Exactly one of: a fused form, or a pronoun + helper, or a modal. Never two. (Stated exceptions: `shoun` / `shorn` + `konj` in a past unreal clause, SBJ-2; a tense helper before a modal, MFUT-1.) ✘ `Ya yem`, `Ya yeht`, `Yal yalm`, `Yem doun`, `Ben doun doun`, `Er doun shoun`.
- **FIN-2 Future** is `geht` (Table A-C) or the fused forms `Yeht`, `Yahlt`, `Dehyt`. The verb `gehk` + `tu` is never a future marker. ✘ `Yem gehk tu mek` ✔ `Yeht mek`.
- **FIN-3 Fused forms are legal** (a) in plain main-clause SVO, (b) in normal-order questions, (c) as the subject token before a modal (`Yem muss`, `Yalm muss`), (d) at the start of a **new** main clause after `n`, `br`, `j`, `dashe`, or a comma-separated main clause.
- **FIN-4 Fused forms are illegal** (a) when any element is fronted (V2), (b) inside subordinate or relative clauses, (c) when a modifier such as `alsitnu` stands between subject and verb (FIN-9). In those positions use the standalone pronoun and the separate helper from Tables B and C.
- **FIN-5 Agreement.** Singular subject: `doun` / `shoun`. Plural subject: `dorn` / `shorn`. `geht` for everyone. `Su` and `Ben` take the singular helper even when "you" is plural.
- **FIN-5a `Su` and `Ben` always take the singular helper.** `doun` / `shoun`, whether "you" is one person or many. `dorn` / `shorn` belong only to `Yal`, `Dehye`, plural nouns and `Dehysseni`. ✘ `Su dorn`, `Ben dorn`, `Seckeh plas chez Su dorn`. ✔ `Su doun`, `Ben doun`.
- **FIN-6 The action verb is invariant.** It stays in dictionary form after the core in every person, tense and aspect. The six legal modifications are: `-nu` (negation), `-en` (modal frame), `an-`/`wieder-`/`aus-` (glued prefixes), `-zung`/`-mann` (derivation into nouns).
- **FIN-7 `doun` / `dorn` / `shoun` / `shorn` as full verbs.** For a non-1SG subject, "do" and "be" are the same word: `Su doun es.` = "You do it / You are it." No second helper is added. For 1SG, `Yem` already contains "am": `Yem ein spilemann.` = "I am a player." When the 1SG pronoun and helper are **separated** (V2, subordinate), `doun` is the 1SG copula, which the dictionary confirms (`am` = `doun`): `Heute doun Ya ein spilemann.` [GAP: a main-clause "I do it"; the Guide's `Ya doun es` predates fusion. Fallback: `Yem es`.]
- **FIN-8 Noun and demonstrative subjects** take `doun`/`dorn` etc. exactly like pronouns: `Den konig doun rukz deny aufsita.` ["The king rules the castle."] [DERIVED]; `Den urzkonig shoun bau deny aufsita.` CANON.
- **FIN-9 The `alsitnu` slot.** When `alsitnu` ("never") follows the subject, the subject is standalone and **no helper is added** (present tense): `Ya alsitnu iz apeleni.` CANON. For `Ben`, `Er`, etc.: `Ben alsitnu iz apeleni.` [DERIVED] [GAP: past/future. Fallback: follow the Gold Standard order *Subject + Modifier + Helper + Verb*: `Ya alsitnu shoun iz apeleni.`]
- **FIN-10 Object pronouns** (me, him, her, us, them, you) use the Object/Dative column of 6.1: `mi`, `er`, `she`, `yemvyeni`, `dehyr`, `su` (formal) / `ben` (informal). "It" as object = `es` (tangible) or `et` (abstract) (REF-1). Reflexives (myself, himself, themselves...) use 6.1a (RFL-1..6). [DERIVED]
- **FIN-11 Fused forms belong to one pronoun each.** `Yem` and `Yeht` = I. `Yalm` and `Yahlt` = we. `Dehyt` = they. Any other subject (a name, `AI`, `Er`, `She`, a noun) takes the plain core of Table A. ✘ `AI yeht verstehennu dehyss` ✔ `AI geht verstehennu dehyss`.
- **FIN-12 Main-verb "do" is `tyern`** in every tense: `Yeht tyern es.`, `Su doun tyern dehyss.`, `Yeht tyernnu es.` English do-support is dropped (Step 0.6). `mek` is "make" only; never swap them between sentences.
- **FIN-13 `haben` needs a core.** "Have" and "has" are the verb `haben`, never a new word (LEM-5): `Su doun haben eine key.`, `Er doun haben eine aufsita.` For 1SG: `Yem haben eine key.`

### 6.5 English pronoun -> Schalowitsk
| English | Schalowitsk |
| :--- | :--- |
| I | `Ya` (`Yem` / `Yeht` in fused positions) |
| you (default / formal / stranger) | `Su` |
| you (informal / gaming / friend) | `Ben` |
| he | `Er` |
| she | `She` |
| it (abstract, weather, time) | `Et` |
| it (physical object) | `Es` |
| we | `Yal` (`Yalm` / `Yahlt` fused) |
| they | `Dehye` (`Dehyt` fused future) |
| myself / yourself / himself / herself / ourselves / themselves | `yaselb` / `suselb` (formal), `benselb` (casual) / `erselb` / `sheselb` / `yalselb` / `dehyeselb` (6.1a) |
| this / that | `dehyss` |
| these / those | `dehysseni` |
| who (question) | `Seckeh penk` |
| everyone / someone / anyone / no one | `alkto` / `mankto` / `irgkto` / `nimkto` |
| everything / something / anything / nothing | `alscht` / `manscht` / `irgscht` / `nikscht` |

---

## MODULE 7 - CLAUSE FRAMES

### 7.1 Plain main clause (SVO)
**Template:** `[Core] [V] [O] [Prepositional phrases] [Manner adverb] [Place / time adverbial]` (rest by ISO-1)

- **SVO-1** Use Table A for the core. The verb follows the core immediately.
- **SVO-2** Trailing adverbials stay in English order (ISO-1). Time words that the English put at the end stay at the end.
- **SVO-3** Copular sentences: `[Core] [predicate]`: `Er doun ein konig.` ("He is a king."), `Yem ein spilemann.` ("I am a player.") [DERIVED] **Superseded for identity predicates by ROL-1:** a nationality, job, title, role, name or relationship now takes `bist` (`Yem bist ein spilemann.`, `Er doun bist ein konig.`). The plain copula remains for adjectives, locations and states (ROL-2).
- **SVO-4 Headlines and fragments.** A fragment whose English implies "is" still gets its core (FIN-1) and gets no article the English lacked (OUT-5): `Translation complete` -> `Trahnslotzung doun kompletn.` ✘ `Den trahnslotzung kompletnu.` [DERIVED]

✔ `Yem spile Roblox heute.` ("I play / am playing Roblox today.")
✔ `Yem spile Roblox mit briv av'mi.`
✔ `Ya shoun spile Roblox.` ("I played Roblox.")
✔ `Yeht spile Roblox.` ("I will play Roblox.")
✔ `Er doun iz den apel.` ("He eats the apple.") [DERIVED]
✔ `Dehye dorn iz apeleni.` ("They eat apples.") [DERIVED]
✔ `Yem ruhn kvik.` ("I run quickly.")
✘ `Yem doun spile Roblox` (second helper) ✘ `Ya spile Roblox` (no core) ✘ `Yem spileing Roblox` (`-ing`)

### 7.2 V2 fronting
- **V2-1 The rule.** If a time word, adverbial or prepositional phrase is placed at Index 0 of a main clause, the **helper goes to Index 1** and the **subject to Index 2**. The verb and everything else follow.
  **Template:** `[Fronted element] [H] [S] [V] [O ...]` (Table B)
- **V2-2 Triggers (an element at Index 0 that is *not* the subject):**
  - time words: `Heute` / `Heut`, `Morgen`
  - prepositional phrases: `En'deny aufsita`, `Tu'den heim`, `Mit briv av'mi`
  - place or manner adverbs: `Daz`, `Kvik`
- **V2-3 Non-triggers.** These at Index 0 do **not** cause V2 and leave the normal order: a WH-phrase (`Seckeh ...`, QST-3), a subordinate clause (`Wehn ...`), a coordinator (`n`, `br`, `j`), `dashe`, `Plis`, an interjection or greeting (`Halo,` `Ok,` `Jak,` `Nu,`).
- **V2-4 Faithful fronting.** Front an element only if the English fronted it; never move it yourself. "I play Roblox today" -> `Yem spile Roblox heute.` ; "Today I play Roblox" -> `Heute doun Ya spile Roblox.`
- **V2-5 Fused forms are forbidden at Index 1 and Index 2.** Use `Ya`, not `Yem`/`Yeht`; `Yal`, not `Yalm`/`Yahlt`; `Dehye`, not `Dehyt` (FIN-4).
- **V2-6 Negation** works as usual on the verb (Module 8).
- **V2-7 Spelling:** `Heut` and `Heute` are the same word. Output `Heute` by default.

✔ `Heute doun Ya spile Roblox.` ("Today I play Roblox.")
✔ `Heute doun Ya spilenu Roblox.` ("Today I do not play Roblox.")
✔ `Heute doun Ya spile nucht.` ("Today I am not playing.") [DERIVED by NEG]
✔ `Morgen geht Ya mek eine spilezung.` ("Tomorrow I will make a game.") [DERIVED]
✔ `Heute doun Ben spile Roblox.` / `Heute doun Su spile Roblox.` / `Heute doun Er spile Roblox.` [DERIVED]
✔ `Heute dorn Yal spile Roblox.` / `Heute dorn Dehye spile Roblox.` [DERIVED]
✔ `En'deny aufsita doun Ya spile Roblox.` ("In the castle I play Roblox.") [DERIVED]
✔ `En'deny aufsita shoun Ya spile Roblox.` ("In the castle I played Roblox.") [DERIVED]
✘ `Heute Yem spile Roblox.` (no V2) ✘ `Heute Ya spile Roblox.` (no helper) ✘ `Heute doun Yem spile Roblox.` (fused form at Index 2) ✘ `Heute Ya doun spile Roblox.` (subject before helper) ✘ `Heute doun Ya doun spile Roblox.` (double helper)

### 7.3 Subordinate clauses (verb-final)
- **SUB-1 The rule.** In a subordinate clause the **helper is the last word** of that clause.
- **SUB-2 Subordinators:** `wehn` (if / when), `wahn` (because), `dass` (that), `whilst` (while). The relative pronouns `Seckeh penk` / `Seckeh` also open a subordinate clause (7.8).
- **SUB-3 Template (Table C):** `[Subordinator] [S] [every O / PP / adverbial] [V] [H]`. All complements sit **between the subject and the verb**. [RESOLVED: the v8.0 template and example `wehn Su tu'deny aufsita gehk doun` put complements before the verb; older files put the object after it.]
- **SUB-4 Standalone pronouns only** (FIN-4): `Ya`, never `Yem`.
- **SUB-5 Negation** stays on the verb: `... Su Roblox spilenu doun`, `... Su gehk nucht doun`.
- **SUB-6 Conditionals.** A *fronted* `wehn` clause is followed by `dashe` ("then") and a normal main clause (fused forms allowed again). `dashe` does **not** trigger V2. A `wehn` clause placed *after* the main clause has no `dashe`. For other subordinators, a fronted clause is followed directly by an SVO main clause with no `dashe`. [DERIVED]
- **SUB-8 Embedded questions** ("I see what you play") are subordinate clauses opened by a WH-phrase or `obe`; no question helper (QST-10).
- **SUB-7 Modal inside a subordinate clause:** the `-en` verb comes first, the modal is the last word. `... Su eine spilezung spilen muss` [DERIVED] (MOD-8).

✔ `Wehn Su gehk doun, dashe Yem gehk.` ("If you go, then I go.")
✔ `Yem gehk wehn Su gehk doun.` ("I go if you go.")
✔ `... wehn Su tu'deny aufsita gehk doun.` ("... when you go to the castle.")
✔ `Wehn Su tu'deny aufsita gehk doun, dashe Yeht mek eine spilezung.` ("If you go to the castle, I will make a game.") [DERIVED]
✔ `Wehn Ya Roblox spile doun, dashe Su doun gehk.` ("If I play Roblox, you go.") [DERIVED]
✔ `Wehn Su Roblox spilenu doun, dashe Yem gehk.` ("If you do not play Roblox, I go.") [DERIVED]
✔ `Yem spile Roblox wahn Roblox mi xnekst doun.` ("I play Roblox because Roblox is great to me.") [DERIVED]
✘ `Wehn Su doun gehk` (helper not last) ✘ `Wehn Yem gehk doun` (fused form in subordinate clause) ✘ `Wehn Su gehk, dashe Ya gehk` as an *output* (helpers missing; this is the Guide's shorthand) ✘ `Wehn Su gehk doun, Yem gehk.` (missing `dashe`)

### 7.4 Modal frame
- **MOD-1 The rule.** `[Subject token] [Modal] [all O] [all PP] [all adverbials] [V-en]`. The modal is the finite verb and sits right after the subject token (Table D).
- **MOD-2 Everything inside the frame.** Direct objects, indirect objects, prepositional phrases and adverbials all stand **between the modal and the infinitive**. The `-en` verb is the **last word** before the end punctuation.
- **MOD-3 The three modals and their English triggers:**
  | Modal | Meaning | English triggers |
  | :--- | :--- | :--- |
  | `muss` | must / have to | must, have to, has to, need to + verb, got to |
  | `kahn` | can / is able to | can, is able to, may (permission), could [DERIVED] |
  | `wolt` | want to | want to, wants to, would like to [DERIVED] |
  | `bofik` | wanna (casual) | "wanna"; informal register only; same frame as `wolt` |
  **Dictionary basis:** `kahn` is the only entry tagged `modal` and also appears inside `kahn-plas` ("anywhere"); `wolle` means *cotton* in the dictionary, so the Guide's modal `wolle` is superseded by `wolt`; `kann` is superseded by `kahn` [RESOLVED]. "wish" is the separate verb `wunsch`, not a modal.
  [GAP: should, ought to, might, would. Fallback: `should`/`ought to` -> `muss`; `might` -> `kahn`; `would` -> drop and use present.]
- **MOD-4 No extra helper.** Never write `doun muss`, `Yem doun kahn`. **Exception (10.0):** the tense helpers `geht` (future), `shoun` / `shorn` (past) and the conditional `wurd` may stand before a modal (MFUT-1, CND-1). Never `doun` / `dorn` before a modal.
- **MOD-5 No `tu`.** The English "to" before the verb disappears. Never `muss tu spilen`.
- **MOD-6 Infinitive formation (Module 14.3):** root already ending in `-en` -> **unchanged** (`haben`, `sehen`, `denken`, `verlassen`); root ending in `e` -> add `n` (`spile` -> `spilen`); any other root -> add `en` (`mek` -> `meken`, `gehk` -> `gehken`, `trink` -> `trinken`, `bau` -> `bauen`, `austrink` -> `austrinken`).
- **MOD-7 V2 with a modal.** The modal takes the helper's slot: `[Front] [Modal] [S standalone] [O / PP ...] [V-en]`. [DERIVED]
- **MOD-8 Modal in a subordinate clause:** `[Sub] [S] [O / PP ...] [V-en] [Modal]`. [DERIVED]
- **MOD-9 Modal questions.** Informal: `Kez Ben kahn Roblox spilen?`; formal: `Chez Su kahn Roblox spilen?`. WH: `Seckeh kel Ben kahn spilen?` [DERIVED]
- **MOD-10 Modal + negation (resolved 10.0).** Negate the **modal**, never the infinitive, by suffixing `-nu` (MNEG-1): `Yem kahnnu Roblox spilen.` The infinitive keeps `-en` and is never negated.
- **MOD-11 Modal + past/future (resolved 10.0).** Tense helper + modal (MFUT-1): `Yeht kahn Roblox spilen.` (I will be able to play.)
- **MOD-12 `brauch` ("need" + noun) is an ordinary verb,** not a modal: `Yem brauch eine key tu'den heim.` "need to + verb" is `muss`; "need + noun" is `brauch`.
- **MOD-13 "going to + verb" is future, not a modal** (TNS-2). "going to + place" is motion (TNS-4).
- **MOD-14 "have to go" (leave).** Leaving/departing without a destination = the dictionary root `verlassen` (already an `-en` form, so it is its own infinitive): `Yem muss verlassen!` With a destination use `gehken`: `Yem muss tu'deny aufsita gehken.` [DERIVED]
- **MOD-15 "want + noun"** ("I want a key"): use `wolt` as a plain verb with no infinitive: `Yem wolt eine key.` [DERIVED]
- **MOD-16 `lyuba` (like / enjoy / prefer) is an ordinary verb and is never `muss`.** "Like / love / enjoy / hate + verb-ing" and "like to + verb" use the frame `[Table A core] lyuba [every object / PP / adverbial] [V-en]`. The second verb takes `-en` (MOR-3) and is the last word. "Like + noun": `Yem lyuba Roblox.` ✔ `Yem lyuba spilen.` ✔ `Su doun lyuba penk troshen.` ✘ `Yem muss spilen.` (that means "I must play") ✘ `Yem lyuba spile` ✘ `Yem lyuba penk troshkeni`. **Negation (10.1, LNEG-1):** suffix `-nu` to `lyuba`, with a noun object or an `-en` infinitive alike; the infinitive stays `-en` and is never negated. ✔ `Yem lyubanu Roblox.` ✔ `Yem lyubanu spilen.` ✔ `Yem lyubanu Roblox spilen.` ✔ `Ya shoun lyubanu Roblox.` ✔ `Su doun lyubanu spilen.` ✔ `Yeht lyubanu spilen.` ✘ `Yem lyuba nucht spilen.` ✘ `Yem lyuba spilenu.` Question: `Chez Su doun lyubanu spilen?` Subordinate: `... dass Er Roblox lyubanu doun.` [DERIVED] (NEG-4 still applies: no double negation with `alsitnu`, `nikscht`, `nimkto`.)

✔ `Yem muss verlassen!` ("I have to go!")
✔ `Yem muss mit briv av'mi spilen.` ("I have to play with my brother.")
✔ `Yem muss eine spilezung mit briv av'mi spilen.` ("I have to play a game with my brother.")
✔ `Ben kahn Roblox spilen.` ("You can play Roblox.") [DERIVED]
✔ `Yem wolt deny aufsita bauen.` ("I want to build the castle.") [DERIVED]
✔ `Su muss den wasser austrinken.` ("You have to finish drinking the water.") [DERIVED]
✔ `Yem muss tu'deny aufsita gehken.` ("I have to go to the castle.") [DERIVED]
✔ `Heute muss Ya eine spilezung mit briv av'mi spilen.` ("Today I have to play a game with my brother.") [DERIVED]
✘ `Yem muss spilen mit briv av'mi.` (infinitive not last)
✘ `Yem muss mit briv av'mi spilen eine spilezung.` (object after the infinitive)
✘ `Yem muss eine spilezung mit briv av'mi spile.` (missing `-en`)
✘ `Yem muss tu spilen` / `Yem haben tu gehk` (English infinitive)
✘ `Yem doun muss spilen` (second helper)
✘ `Yem muss gehk tu'deny aufsita` (bare verb, wrong place)

### 7.5 Questions and 7.6 Commands
Full rules: Module 12 (questions) and Module 13 (imperatives). Their frame rules still obey 7.9.

### 7.7 Coordination
- **COO-1** `n` (and), `br` (but), `j` (or) are separate words between clauses or phrases: `Yem spile Roblox n Ben doun iz apeleni.`
- **COO-2** Each coordinated clause is framed independently. A coordinator does not trigger V2, and the fused form is legal again after it (FIN-3).
- **COO-3** Verbs sharing a subject and core: `Yem spile n iz.` [DERIVED]. Lists: `apel, buch n hze` (ISO-1).
- **COO-4** The `n` inside a number is part of the tens word (`doiwikn`, NUM-3), not the conjunction, and is never written as a separate word.

### 7.8 Relative clauses
- **REL-1** Introducers: `Seckeh penk` (who / whom; persons) and `Seckeh` (which / that; things). They stand directly after the head noun.
- **REL-2** A relative clause is subordinate: verb-final, helper last (Table C).
- **REL-3** If the relative pronoun is the subject, no other subject word appears. If it is the object, the real subject follows it. [DERIVED]
- **REL-4 "That has" / "which has".** The relative word is `Seckeh`, never `dehyss`. "That has X" = `Seckeh [X] haben doun`. ✔ `..., Seckeh ein schpize xnekst kriegsvalt haben doun.` ✘ `..., dehyss doun ein schpize xnekst kriegsvalt.` (drops "has", adds "is") [DERIVED]

✔ `... ein konig Seckeh penk doiwikn Nein penkeni rukz doun.` ("... a king who rules twenty-nine people.")
✔ `deny key Seckeh Ya brauch doun` ("the key that I need") [DERIVED]
✘ `... ein konig Seckeh penk twenty-nine penkeni rukz doun` (English number leaked)

### 7.9 Frame priority and combinations
| Priority | Condition | Frame |
| :--- | :--- | :--- |
| 1 | Command | Module 13 (no subject, no helper, no V2) |
| 2 | Clause opened by a subordinator or relative pronoun | 7.3 verb-final |
| 3 | Question | Module 12 (normal order + helper + `Seckeh` / `Schalowit`) |
| 4 | Contains `muss` / `kahn` / `wolt` + verb | 7.4 modal frame |
| 5 | An element other than the subject is at Index 0 | 7.2 V2 |
| 6 | Nothing above | 7.1 SVO |

**Combinations**
| Combination | Result |
| :--- | :--- |
| V2 + modal | `[Front] [Modal] [Ya] [O / PP] [V-en]` |
| V2 + negation | helper and subject swap; verb carries `-nu` / `nucht` |
| Subordinate + modal | `[Sub] [S] [O / PP] [V-en] [Modal]` |
| Subordinate + negation | `[Sub] [S] [O] [V-nu] [H]` |
| Question + modal | `[Seckeh ...] [wh-helper] [S] [Modal] [O] [V-en]?` or `[yn-helper] [S] [Modal] [O] [V-en]?` |
| Fronted `wehn` clause + main clause | `Wehn [S ... V H], dashe [Table A core] [V] ...` |
| Command + anything | Command frame only; never V2 |

---

## MODULE 8 - NEGATION

### 8.1 Decision tree (run for every negated clause)
```
Does the clause contain an ABSOLUTE NEGATIVE?
   (alsitnu = never, nikscht = nothing, nimkto = no one)
   |
   +-- YES --> Leave the verb UNTOUCHED. Add no -nu and no nucht.        (NEG-4)
   |
   +-- NO --> Does the clause have a DIRECT OBJECT?                       (NEG-5)
                |
                +-- YES --> Fuse -nu onto the action verb. Object follows.  (NEG-2)
                |           Yem spilenu Roblox.
                |
                +-- NO ---> Put nucht directly after the action verb.      (NEG-3)
                            Yem spile nucht.
```

### 8.2 Rules
- **NEG-1 Negation never touches the core.** Do not negate `Yem`, `doun`, `shoun`, `geht`. ✘ `Yem nucht spile` ✘ `Yemnu spile` ✘ `Ben nu doun spile`.
- **NEG-2 Transitive: `V + nu` fused, then the object.** Attach `nu` to the dictionary form with **no letter dropped or added**.
  | Verb | Negated transitive form |
  | :--- | :--- |
  | `spile` | `spilenu` |
  | `iz` | `iznu` |
  | `mek` | `meknu` |
  | `gehk` | `gehknu` |
  | `stevad` | `stevadnu` |
  | `brauch` | `brauchnu` |
  | `bau` | `baunu` |
  | `austrink` | `austrinknu` |
  | `angehk` | `angehknu` |
- **NEG-3 Intransitive: `V nucht`.** `nucht` is a separate word and stands **immediately after the verb**, before any prepositional phrase or adverb.
- **NEG-4 Absolute negatives suppress all other negation.** `alsitnu` (FIN-9), `nikscht`, `nimkto` and the determiner `kein` (NEG-11) already negate the clause. Never combine them with `-nu` / `nucht` (no double negatives).
- **NEG-5 What counts as a direct object.** A noun phrase, pronoun, number + noun, or `es` / `et` that receives the action **with no preposition**: `Roblox`, `deny key`, `apeleni`, `es`, `doiwikn Nein penkeni`.
  **Not** direct objects: prepositional phrases (`mit briv av'mi`, `tu'deny aufsita`), adverbs (`heute`, `daz`, `kvik`), predicate adjectives (`xnekst`), predicate nouns after a copula.
- **NEG-6 Three different things spelled `nu`.**
  | Form | What it is | Where |
  | :--- | :--- | :--- |
  | `-nu` | verb suffix | fused to a transitive verb |
  | `nucht` | negation particle | after an intransitive verb |
  | `Nu` | the word "No" | stand-alone answer only |
  Never write standalone `nu` inside a clause.
- **NEG-7 Imperatives:** apply the same algorithm: `Stevadnu Ben es!` ("Don't find it!"), `Gehk nucht!` ("Don't go!"), `Gehk nucht daz!` [DERIVED]
- **NEG-8 Frames.** The verb carries the negation in every frame:
  | Frame | Example |
  | :--- | :--- |
  | SVO transitive | `Yem spilenu Roblox.` |
  | SVO intransitive | `Yem spile nucht.` |
  | V2 | `Heute doun Ya spilenu Roblox.` |
  | Subordinate | `Wehn Su Roblox spilenu doun, dashe Yem gehk.` [DERIVED] |
  | Past | `Ya shoun spilenu Roblox.` [DERIVED] |
  | Future | `Yeht meknu eine spilezung.` [DERIVED] |
  | Question | `Kez Ben doun spilenu Roblox?` [DERIVED] |
  | Intransitive with PP | `Yem spile nucht mit briv av'mi.` [DERIVED] |
  | Intransitive with adverb | `Yem gehk nucht daz.` [DERIVED] |
- **NEG-9 Absolute negatives in use:** `Ya alsitnu iz apeleni.` ("I never eat apples.") CANON. `Nimkto doun spile Roblox.` ("No one plays Roblox.") [DERIVED]. `Yem iz nikscht.` ("I eat nothing.") [DERIVED]
- **NEG-10 Negated copula, existential and modal (resolved 10.0 / 10.1).** Identity predicates: ROL-6 (`nucht` after `bist`). Modals: MNEG-1 (`-nu` on the modal; never on the infinitive). "No X" in an existential or with a possessed or quantified noun: NEG-11 (`kein`). All other copular clauses (adjective, place, state): NEG-12.
- **NEG-11 `kein` = the determiner "no" (10.1).** `kein` replaces `ein` / `eine` and takes a **female** form `keine` exactly where `ein` would be `eine` (GEN-3, GEN-4). It may take a singular or a bare plural noun. It is an **absolute negative** (NEG-4): the clause gets no `-nu` and no `nucht`. Use it for existence, possession and "no" quantity. Not for identity: "He is not a king" stays `Er doun bist nucht ein konig.` (ROL-6). `nucht ein` stays legal for plain "not a" (a contrast, not a "no").
  ✔ `Dah doun kein konig.` (There is no king.) ✔ `Dah doun keine key.` (There is no key; `key` is female.) ✔ `Dah dorn kein konigeni.` (There are no kings.)
  ✔ `Yem haben keine keyeni.` (I have no keys.) ✔ `Kein konig doun rukz deny aufsita.` (No king rules the castle.)
  ✘ `Dah doun nucht kein konig.` (double negative) ✘ `Yem habennu keine keyeni.` ✘ `Dah doun nikscht konig.`
- **NEG-12 Plain copula negation (10.1).** `nucht` goes **directly after the helper** (or fused core), before the predicate. In V2 it follows the helper and subject; in a subordinate clause it stands before the final helper (SUB-5) [DERIVED]. ✔ `Er doun nucht xnekst.` ✔ `Yem nucht sicher.` ✔ `Heute doun Ya nucht sicher.` ✔ `Dah doun nucht ein konig.` (There is not a king.) ✔ `... dass Er xnekst nucht doun.` ✘ `Er doun xnekstnu.` (ADJ-5)

---

## MODULE 9 - TENSE AND ASPECT

- **TNS-1 Three tenses only:** present, past, future. Each is carried by the core (Module 6), never by the verb.
- **TNS-2 Future.** "will", "'ll", "shall", "is/are going to + **verb**" -> future core (`geht` / `Yeht` / `Yahlt` / `Dehyt`). ✘ `gehk tu`.
  English present used for the future ("I play tomorrow") keeps the **present** core plus the time adverb (ISO-1): `Yem spile Roblox morgen.`
- **TNS-3 Aspect uniformity.** Schalowitsk has one aspect. Continuous / progressive collapses to the simple form of the same tense. `Yem iz` = "I eat" and "I am eating". Never add `-ing`, `doun-ing` or any aspect marker.
  | English | Schalowitsk |
  | :--- | :--- |
  | I am playing | `Yem spile` |
  | I was playing | `Ya shoun spile` |
  | I will be playing | `Yeht spile` |
- **TNS-4 "going to + place" is motion, not future.** Use `gehk` + `tu`: `Yem gehk tu'deny aufsita.` Test: if the word after "going to" is a verb, it is future; if it is a place, it is motion.
- **TNS-5 Perfect forms** [DERIVED]: "have/has eaten", "had eaten" -> past core; "will have eaten" -> future core. "used to eat" -> past core.
- **TNS-6 Conditional, subjunctive, passive (updated 10.0).** "would" = `wurd` (CND-1). Passive = `gewor` (PAS-1). Subjunctive = `konj` (SBJ-1).
- **TNS-7 Frequency adverbs.** `alzeit` (always), `meystens` (usually), `ofte` (often), `mankzeit` (sometimes) and `alsitnu` (never) stand in the **modifier slot** between subject and verb, exactly like `alsitnu` in FIN-9: `Ya alzeit spile Roblox.` [DERIVED from the CANON `Ya alsitnu iz apeleni.`] Only `alsitnu` is an absolute negative (NEG-4). [GAP: confirm that the other four also drop the helper.]
- **TNS-9 English irregular pasts are never separate verbs.** The dictionary lists `went` = `shoun gehk` and `drank` = `shoun trink`. This confirms the rule: past = `shoun` / `shorn` + the invariant root. Never invent forms such as `gehkt` or `trinkt`. (DIC-6)
- **TNS-8 Tense inside subordinate clauses** is carried by the last word (Table C): `... Su gehk shoun` ("... you went").

| English form | Core used |
| :--- | :--- |
| I eat / am eating / do eat | present |
| I ate / was eating / did eat / have eaten / had eaten / used to eat | past |
| I will eat / am going to eat / shall eat / will be eating | future |
| I eat tomorrow | present + `morgen` |

---

## MODULE 10 - THE NOUN PHRASE

### 10.1 Order
`[Determiner or number] [adjectives] [noun] [post-nominal possessor] [prepositional phrase]`
- **NP-1** Modifiers precede the noun: `blau hze` ("blue house"). Adjectives never agree in number or case; only the noun pluralizes. ✘ `hze blau` ✔ `blau hze` ✔ `blau hzeni`

### 10.2 Determiners
| English | Schalowitsk | Rule |
| :--- | :--- | :--- |
| the (neutral-male noun) | `den` | Same for singular and plural. Pronounced Deh-n. |
| the (female noun) | `deny` | Same for singular and plural. Pronounced Deh-n-eh. |
| a / an / one (neutral-male noun) | `ein` | Singular only. |
| a / an / one (female noun) | `eine` | Singular only. |
| (indefinite plural, "apples") | bare plural noun, no article | `Ya alsitnu iz apeleni.` |
| this / that | `dehyss` | before a singular noun |
| these / those | `dehysseni` | before a plural noun |
- **NP-2** English "a/an" -> `ein` or `eine`; "the" -> `den` or `deny` (by GEN-1 to GEN-5); plural without article -> bare plural noun.
- **NP-3** `Ein` as a counting numeral is capitalized (NUM-5); as an article it is lower-case.


### 10.2A Noun gender and gendered articles (new in 9.3)
Schalowitsk has **two genders**. Gender only shows up on the article. Nouns, adjectives, verbs and demonstratives never change.

| | Definite | Indefinite | Sound |
| :--- | :--- | :--- | :--- |
| Neutral-male | `den` | `ein` | Deh-n |
| Female | `deny` | `eine` | Deh-n-eh |

- **GEN-1 Two genders only.** `den` / `ein` = neutral-male. `deny` / `eine` = female. Nothing else exists. Capitalize `Den` / `Deny` at the start of a sentence (ORT-4); `ein` / `eine` as an article stay lower-case (NP-3).
- **GEN-2 Decision order.** Take the first rule that matches: (a) a **person's natural gender** (GEN-3); (b) the **ending** of the singular noun (GEN-4); (c) default `den`.
- **GEN-3 People.** A female person is always `deny` / `eine`, whatever the ending. A male person is always `den` / `ein`, whatever the ending. A person of unknown or unmentioned gender follows the ending rule (GEN-4).
- **GEN-4 Endings.** Look at the **last letters of the singular noun**:
  | Ending | Gender | Examples |
  | :--- | :--- | :--- |
  | a vowel (`a e i o u`) | female (`deny`) | `deny aufsita`, `deny golowa`, `deny hze`, `deny jad'ze` |
  | `y` | female | `deny key` |
  | `-en` | female | (any noun ending in `en`) |
  | `-ung` (including `-zung`) | female | `deny spilezung` |
  | `-zeng` | female | `deny spilezeng` |
  | `-heit` | female | any noun ending in `heit` |
  | `-in` | female | `bremolin`, `Deutschin` (ROL-4) |
  | `-ka` | female (vowel rule) | `lehreka` (ROL-4) |
  | `-ik` | female | any noun ending in `ik` |
  | `-mann` | neutral-male (`den`) | `den spilemann` |
  | `-er` | neutral-male | `den wasser` |
  | any other consonant | neutral-male (default) | `den konig`, `den apel`, `den heim`, `den task`, `den schluessel` |
  A specific suffix (`-mann`, `-er`, `-ung`, `-zeng`, `-heit`, `-ik`, `-en`) always beats the general vowel / consonant rule. Verb infinitives that end in `-en` are verbs, not nouns, so this rule never applies to them.
- **GEN-5 Plurals keep the singular's gender.** Plural endings (`-eni`, `-zeng`) never change gender. Decide gender from the **singular** noun, then pluralize. `den konig` -> `den konigeni`; `deny aufsita` -> `deny aufsitaeni`; `deny spilezung` -> `deny spilezeng`. [DERIVED]
- **GEN-6 Fusion follows gender.** `tu` / `en` / `zu` + `den` -> `tu'den` / `en'den` / `zu'den`; `tu` / `en` / `zu` + `deny` -> `tu'deny` / `en'deny` / `zu'deny`. Still only these three prepositions (PRP-2).
- **GEN-7 Coined words and mash-ups.** A noun coined under Module 16A, or a mash-up, gets its gender from GEN-4 like any other noun. A dictionary headword's gender is always from its own spelling, never from the English word.
- **GEN-8 What has no gender.** `dehyss`, `dehysseni`, possessives (`av'mi`), numerals and proper names (NAM-1) never change for gender.
- ✔ `Yem gehk tu'deny aufsita.` ✔ `Yem brauch eine key tu'den heim.` ✔ `Yem spile eine spilezung.` ✔ `Den konig doun rukz deny aufsita.` ✔ `Er doun ein konig.` ✔ `Deny golowa av'mi doun bol.`
- ✘ `den aufsita` ✘ `ein key` ✘ `eine konig` ✘ `tu'den aufsita` ✘ `deny konigeni` ✘ `denya aufsita`

### 10.3 Possession
- **POS-1 No Saxon genitive.** `'s` and `s'` never appear. Convert every English possessive to an `of`-relation.
- **POS-2 Pronoun possessor** (my, your, his, her, our, their): `[noun] av'[pronoun]`. The possessed noun carries **no article**.
  Default order: `briv av'mi`. Accepted equivalent: `av'mi briv`. Use the **default** when generating.
  | English | Schalowitsk |
  | :--- | :--- |
  | my brother | `briv av'mi` |
  | your brother (informal) | `briv av'ben` [DERIVED] |
  | your brother (formal) | `briv av'su` [DERIVED] |
  | his brother | `briv av'er` [DERIVED] |
  | her brother | `briv av'she` [DERIVED] |
  | our brother | `briv av'yemvyeni` [DERIVED] |
  | their brother | `briv av'dehyr` [DERIVED] |
  ✘ `mi briv` (bare possessive is not used for "my"), ✘ `av mi briv` (no apostrophe), ✘ `briv's mi`.
- **POS-3 Noun possessor.**
  Default (post-nominal): `den [possessed] av den [possessor]` -> `deny aufsita av den konig` ("the castle of the king / the king's castle").
  Accepted equivalent (pre-nominal, **literal hyphen**): `den [possessor] av-[possessed]` -> `den konig av-aufsita`. Here the possessed noun takes **no article**.
- **POS-4 Chained possession** [DERIVED]: `deny hze av briv av'mi` ("my brother's house").
- **POS-5 Body parts:** `Deny golowa av'mi doun bol.` ("My head hurts.") [DERIVED]
- **POS-6 "whose"** = `Seckeh penk av-[noun]` (QST-12). **[GAP]** free-standing possessives ("mine/yours"): rephrase with `av` + noun; otherwise `[UNKNOWN]`.

### 10.4 Prepositions (a closed set)
| Preposition | Meaning | Fuses with `den`? |
| :--- | :--- | :--- |
| `tu` | to, toward, into | yes: `tu'den` / `tu'deny` |
| `en` | in, inside | yes: `en'den` / `en'deny` |
| `zu` | at | yes: `zu'den` / `zu'deny` |
| `mit` | with | no |
| `av` | of (dictionary also: around) | no |
| `darab` | about | no |
| `regard` | regarding | no |
| `van` | from | no |
| `unter` | under | no |
| `ovr` | above, over | no |
| `auf` | up, above | no |
| `scherehz` | across | no |
| `bis` | until | no |
| `durh` | through | no |
| `vor` | in front of | no |
| `sorgfalt` | by | no |
| `als` | than | no |
- **PRP-1** The listed prepositions exist, plus (10.0) `radi` (for), `na` (on), `posle` (after), `ohne` (without), `vne` (out of), `nieder` (down), and `tu na` (onto) (PREP-N1), and the time/place words `vorhe` "before" and `nahe` "near".  Safe equivalences: "into/towards" -> `tu`; "inside/within" -> `en`; "at" -> `zu`; "together with" -> `mit`; "concerning" -> `darab`.
- **PRP-2 Article fusion.** `tu` + `den` -> `tu'den`; `en` + `den` -> `en'den`; `zu` + `den` -> `zu'den`; `tu` + `deny` -> `tu'deny`; `en` + `deny` -> `en'deny`; `zu` + `deny` -> `zu'deny` (GEN-6). Fusion happens **only** with `den` / `deny`, never with `ein`, `eine`, `dehyss` or a bare noun, and **only** for these three prepositions.
  ✔ `tu'deny aufsita` ✔ `tu'den konig` ✔ `tu eine aufsita` ✔ `mit deny key` ✔ `av den konig` ✘ `tu deny aufsita` ✘ `mit'deny key` ✘ `av'den konig`
- **PRP-3** Prepositional phrases never take a direct-object role (NEG-5).

### 10.5 Adjectives and adverbs
- **ADJ-1** No adverbial suffix exists. The base adjective works as an adverb **after the verb**: `Yem ruhn kvik.` ("I run quickly.") ✘ `kvikly`, `kvikli`.
- **ADJ-2** Nuanced actions are built as **Verb + Adjective**: `vak kvik` ("walk quickly" = sprint). Never invent a new verb outside Module 16A (LEX-2).
- **ADJ-3** With an object, the manner adverb stands after the object (ISO-1): `Yem spile Roblox kvik.` [DERIVED]
- **ADJ-4** Predicate adjectives follow the experiencer rules below.
- **ADJ-5 An adjective is never a verb.** It never takes `-nu`, `-u` or `-en`. For "complete / finish X" with no verb entry, use LEX-3: `mek` + object + adjective: `Su muss dehyss kompletn meken.` [DERIVED] [GAP G-34]

### 10.6 Plurals
- **PLU-0 Gender is kept.** Pluralizing never changes the article's gender (GEN-5): `den konigeni`, `deny aufsitaeni`, `deny spilezeng`.
- **PLU-1 Algorithm (Module 14.4):** (1) ends in `zung` -> `zeng`; (2) otherwise, ends in `e` or `n` -> drop that letter, add `eni`; (3) otherwise add `eni`.
- **PLU-2 `-zung` nouns:** `spilezung` -> `spilezeng`; `vsespilezung` -> `vsespilezeng`.
- **PLU-3 Mash-up nouns:** apply the same end-letter rules to the **absolute end** of the whole word: `jad'ze` -> `jad'zeni`. [RESOLVED: the earlier text "add `eni` to the absolute end" would give `jad'zeeni`; the attested form is `jad'zeni`.]
- **PLU-4 After a number above one the noun is plural:** `doiwikn Nein penkeni`. After `Ein` / `ein` it is singular.
- **PLU-5** Adjectives, articles and possessives do not pluralize. Demonstratives use `dehysseni`.
- **PLU-6** Mass nouns stay singular (`wasser`): `den wasser`.
- **PLU-7 Dictionary plural headwords win** (DIC-7): also `sistemz`, `strukturz`, `skilz`. The dictionary also shows the algorithm at work: `derzhe` -> `derzheni` ("states").
| Singular | Plural | Path |
| :--- | :--- | :--- |
| `hze` | `hzeni` | ends in `e` |
| `buch` | `bucheni` | default |
| `apel` | `apeleni` | default |
| `penk` | `penkeni` | default |
| `konig` | `konigeni` | default |
| `briv` | `briveni` | default |
| `aufsita` | `aufsitaeni` | default |
| `spilezung` | `spilezeng` | `-zung` |
| `spilemann` | `spilemaneni` | ends in `n` |
| `jad'ze` | `jad'zeni` | mash-up, ends in `e` |
| `derzhe` | `derzheni` | ends in `e` (dictionary example) |
| `dehyss` | `dehysseni` | default |

### 10.7 Comparatives and superlatives
- **CMP-1 Comparative:** base adjective + `n`. `xnekst` -> `xnekstn` ("greater"). [RESOLVED: older files misspelled it `xneksn`.]
- **CMP-2 Superlative:** base adjective + `t`. `xnekst` -> `xnekstt` ("greatest").
- **CMP-3 "than"** = `als`: `Roblox doun xnekstn als Minecraft.` ("Roblox is greater than Minecraft.")
- **CMP-4** Apply to any adjective by the same rule (`kvik` -> `kvikn`, `kvikt`). Never use `-er` / `-est` or "more" / "most".
- **CMP-5 [GAP] "as ... as", "less", "least".** No form defined; fallback: rephrase with a comparative.

### 10.8 Predicate adjectives and the Experiencer rule
Used when an adjective is the predicate and an evaluator ("to me", "for him") matters.
- **EXP-1** If the **subject is also the experiencer**, omit the dative pronoun.
- **EXP-2** If the **subject is not the experiencer** and the experiencer is stated: `[Subject] [helper] [dative pronoun] [adjective]`. Use the Object/Dative column of 6.1 (`mi`, `ben`/`sein`, `su`, `er`, `she`, `yemvyeni`, `dehyr`).
- **EXP-3** If no experiencer is stated, use no dative: `Roblox doun xnekst.`
✔ `Roblox doun mi xnekst.` ("Roblox is great to me.")
✔ `Roblox doun er xnekst.` ("Roblox is great to him.")
✔ `Roblox shoun mi xnekst.` ("Roblox was great to me.") [DERIVED]
✔ `Roblox doun xnekst.` ("Roblox is great.") [DERIVED]
✘ `Roblox doun Ya xnekst.` (nominative pronoun used as dative) ✘ `Yem mi xnekst.` (subject == experiencer: no dative)

---

## MODULE 11 - SEMANTIC BIFURCATION (`Et`/`Es`, `Dah`/`Daz`)

English "it" and "there" each map to **two** Schalowitsk words. Decide by meaning, never by form.

### 11.1 "It"
- **REF-1 `Et`:** abstract concepts, weather, time, atmosphere, general situations, dummy ("it is...") subjects, ideas.
- **REF-2 `Es`:** tangible, concrete, physical objects you could point to or hold.
- **Test:** Can you point at it or pick it up? Yes -> `Es`. No -> `Et`.
- **REF-2a** When "it" refers back to a noun, classify by that noun: `key`, `apel`, `aufsita` -> `Es`; an idea, plan, task, situation -> `Et`.
- **REF-2b Default** for an object "it" after a physical-action verb (find, take, eat, open, click) when the referent is unknown: `Es`. Default for a dummy subject: `Et`.
✔ `Et doun regen.` ("It is raining.")
✔ `Dehyss doun es.` ("This is it.")
✔ `Stevad Ben es!` ("Find it! [a physical thing]")
✘ `Es doun regen.` ✘ `Stevad Ben et!` (when the thing is a physical object) [RESOLVED: v6.0 and v7.0 wrote `Stevad Ben et!`; v8.0 and the bifurcation rule require `es` for tangible objects.]

### 11.2 "There"
- **REF-3 `Dah`:** existential "there is / there are". Form: `Dah [doun/dorn/shoun/shorn/geht] [noun phrase]`. Plural noun -> `dorn` / `shorn`.
- **REF-4 `Daz`:** a physical place you can point to or travel to ("over there", "go there").
✔ `Dah doun ein konig.` ("There is a king.")
✔ `Dah dorn konigeni.` ("There are kings.") [DERIVED]
✔ `Dah doun unruhig.` ("There is unrest.")
✔ `Gehk daz!` ("Go there!") general; `Gehk Ben daz!` targeted
✔ `Yem gehk daz.` ("I go there.")
✘ `Daz doun ein konig.` ✘ `Gehk dah!`
- **REF-5 "here"** = `hier` (dictionary), a plain adverb that follows the verb phrase (ISO-1): `Yem spile Roblox hier.` [DERIVED position]

---

## MODULE 12 - INTERROGATIVES AND REGISTER

### 12.1 Register resolution
- **REG-1** Decide the register **once per sentence/conversation** in this order:
  1. An explicit user instruction ("informal", "to my friend", "formal") wins.
  2. Else textual cues:
     | Informal (`Ben`, informal helpers) | Formal (`Su`, formal helpers) |
     | :--- | :--- |
     | gaming context or game names, "gg", "noob", "lol", "bro/dude/mate/buddy", slang, chat-style exclamations, talk to a friend or peer | polite markers ("please", "sir", "would you"), strangers, customers, official or professional text |
  3. Else **FORMAL** (the default).
- **REG-2 Effects of register:**
  | Element | Formal | Informal |
  | :--- | :--- | :--- |
  | "you" | `Su` | `Ben` |
  | question helper (HLP-2) | `chez` `chel` `chaz` `chom` | `kez` `kel` `kaz` `kom` |
  | "key" | `schluessel` | `key` |
  | "please" | `Plis` at the **start** | `Plis` at the **end** |
- **REG-3 Question helpers** appear only in direct questions, never in statements or commands. Both registers need one (HLP-1); the register picks the form (HLP-2). Capitalize a helper only when it is sentence-initial.
- **REG-4** Slang inputs are mapped to the dictionary's slang headwords (examples: `rofl`, `achmikh`, `brach`, `oye`, `briv`, `bofik`, `lit`); raw English slang may not remain (NAM-3). A slang or casual headword in the output forces the **informal** register for the whole sentence.
- **REG-5 Consistency.** Keep one register per sentence and, unless a new cue appears, per conversation. Never mix `Su` with a `k-` helper or `Ben` with a `ch-` helper. Never switch between `Ben` and `Su` in neighbouring sentences without a cue. No cue = formal (REG-1). The word "username" or a UI word is not a gaming cue.

### 12.2 Question helpers (new in 9.4)
- **HLP-1 One helper per question, both registers.** Every direct question carries exactly one question helper. Register chooses the form, never the presence. A question without a helper is an error, even in casual chat.
- **HLP-2 Helper table** (fixed forms):
  | Question type | Formal | Informal | Slot |
  | :--- | :--- | :--- | :--- |
  | Yes/No | `chez` | `kez` | Index 0 |
  | WH | `chel` | `kel` | directly after the complete WH-phrase |
  | How | `chaz` | `kaz` | Index 0 |
  | Tag | `chom` | `kom` | last token, after a comma, before `?` |
  Pattern: formal = `ch-`, informal = `k-`. The vowel marks the type: `e` Yes/No, `e` + `l` WH, `a` How, `o` Tag.
- **HLP-3 One only.** Never two helpers in one question.
- **HLP-4 Direct questions only.** Never in statements, commands, subordinate clauses or embedded questions (QST-10).
- **HLP-5 Capitalization.** Only when sentence-initial (Yes/No, How).
- **HLP-6 Pairing.** Formal helper with `Su`, informal helper with `Ben`. A mix is an error. If the sentence has neither (`Yalm`, `Er`...), REG-1 decides. ✘ `Chez Ben`, `Kez Su`, `Seckeh plas chez Su`, `Seckeh chel Ben`. ✔ `Chez Su`, `Kez Ben`, `Seckeh plas chel Su`, `Seckeh kel Ben`.
- **HLP-7 Origin.** `chez` is kept from earlier editions. The other seven were coined for 9.4 as an owner decision (Module 16A, Route B respelling) and are fixed text: never re-coin them. `grad`, `wehl` and `obe` (QST-7, QST-10, QST-12) share this status. They were checked against this file only (G-28).
- **HLP-8 With `Plis`.** `Plis` keeps its slot (PLS-1, PLS-2). "Index 0" for a helper means the first token after a sentence-initial `Plis`.

### 12.3 Question types
| Type | Formal | Informal |
| :--- | :--- | :--- |
| Yes/No | `Chez [Clause]?` | `Kez [Clause]?` |
| WH | `Seckeh [domain] chel [Clause]?` | `Seckeh [domain] kel [Clause]?` |
| How | `Chaz [Clause] Schalowit?` | `Kaz [Clause] Schalowit?` |
| Tag | `[Clause], chom?` | `[Clause], kom?` |

- **QST-1 Yes/No.** No inversion. After the helper the clause has its normal Table A order.
  ✔ `Kez Ben doun spile Roblox?` ✔ `Chez Su doun spile Roblox?`
  ✘ `Ben doun spile Roblox?` (no helper)
- **QST-2 WH questions.** `Seckeh` + a domain word at **Index 0**, then the WH helper:
  | English | Schalowitsk |
  | :--- | :--- |
  | what | `Seckeh` |
  | when | `Seckeh zeit` |
  | who / whom | `Seckeh penk` |
  | why | `Seckeh prichin` |
  | where | `Seckeh plas` |
  | what/which + noun | `Seckeh [noun]`: `Seckeh spilezung` ("what game") [DERIVED] |
  | how many | `Seckeh viel [plural noun]` (QST-7) |
  | how much | `Seckeh melok [noun]` (QST-7) |
  | how + adjective/adverb (old, far, fast, often) | `Seckeh grad [adj]` (QST-7) |
  | which (one) | `Seckeh wehl` (QST-12) |
  | whose + noun | `Seckeh penk av-[noun]` (QST-12) |
  The pattern is productive: `Seckeh` + any dictionary noun means "what / which [noun]".
- **QST-3 WH-phrases do not trigger V2.** After the full WH-phrase comes the WH helper, then the clause in **normal order**, fused forms allowed: `Seckeh chel Yem mek?` [DERIVED]; `Seckeh chel Yalm?` ("What are we doing?") [RESOLVED: the Guide wrote `Seckeh Yal dorn?`; the fused form `Yalm` is the current standard.]
- **QST-4 "How" (manner) is `Schalowit` and only `Schalowit`.** It must be the **last token before the final punctuation**. It is never fronted and never co-occurs with `Seckeh`. How + adjective (degree) is QST-7, not this rule.
  ✔ `Kaz Ben doun Schalowit?` ✔ `Chaz Su doun Schalowit?` ✔ `Kaz Ben doun daz Schalowit?` ✔ `Kaz Ben doun spile Schalowit?` [DERIVED]
  ✘ `Schalowit Ben doun?` ✘ `Seckeh Ben doun?` (for "how") ✘ `Kaz Ben doun Schalowit daz?`
- **QST-5 Worked WH examples:**
  ✔ `Seckeh penk chel Su doun bist?` ("Who are you?") formal (ROL-7)
  ✔ `Seckeh penk kel Ben doun bist?` ("Who are you?") informal (ROL-7)
  ✔ `Seckeh kel Ben doun spile?` ("What are you playing?") [DERIVED]
  ✔ `Seckeh plas kel Ben doun gehk?` ("Where are you going?") [DERIVED]
  ✔ `Seckeh zeit kel Ben doun spile?` ("When do you play?") [DERIVED]
  ✔ `Seckeh prichin kel Ben doun spile?` ("Why are you playing?") [DERIVED]
  ✔ `Seckeh chel Yalm?` ("What are we doing?")
- **QST-6 Answers:** `Jak` (yes), `Nu` (no). Answers carry no helper.
- **QST-7 Quantity and degree questions.** [RESOLVED in 9.4; the old gap is closed]
  - how many: `Seckeh viel` + **plural** noun (`-eni`, MOR-4a). ✔ `Seckeh viel spilezungeni kel Ben doun spile?` [DERIVED]
  - how much: `Seckeh melok` + singular noun. ✔ `Seckeh melok izeug chel Su doun haben?` [DERIVED]
  - how + adjective or adverb (old, far, long, fast, often): `Seckeh grad [adj]`. ✔ `Seckeh grad kvik kel Ben doun ruhn?` ("How fast do you run?") ✔ `Seckeh grad ofte kel Ben doun spile?` [DERIVED]
  - If the dictionary has no word for the adjective, coin it under Module 16A (G-29).
  - Never `Seckeh [adj]` alone for degree, and never `Schalowit` for degree.
- **QST-8 Negated questions** use the NEG algorithm: `Kez Ben doun spilenu Roblox?` [DERIVED]
- **QST-9 Tag questions** ("isn't it?", "don't you?", "right?", "okay?"). [DERIVED]
  - Form: a full **statement** clause (statement frames allowed: V2, modal), then a comma, then the tag helper as the **last token**: `[Clause], chom?` / `[Clause], kom?`.
  - The tag helper never changes with polarity and never repeats the verb. It replaces every English tag.
  - A tag question has no Index-0 helper, no `Seckeh` and no `Schalowit`.
  - A modal clause keeps its `-en` verb last inside the clause; the tag follows the comma (exempt from MOD-2).
  ✔ `Ben doun spile Roblox, kom?` ✔ `Su doun spile Roblox, chom?` ✔ `Ben doun spilenu Roblox, kom?` ✔ `Ben kahn Roblox spilen, kom?`
  ✘ `Ben doun spile Roblox kom?` (no comma) ✘ `Kez Ben doun spile Roblox, kom?` (two helpers)
- **QST-10 Embedded questions.** [DERIVED]
  - A WH-phrase or `obe` ("whether / if") opens a **subordinate clause** in SUB-3 order: `[Main clause] [Seckeh ... / obe] [S] [O] [V] [H]`.
  - The embedded clause has **no helper** and no `?` of its own. If the whole sentence is a question, the helper belongs to the main clause.
  - `wehn` stays "if / when" for conditionals only (SUB-6). `obe` is only "whether".
  ✔ `Yem sehen Seckeh Ben spile doun.` ("I see what you play.")
  ✔ `Yem sehen obe Su Roblox spile doun.` ("I see whether you play Roblox.")
  ✔ `Kez Ben doun sehen Seckeh Ya spile doun?` ("Do you see what I play?")
- **QST-11 Frames.** Helper + modal: `Kez Ben kahn Roblox spilen?`, `Seckeh kel Ben kahn spilen?` (MOD-9). Frame priority is unchanged (7.9): the question frame outranks V2 and modal, so no inversion.
- **QST-12 "Which" and "whose".**
  - which + noun = `Seckeh [noun]` (QST-2). Never `Seckeh wehl [noun]`.
  - which (one/ones), standalone: `Seckeh wehl`. ✔ `Seckeh wehl kel Ben doun spile?`
  - which of: `Seckeh wehl av [NP]`. ✔ `Seckeh wehl av deny spilezungeni kel Ben doun spile?` [DERIVED]
  - whose + noun: `Seckeh penk av-[noun]` (POS-3 hyphen form, no article on the noun). ✔ `Seckeh penk av-aufsita chel Su doun sehen?` [DERIVED]
- **QST-13 [GAP] "how come", "what for", stranded prepositions.** Fallback: rephrase with `Seckeh prichin` or `Seckeh` + a noun; otherwise `[UNKNOWN]`.
- **QST-14 Subject WH-questions** (the WH word is the subject: "Who is doing that?", "What is going on?"). The clause after the helper has only the singular core: `Seckeh [domain] [helper] doun [V] [O]?` (`shoun` past, `geht` future). Never drop the core (FIN-1). The helper follows REG-1; with no `Su` / `Ben` in the clause it defaults to formal. ✔ `Seckeh penk chel doun tyern dehyss?` ✔ `Seckeh chel doun pass?` ✘ `Seckeh penk kel tyern dehyss?` [DERIVED]
- **QST-15 Copular WH-questions with a noun subject** ("What is your username?"): `Seckeh [domain] [helper] [noun phrase] doun?`, built like `Seckeh penk chel Su doun?`. The possessor stays on the noun with `av'` (POS-2); "your" never becomes the subject. ✔ `Seckeh chel usernam av'su doun?` ✘ `Seckeh kel Ben doun den usernam?` [DERIVED]
- **QST-16 Embedded manner clause** ("how I like it", "the way I play"): Table C order inside the clause, with `Schalowit` as its last word. When this clause ends the sentence, `Schalowit` is also the last token before the final punctuation (L15). A subordinate clause may follow the infinitive of a modal frame; MOD-2 governs only the infinitive's own clause. ✔ `Yem kahn den tekst merkaen Ya et lyuba doun Schalowit.` [DERIVED] [GAP G-32]


---

## MODULE 13 - IMPERATIVES AND POLITENESS

### 13.1 Targeted versus general
```
Is the command addressed to a specific person or group
(named, "you", pointing, a chat participant, a teammate)?
   |
   +-- YES --> TARGETED:  [V] [Ben/Su] [O] [PP / adverb] !
   |
   +-- NO  --> GENERAL:   [V] [O] [PP / adverb] !
```
- **IMP-1 Imperative frame.** No subject, no core/helper, no tense, no V2, no fused form. The verb is in **dictionary form** (not `-en`). ✘ `Schreiben Ben dehyss.` (German infinitive; the dictionary root is `schrei`) ✔ `Schrei dehyss.`
- **IMP-2 Targeted:** the verb is followed immediately by the target pronoun, then the object.
  ✔ `Stevad Ben es!` ✔ `Stevad Ben deny key!` ✔ `Gehk Ben daz!`
- **IMP-3 General:** broad announcements, signs, UI buttons, instructions with no addressee.
  ✔ `Stevad es!` ✔ `Stevad deny key!` ✔ `Gehk daz!` ✔ `Kluk dehyss!`
- **IMP-4 Cues for "targeted"**: "you", a name or vocative ("John, ..."), "hey", "teammate", mention of pointing or looking at the person, an in-chat order to a participant. **Cues for "general"**: signs, button labels, recipes, tutorials, headlines, no addressee. **If there is no cue, use GENERAL.** [DERIVED]
- **IMP-5 Pronoun choice** follows register (REG-1): informal -> `Ben`, formal -> `Su`. With `Su` the object noun is `schluessel` not `key` (REG-2): `Stevad Su den schluessel!`
- **IMP-6 Object "it"** follows REF-1/2: tangible -> `es`. `Stevad Ben es!`
- **IMP-7 Prefixed verbs stay whole:** `Austrink Ben den wasser!` [DERIVED]
- **IMP-8 Negative imperatives:** `Stevadnu Ben es!`, `Gehk nucht!` (NEG-7).
- **IMP-9 Vocatives:** a name before the command is kept with a comma, and the pronoun is still inserted: `John, stevad Ben es!` [DERIVED]
- **IMP-10 "Let's ..." (hortative)** is resolved in 10.1 by HRT-1: `lez Yal [V] [O]!` (Module 28.5).
✘ `Stevad Ben et!` (physical object) ✘ `Ben stevad es!` (pronoun before verb) ✘ `Stevad es Ben!` ✘ `Yem stevad es!` (a subject in a command) ✘ `Gehken daz!` (infinitive in a command) ✘ `Doun Ben stevad es!`

### 13.2 Politeness (`Plis`)
- **PLS-1** Add `Plis` only if the English contains "please".
- **PLS-2** Formal: `Plis` at the **start** of the sentence. Casual: `Plis` at the **end**, just before the final punctuation.
  ✔ `Plis stevad Su den schluessel!` ✔ `Stevad Ben deny key plis!` [DERIVED]
- **PLS-3** If a casual sentence ends with `Schalowit`, `Schalowit` stays last (QST-4).
- **PLS-4** `Grahdtuhd` = "thank you"; `Halo` = "hello"; `Adjo` = "goodbye"; `Ok`, `Jak`, `Nu` as listed in 5.3. An interjection at the start of a sentence is followed by a comma and does not trigger V2 (V2-3): `Halo, Yem spile Roblox.`

---

## MODULE 14 - MORPHOLOGY

All derivations start from the **dictionary root** of the verb (the form in `Dictionary.json`, e.g. `spile`, never the infinitive `spilen`). All results are lower-case mid-sentence (ORT-4).

### 14.1 Nominalization `-zung` (verb -> noun/object/state)
- **MOR-1** Applies to **verb roots**. If the root ends in `e`, `t`, `z`, `x`, `d`, `r`, `a` or `i`, **drop that last letter**, then add `zung`; otherwise add `zung` directly.
  **A dictionary headword always wins.** `spile` -> `spilezung` ("game") is a lexicalized exception: the dictionary keeps the `e`. [RESOLVED: the Guide's drop rule would give `spilzung`, but `Dictionary.json`, v6.0, v7.0 and v8.0 all use `spilezung`.] Other dictionary `-zung` nouns attach to their base whole (`zeit` -> `zeitzung`, `meister` -> `meisterzung`, `drhn` -> `drhnzung`), because their bases are nouns, not verbs.
  For any other `e`-final verb root with no headword, follow the rule text (drop the `e`). [GAP G-21: the only attested `e`-final example keeps its `e`; the owner should confirm whether the drop rule applies to `e` at all.]
  Mechanical demonstrations (not vocabulary): `mek` -> `mekzung`; `iz` -> `izung`; `stevad` -> `stevazung`; `gehk` -> `gehkzung`; `bau` -> `bauzung`; `ruhn` -> `ruhnzung`.

### 14.2 Agent `-mann` (verb -> doer)
- **MOR-2** Attach `mann` directly to the root. Nothing is dropped. `spile` -> `spilemann` ("player"). Mechanical: `iz` -> `izmann`; `mek` -> `mekmann`.

### 14.3 Infinitive `-en` (modal frames only)
- **MOR-3** Root already ends in `-en` -> **unchanged** (it is its own infinitive). Root ends in `e` -> add `n`. Any other ending -> add `en`. Prefixed roots keep their prefix.
  | Root | Infinitive |
  | :--- | :--- |
  | `spile` | `spilen` |
  | `mek` | `meken` |
  | `gehk` | `gehken` |
  | `trink` | `trinken` |
  | `bau` | `bauen` |
  | `iz` | `izen` |
  | `brauch` | `brauchen` |
  | `stevad` | `stevaden` |
  | `verlassen` | `verlassen` (unchanged) |
  | `haben` | `haben` (unchanged) |
  | `sehen` | `sehen` (unchanged) |
  | `denken` | `denken` (unchanged) |
  | `kome` | `komen` |
  | `ruhn` | `ruhnen` |
  | `austrink` | `austrinken` |
  | `angehk` | `angehken` |
  The infinitive exists **only** at the end of a modal frame (MOD-2) and is **never** negated with `-nu`. It is not a base form for derivation.

### 14.4 Plural `-eni` / `-zeng`
- **MOR-4a** Algorithm: (1) ends in `zung` -> replace with `zeng`; (2) ends in `e` or `n` -> drop that letter, add `eni`; (3) otherwise add `eni`. Mash-up nouns follow the same rules at the absolute end (PLU-3). Examples: see PLU table (10.6).

### 14.5 Compounds (plain glue, resolved 10.1)
- **MOR-4 Plain glue.** A compound noun is two elements written as **one lower-case word**: `[modifier][head]`. The modifier comes first, the head (the thing itself) comes last, as in English. Nothing is dropped, no apostrophe, no hyphen. The modifier may be a noun or an adjective. ✔ `izeughze` (food house) ✔ `konigaufsita` (king's castle) ✔ `sicherbremol` (security guard, ROL-12)
- **MOR-4d Head rules.** The head decides gender (GEN-4, GEN-7), the article, the plural (MOR-4a, applied at the absolute end) and the female suffix (ROL-4). ✔ `deny izeughze`, plural `izeughzeni` ✔ `deny konigaufsita`, plural `konigaufsitaeni` ✔ `den sicherbremol`, plural `sicherbremoleni`
- **MOR-4e Two elements maximum.** A concept with three or more elements uses the possessive phrase: `[head] av [modifier]`. ✔ `hze av izeughze` ✘ `izeughzekonig`
- **MOR-4b Lexicalized compounds override.** `jad'ze` (supermarket) is kept verbatim with its apostrophe, plural `jad'zeni` (PLU-3). It is the only apostrophe compound; new compounds never use one. A dictionary headword always wins over a glued form.
- **MOR-4c Fallback.** If a glued compound would be unclear, use the phrase `[head] av [modifier]`: `hze av izeug`. Both parts must exist in the dictionary (or be coined by Module 16A) first (COIN-1).

### 14.6 Verb prefixes (inseparable)
- **MOR-5 Meanings** (use a prefix only when the English carries the meaning):
  | Prefix | Function | English cues | Example |
  | :--- | :--- | :--- | :--- |
  | `an-` | Inchoative: onset, start | set off, start to, begin to | `gehk` -> `angehk` ("set off"): `Yem angehk.` |
  | `wieder-` | Iterative / excess: redo, over- | re-, again, redo | `mek` -> `wiedermek` ("remake"): `Er shoun wiedermek den task.` |
  | `aus-` | Completion / thoroughness | finish, completely | `trink` -> `austrink` ("finish drinking"): `Su geht austrink den wasser.` |
- **MOR-6 Inseparability.** The prefix is glued to the verb **in every position**: SVO, V2, subordinate clauses, modal frames, negation, imperatives. It never detaches to the clause end. ✘ `Yem gehk an` ✘ `Yem gehk ... an` ✘ `Yem wieder mek`
  ✔ `Yem muss den wasser austrinken.` ✔ `Yem austrinknu den wasser.` ✔ `Austrink Ben den wasser!` [DERIVED]

### 14.7 Noun prefixes
- **MOR-7** Prefixes attach to the (possibly derived) noun; the **whole word is lower-case** mid-sentence.
  | Prefix | Function | Example |
  | :--- | :--- | :--- |
  | `un-` | negation / antonym noun | `ruhig` ("quiet") -> `unruhig` ("restless / unrest"): `Dah doun unruhig.` [RESOLVED: v5.0 glossed `ruhig` as "peace"; the dictionary says quiet; "peace" = `friede`] |
  | `urz-` | primeval / arch- / high | `konig` -> `urzkonig` ("high king"): `Den urzkonig shoun bau deny aufsita.` |
  | `sam-` | collective / co- / teammate | `spilemann` -> `samspilemann`: `Yem brauch ein samspilemann.` |
  | `vse-` | total inclusion ("every ...") | `spilezung` -> `vsespilezung`: `Yem spile vsespilezung.` |

### 14.8 Order of operations
**derive** (`-zung` / `-mann`) -> **noun prefix** -> **plural**. Example: `spile` -> `spilemann` -> `samspilemann` -> `samspilemaneni`.
For verbs: **verb prefix** -> **negation `-nu`** *or* **infinitive `-en`**.

### 14.9 Morphology test vectors (normative)
There is no code in this specification. Apply the prose rules in 14.1 to 14.8. These test vectors are authoritative: if a rule and a vector ever disagree, the vector wins and the disagreement is logged in Module 25.

| Operation | Input | Result | Rule |
| :--- | :--- | :--- | :--- |
| Nominalize (`-zung`) | `spile` | `spilezung` (lexicalized headword) | MOR-1 |
| Nominalize | `mek` | `mekzung` | MOR-1 |
| Nominalize | `iz` | `izung` | MOR-1 |
| Agent (`-mann`) | `spile` | `spilemann` | MOR-2 |
| Infinitive | `spile` | `spilen` | MOR-3 |
| Infinitive | `mek` | `meken` | MOR-3 |
| Infinitive | `austrink` | `austrinken` | MOR-3 |
| Infinitive | `verlassen` | `verlassen` (already ends in `-en`) | MOR-3 |
| Reflexive | `Su` | `suselb` | RFL-1..5 |
| Reflexive | `Ben` | `benselb` | RFL-1..5 |
| Reflexive | `Er` | `erselb` | RFL-1..5 |
| Reflexive | `She` | `sheselb` | RFL-1..5 |
| Reflexive | `Yal` | `yalselb` | RFL-1..5 |
| Reflexive | `Dehye` | `dehyeselb` | RFL-1..5 |
| Reflexive | `Es` | no form (GAP, output `[UNKNOWN:itself]`) | RFL-6 |
| Verb prefix | `aus` + `trink` | `austrink` | MOR-5 |
| Noun prefix | `sam` + `spilemann` | `samspilemann` | MOR-7 |
| Plural | `apel` | `apeleni` | MOR-4a |
| Plural | `spilezung` | `spilezeng` | MOR-4a |
| Chain | `spile` -> agent -> `sam-` -> plural | `spilemann` -> `samspilemann` -> `samspilemaneni` | 14.8 |


---

## MODULE 15 - ALGORITHMIC NUMBERS (1-99)

Do **not** look numbers up in a dictionary. Generate them.

* **NUM-1 Digits:** 0 `Zer`, 1 `Ein`, 2 `Doiw`, 3 `Dry`, 4 `Caut`, 5 `Foiw`, 6 `Seiz`, 7 `Sieb`, 8 `Akch`, 9 `Nein`.

* **NUM-2 Tens:** Base + `-ik` (exception: 10 is `dezi`): 10 `dezi`, 20 `doiwik`, 30 `dryik`, 40 `cautik`, 50 `foiwik`, 60 `seizik`, 70 `siebik`, 80 `akchik`, 90 `neinik`.

* **NUM-3 Compounding:** `[Tens]n [Units]` (e.g., 21 = `doiwikn Ein`, 11 = `dezin Ein`).

* **NUM-5 Capitalization:** Standalone digits and the unit part of a compound start capitalized (`Ein`, `Doiw`, `doiwikn Nein`). **Tens (`doiwik` ... `neinik`), `dezi`, `hundert`, `tausend`, `milion` and ordinals are always lower-case** (ORT-4.4); only a sentence start capitalizes them (ORT-4.1). Standalone 10 is `dezi`. The single digit used as an **article** ("a / one") is lower-case `ein`; as a counting word in a list it is `Ein`.

* **NUM-6 Range:** 0 to 999,999,999 are generated (NUM-10, NUM-14). The dictionary adds `hundert` (100). Decimals, fractions and percent are generated by NUM-11 to NUM-13 (10.1). Millions (to 999,999,999) and negatives are generated by NUM-14 and NUM-15 (10.1). \[GAP: 1,000,000,000 and above. Fallback: write Arabic digits.\]

* **NUM-9 Dictionary confirmation.** The dictionary contains the digits 0-9 and deliberately leaves `ten`, `twenty`, `thirty` (and the entry for `eight`) **empty**: they are generated, not listed. Ordinals exist only as `vralet` (first) and `flumed` (second); \[GAP: other ordinals\].

* **NUM-7 In a noun phrase:** `[numeral] [plural noun]`: `doiwikn Nein penkeni` ("twenty-nine people"), `Dry spilezeng` ("three games"). "One game" = `eine spilezung`.

* **NUM-8 Spaced notation:** `[Tens]n [Units]`, with a space after `n` and the unit capitalized (`doiwikn Ein`, `dezin Nein`).

| Tens \\ Unit | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 
| ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | 
| **0x** | `Zer` | `Ein` | `Doiw` | `Dry` | `Caut` | `Foiw` | `Seiz` | `Sieb` | `Akch` | `Nein` | 
| **1x** | `dezi` | `dezin Ein` | `dezin Doiw` | `dezin Dry` | `dezin Caut` | `dezin Foiw` | `dezin Seiz` | `dezin Sieb` | `dezin Akch` | `dezin Nein` | 
| **2x** | `doiwik` | `doiwikn Ein` | `doiwikn Doiw` | `doiwikn Dry` | `doiwikn Caut` | `doiwikn Foiw` | `doiwikn Seiz` | `doiwikn Sieb` | `doiwikn Akch` | `doiwikn Nein` | 
| **3x** | `dryik` | `dryikn Ein` | `dryikn Doiw` | `dryikn Dry` | `dryikn Caut` | `dryikn Foiw` | `dryikn Seiz` | `dryikn Sieb` | `dryikn Akch` | `dryikn Nein` | 
| **4x** | `cautik` | `cautikn Ein` | `cautikn Doiw` | `cautikn Dry` | `cautikn Caut` | `cautikn Foiw` | `cautikn Seiz` | `cautikn Sieb` | `cautikn Akch` | `cautikn Nein` | 
| **5x** | `foiwik` | `foiwikn Ein` | `foiwikn Doiw` | `foiwikn Dry` | `foiwikn Caut` | `foiwikn Foiw` | `foiwikn Seiz` | `foiwikn Sieb` | `foiwikn Akch` | `foiwikn Nein` | 
| **6x** | `seizik` | `seizikn Ein` | `seizikn Doiw` | `seizikn Dry` | `seizikn Caut` | `seizikn Foiw` | `seizikn Seiz` | `seizikn Sieb` | `seizikn Akch` | `seizikn Nein` | 
| **7x** | `siebik` | `siebikn Ein` | `siebikn Doiw` | `siebikn Dry` | `siebikn Caut` | `siebikn Foiw` | `siebikn Seiz` | `siebikn Sieb` | `siebikn Akch` | `siebikn Nein` | 
| **8x** | `akchik` | `akchikn Ein` | `akchikn Doiw` | `akchikn Dry` | `akchikn Caut` | `akchikn Foiw` | `akchikn Seiz` | `akchikn Sieb` | `akchikn Akch` | `akchikn Nein` | 
| **9x** | `neinik` | `neinikn Ein` | `neinikn Doiw` | `neinikn Dry` | `neinikn Caut` | `neinikn Foiw` | `neinikn Seiz` | `neinikn Sieb` | `neinikn Akch` | `neinikn Nein` | 

---

## MODULE 16 - WORD FORGING AND THE MISSING-WORD PROTOCOL

- **LEX-1 Lookup order** (Module 2.4): `Dictionary.json` (non-empty entry) -> guide-only words (Module 19.1) -> phrasing solution (LEX-3) -> **coining (Module 16A)** -> `[UNKNOWN:word]`. An empty dictionary entry counts as "not found" (DIC-2).
- **LEX-2 The Immutable Rule.** Never alter, mash or re-spell a **listed** verb, adjective or adverb. Dictionary roots stay absolute for syntactic stability. A new word may exist **only** if it is coined by the Module 16A procedure. Never "German-ify" or "Russian-ify" English words by hand, even though many roots look Germanic (`heim`, `brauch`, `wasser`, `konig`); Module 16A has its own fixed respelling rules.
- **LEX-3 Phrasing solutions** (use before giving up):
  | Need | Solution | Attested example |
  | :--- | :--- | :--- |
  | A nuanced action | Verb + Adjective | `vak kvik` = "sprint" (walk + quick) |
  | A complex concept | `mek` + state noun | `mek schtobe` = "configure" (make order) |
  | Turn on / activate | `begin` | `begin` (dictionary: start = `begin`) |
  | A new noun concept | glued compound (MOR-4), or `[head] av [modifier]` (MOR-4c) | `izeughze` = "food house" |
  | A near-synonym exists | Use the single idiomatic word, not a word-for-word English phrase | |
  | An idiom for an event | `pass` (happen) | `Seckeh chel doun pass?` = "What is going on?" |
  | An idiom for a change of state | `tudoun` (become) + adjective | `She doun tudoun verrukt.` = "She is going insane." |
  | "go for a walk" | `vak` alone | `Vak.` |
- **LEX-4 Last resort:** only after Module 16A is excluded (COIN-1) or every candidate fails COIN-6, output `[UNKNOWN:english_word]` in the exact position the word would occupy, and still finish the rest of the sentence correctly. This makes gaps visible and searchable; it is never an excuse to leave English in the sentence.
- **LEX-5 Listed English-looking words** (`key`, `Roblox`) are legal only because they are listed in the dictionary or Module 19.1. An English word that is **not** listed is not legal, and a coined word must never be spelled like one (COIN-6).
- **LEX-6 Do not translate word-for-word through English idioms.** Map the meaning, not the phrase (a "piece of cake" is not `iz`-something). Use Module 18.4 for the three listed idioms; otherwise paraphrase with listed words or fall back to LEX-4.

---

## MODULE 16A - CONTROLLED WORD COINING (replaces most `[UNKNOWN]` output)

**Purpose:** When a **content word** is missing, coin a new Schalowitsk word by the fixed procedure below instead of printing `[UNKNOWN:word]`. The procedure is deterministic: the same English word must always produce the same coined word. Coined words are tagged [DERIVED] and follow every grammar rule like dictionary words.

### COIN-1 When to coin (gate)
Coin only if **all** are true:
1. The word is a noun, verb, adjective or adverb.
2. Lookup failed: `Dictionary.json` (all senses, DIC-1), Module 19.1, and the LEX-3 phrasing solutions. An **empty** dictionary entry counts as missing.
3. **No near-synonym exists.** Before coining, search the dictionary for a listed word that carries the core meaning without changing the truth of the sentence. If one exists, use it.
4. **The word is in dictionary form** (LEM-1). Inflected forms are never coined (LEM-2).
5. **Rephrasing with existing words does not keep the exact meaning** (LEX-3, LEM-4d).
6. **It is not an acronym, initialism or name** (NAM-1, NAM-7).

**Never coin:**
- Proper names (NAM-1), countries, languages, demonyms (NAM-2), numbers (Module 15).
- Closed-class words: pronouns, helpers, prepositions, conjunctions, determiners, question words. Keep the old fallbacks (PRP-1). **Exception:** the question helpers (HLP-2) and the question words `grad`, `wehl`, `obe` are owner-approved fixed forms (HLP-7); they are never re-coined.
- Idioms and set phrases. Paraphrase them (LEX-6).
- Garbled or unintelligible input. Output `[UNKNOWN:word]`.
- Inflected forms (`has`, `does`, `trolling`, `chatted`, `sizes`): look up the lemma (LEM-1).
- Acronyms and initialisms (NAM-7).

### COIN-2 Pick one core sense
Choose the single most common sense of the English word and coin for that sense only. Do not try to cover several senses with one coined word.

### COIN-3 Route A: build from existing Schalowitsk words (try first; stop at the first success)
- **A1 Derive.** An existing root plus the Module 14 algorithms: `-mann` (doer), `-zung` (thing/state), prefixes `an-`, `wieder-`, `aus-`, `un-`, `urz-`, `sam-`, `vse-`. Use when the English word means "doer of X", "act or result of X", "again X", "finish X" and so on. Mechanical examples: builder = `bau` + `mann` = `baumann`; rebuild = `wiederbau`.
- **A2 Phrase.** The LEX-3 patterns: verb + adjective, `mek` + state noun, `noun av noun`. Attested: `vak kvik` (sprint), `hze av izeug` (food house).
- **A3 Root blend.** Use only when the concept is clearly "X + Y" and both X and Y are non-empty dictionary roots.
  1. Take the first 2 to 4 letters of X (cut after a vowel, or at a consonant that stays pronounceable).
  2. Take the last 2 to 4 letters of Y, starting at a consonant.
  3. Join them with no hyphen and no apostrophe. Total length 4 to 8 letters.
  4. The result must not equal X or Y.
  Illustrative: `wasser` + `heim` -> `washeim`.

### COIN-4 Route B: borrow and respell (only if Route A fails)
Choose the source language with this table. Go top to bottom and take the first row that fits.

| If the concept is... | Source language | Share of borrowed words |
| :--- | :--- | :--- |
| Another culture's own thing (sushi, tango, kimono) | That language | tiny (about 1 in 20) |
| Technology, games, internet, modern life, or the English form is already short and clear | English | about 40% |
| Structure, measurement, abstract ideas, daily actions, or a clear Germanic cognate exists (water / Wasser) | German | about 30% |
| Nature, feelings, family, social life, slang, or a clear Slavic cognate exists | Russian first; other Slavic only if Russian has no usable form | about 25% |

The shares are tendencies for a batch, not quotas for one word. When one response or session has 6 or more borrowed words, count the sources and send the next close call to the least-used source. Never pick a source language at random.

### COIN-5 Respelling (apply to the borrowed word, in this order)
1. Use only letters Schalowitsk uses (Module 5).
2. **English:** `c` -> `k`, `ck` -> `k`, `qu` -> `kv` (`kvik`), `ph` -> `f`, collapse double letters, drop a silent final `e` (apple -> `apel`).
3. **German:** `ü` -> `u` (`uberstark`), `ä` -> `e`, `ß` -> `s`, `ck` -> `k` (`verrukt`), initial `sp-` -> `schp-` and `st-` -> `scht-` (`schpize`, `schtobe`); keep `sch`, `ei`, `z`, `w` (`heim`, `zeit`, `wasser`).
4. **Russian / Slavic (transliterate):** `ж` -> `zh`, `х` -> `kh`, `ч` -> `ch`, `ш` and `щ` -> `sch`, `й` -> `j`, `ы` -> `i`, `я` -> `ja`, `ю` -> `ju`, `в` -> `v`.
5. **Optional vowel colour:** add one `h` after the stressed long vowel `a`, `o` or `u`, at most once per word (`grahdtuhd`). Never add `h` after `e` or `i` for style.
6. **Shape:** 1 to 3 syllables, 3 to 8 letters preferred (10 maximum), no 3-consonant cluster except `sch`.

### COIN-6 Safety checks (every candidate must pass all)
1. Not identical to any dictionary word, Module 19.1 word, pronoun, helper, preposition, conjunction, or `Schalowit` / `Seckeh` / `nucht`.
2. Differs by more than one letter from any existing word of the same part of speech.
3. Not spelled exactly like an English word (L23). It may equal its German or transliterated Russian spelling.
4. Does not accidentally end in `nu` (negation), `zung`, `mann`, `eni`, `zeng`, and does not accidentally start with `an-`, `wieder-`, `aus-`, `un-`, `urz-`, `sam-`, `vse-` unless that is the intended derivation.
5. Survives the algorithms: infinitive (MOR-3), plural (MOR-4a) and, for verbs, negation `-nu`. Run them on the candidate and confirm nothing collides.
6. One English lemma -> one Schalowitsk word.

If a candidate fails, try the next candidate on the same route (max 3). Then move to the next route. If everything fails, output `[UNKNOWN:word]` (LEX-4).

### COIN-7 Tie-break (when several candidates pass)
1. Route A before Route B. Inside Route A: A1, then A2, then A3.
2. Shorter word.
3. The word an English reader would recognize fastest.
4. Alphabetical order.

### COIN-8 Consistency and use
- Keep a **coinage table** for the session: `english lemma + part of speech -> schalowitsk`. Reuse the stored word every time. Never coin two words for one lemma.
- A coined word behaves exactly like a dictionary word: all grammar rules apply. Do **not** mark it inside the sentence (OUT-1 stays intact).
- If a sentence needs more than 2 coinages, first try to rephrase with existing words (the meaning must stay the same), then coin the rest.
- If the dictionary later contains the word, the dictionary form wins (Module 2.3).

### COIN-9 Worked examples (illustrative; verify against the real dictionary)
| English | Route | Result | Why |
| :--- | :--- | :--- | :--- |
| builder | A1 | `baumann` | `bau` + `mann` (MOR-2) |
| rebuild | A1 | `wiederbau` | `wieder-` + `bau` (MOR-5) |
| window | B, Russian | `okno` | Russian `окно`, short, passes all checks |
| bridge | B, German | `bruke` | Brücke: `ü` -> `u`, `ck` -> `k` |
| computer | B, English | `kompjuter` | tech word, `c` -> `k`, `j` for the "y" sound |
| sushi | B, other | `suschi` | culturally native word, `sh` -> `sch` |

---

## MODULE 17 - PROPER NAMES AND SLANG

- **NAM-1 Preserve verbatim:** people ("John"), brands, software, games ("Roblox"), products, companies ("Microsoft"), fictional characters, specific landmarks. Do not translate, inflect or respell.
- **NAM-2 Look up (do not preserve):** country names, national languages, demonyms, continents. The dictionary lists them as entries with an `entity_type` (examples: `Franzka` France, `Dojtska` Germany, `Tsinoh` China, `Kanada` Canada, `Europana` Europe, `spanisk` Spanish). Descriptive patterns only: countries often end in `-ka`, continents in `-ana`, languages in `-isk`. **Use listed names only; never build a new name from the pattern.** If the dictionary has no entry, keep the original name verbatim. [GAP: major international cities (none seen).]
- **NAM-3 Slang.** The dictionary contains slang headwords (2000s-era register): `rofl` (lol), `achmikh` (omg), `zeltnucht` (nevermind), `brach` (bruh), `oye`, `sup`, `gai`, `gais` (guys), `oyemann` (mate), `briv` (bro), `bofik` (wanna), `lit` (cool), `uberstark` (overpowered), `schpize` (really). Map casual input to these. Never leave unparsed English slang in the output. If no headword exists, paraphrase with listed words; if impossible, `[UNKNOWN:slang]`.
- **NAM-4 Names take no morphology.** No plural `-eni`, no `'s`, no `-zung`, no prefixes. ✘ `Robloxeni` ✘ `John's` ✔ `deny aufsita av John` ✔ `John av-aufsita`
- **NAM-5 Names as subjects** are 3SG nouns: `John doun spile Roblox.` [DERIVED]; `Roblox doun mi xnekst.`
- **NAM-6 Quoted material, code, URLs and numerals in digit form** are copied unchanged.
- **NAM-7 Acronyms and initialisms** (`AI`, `UI`, `URL`, `GPS`) pass through verbatim in capitals, take no morphology and are never coined (LEM-4e). They act as 3SG nouns, article `den` if one is needed. ✔ `AI geht verstehennu dehyss.` ✔ `Dehyss UI doun xnekst!` ✘ `ui`
- **NAM-8 Names, articles and adjectives of nationality.** A name takes no article the English did not have (OUT-5). A multi-word country name built only from dictionary words is translated word by word and capitalized: United States = `Ferjed Derzheni`, a singular name taking `doun` [DERIVED] [GAP G-36]. "Nation" / "state" = `derzhe` (plural `derzheni`). An adjective of nationality or continent ("European") is a demonym entry (`europanisk`, entity_type demonym); never reuse the continent or country word (`Europana`, `Dojtska`) as an adjective.

---

## MODULE 18 - SPECIAL REGISTERS, INDEFINITES, MEDICAL, IDIOMS

### 18.1 Indefinite pronouns
| English | Schalowitsk | Behaviour |
| :--- | :--- | :--- |
| everyone | `alkto` | normal noun/pronoun, 3SG |
| someone | `mankto` | normal |
| anyone | `irgkto` | normal |
| no one | `nimkto` | **absolute negative** (NEG-4) |
| everything | `alscht` | normal |
| something | `manscht` | normal |
| anything | `irgscht` | normal |
| nothing | `nikscht` | **absolute negative** (NEG-4) |
- **SPC-1** They take 3SG cores: `Alkto doun spile Roblox.` ("Everyone plays Roblox.") [DERIVED]; `Nimkto doun spile Roblox.`; `Yem iz nikscht.` [DERIVED].

### 18.2 Medical expressions
- **SPC-2** `[Body-part noun] doun bol` ("the X hurts"): `Deny golowa doun bol.` ("The head hurts / Headache.")
- **SPC-3** Possession: `Deny golowa av'mi doun bol.` ("My head hurts.") [DERIVED]. Plural body parts: `dorn bol` with the plural noun [DERIVED].
- **SPC-4** The pattern is the only defined medical construction. [GAP: "I feel sick", "I have a fever". Fallback: `[UNKNOWN:word]` for the missing noun; do not invent illness words.]

### 18.3 Comparatives and superlatives
See CMP-1 to CMP-5 (10.7). `xnekst` / `xnekstn` / `xnekstt` and `als` ("than").

### 18.4 Idioms (fixed strings)
Idioms are **lexicalized**: output them verbatim, with no core change, no V2, no negation, no plural. Use one only when the English meaning clearly matches.
| Schalowitsk | Literal | Meaning (use when the English means this) |
| :--- | :--- | :--- |
| `Doun fast apel` | "It is almost an apple" | good enough, close enough |
| `Kohmbaht den wasser` | "Fighting the water" | a futile or impossible endeavor |
| `Aufallweiz doun xnekstt` | "Family is greatest" | a warm communal blessing; a fond farewell |

### 18.5 Greetings and survival phrases
`Halo` (hello; the dictionary also has `hallo`), `Adjo` (goodbye; also `vay`), `Jak` (yes), `Nu` (no), `Ok` (ok), `Grahdtuhd` (thank you), `Plis` (please), `verzei` (sorry), `wilkom` (welcome). Capitalize when sentence-initial (ORT-4). Casual greetings (`sup`, `oye`) imply the informal register. [GAP: "good morning", "good night", "thank you very much". The parts exist (`xne` good, `morgen`, `nacht`, `sehr`) but no phrase is listed. Fallback: `[UNKNOWN:phrase]`.]

### 18.6 Conjunctions and connectors (summary)
| English | Schalowitsk | Frame effect |
| :--- | :--- | :--- |
| and | `n` | none (COO-1) |
| but | `br` | none |
| or | `j` | none |
| if / when | `wehn` | subordinate (SUB-1) |
| then | `dashe` | main clause after fronted `wehn`; no V2 |
| because | `wahn` | subordinate |
| that | `dass` | subordinate |
| while | `whilst` | subordinate |
| than | `als` | comparative (CMP-3) |
| about | `darab` | preposition |

---

## MODULE 19 - GUIDE-ONLY WORDS, SUPERSEDED FORMS AND DICTIONARY FACTS

This module is **not** a vocabulary list. `Dictionary.json` holds the words. This module records only (1) the words the AI must keep that the dictionary does **not** contain, (2) old forms that are now superseded, and (3) dictionary facts that change how a rule applies.

### 19.1 Guide-only words (the dictionary is silent, so these are kept)
| Word | Meaning | Used in |
| :--- | :--- | :--- |
| `Yem` `Yeht` `Yalm` `Yahlt` `Dehyt` | fused subject + helper cores | Module 6 |
| `dehysseni` | these / those | NP-2 |
| `dass`, `whilst` | that (conj.), while | SUB-2 |
| `als` | than | CMP-3 |
| `en`, `zu` | in / inside, at | PRP-1 |
| `alsitnu` | never (absolute negative) | NEG-4, FIN-9 |
| `chez` `chel` `chaz` `chom` | formal question helpers: Yes/No, WH, How, Tag | HLP-2 |
| `kez` `kel` `kaz` `kom` | informal question helpers: Yes/No, WH, How, Tag | HLP-2 |
| `grad` | degree word in `Seckeh grad [adj]` (how old / far / fast) | QST-7 |
| `wehl` | which (one) in `Seckeh wehl` | QST-12 |
| `obe` | whether / if in embedded yes/no questions | QST-10 |
| `Es`, `Dah` | it (physical), there (existential) | REF-2, REF-3 |
| `su`, `er`, `she`, `dehyr`, `yemvyeni` | object / dative forms (the dictionary has only `mi`) | 6.1, FIN-10 |
| `alkto`, `mankto`, `irgscht` | everyone, someone, anything (the dictionary has no entry for these) | SPC-1 |
| `konig`, `urzkonig` | king, high king | POS-3, MOR-7 |
| `key`, `schluessel` | key (informal, formal) | REG-2 |
| `schtobe` | order / state, only inside `mek schtobe` ("configure") | LEX-3 |
| `prichin`, `plas` | domain nouns inside `Seckeh prichin` (why) and `Seckeh plas` (where) | QST-2 |
| `unruhig` | restless / unrest (`un-` + `ruhig` "quiet") | MOR-7 |
| `jad'ze` | supermarket (lexicalized compound; plural `jad'zeni`) | MOR-4b |
| `kvik` | quick / quickly (the dictionary entry `quick` is empty, but `kviklusep` "easily" contains `kvik`) | ADJ-1 |
| `Ok`, `heut` | "ok"; short form of `heute` | 5.3, V2-7 |
| `angehk` `wiedermek` `austrink` `samspilemann` `vsespilezung` | prefix-derived words from the Guide and v5.0 | MOR-5, MOR-7 |
| `Doun fast apel`, `Kohmbaht den wasser`, `Aufallweiz doun xnekstt` | the three idioms | 18.4 |
| `radi` `na` `posle` `ohne` `vne` `nieder` | for, on, after, without, out (of), down (10.0) | PREP-N1 |
| `gewor` | passive helper (10.0) | PAS-1 |
| `konj` | subjunctive helper, if-clause only (10.0) | SBJ-1 |
| `wurd` | conditional helper "would" (10.0) | CND-1 |
| `tausend` `milion` | thousand, million (10.0) | NUM-10 |
| `esselb` `etselb` | itself (tangible, abstract) (10.0) | RFL-7 |
| `Roblox`, `Microsoft`, `John` | pass-through names | NAM-1 |

### 19.2 Superseded forms (NEVER output these)
| Old form (guides) | Current form (dictionary) | Meaning |
| :--- | :--- | :--- |
| `kastelv` | `aufsita` | castle |
| `run` | `ruhn` | run |
| `klikat` | `kluk` | click |
| `ruks` | `rukz` | rule / govern |
| `chez` in WH-questions, how-questions or informal questions | `chel` / `chaz`; informal `kez` `kel` `kaz` | question helpers (HLP-2) |
| informal questions with no helper | any question needs one helper | HLP-1 |
| `kann` | `kahn` | can |
| `wolle` | `wolt` | want (dictionary `wolle` = cotton) |
| `darum` | `wahn` | because |
| `pahr` | `darab` | about |
| `alvse` | `alscht` | everything |
| `irgenkto` | `irgkto` | anyone / anybody |
| `vseNm` | `alkto` | everyone |
| `schtojem` | `mankto` | someone |
| `vsedeng` | `alscht` | everything |
| `etvasch` | `manscht` | something |
| `luboman` | `irgkto` | anyone / anybody |
| `anyvasch` | `irgscht` | anything |
| `start` | `begin` | start / activate |
| `sein` (as "your") | `ben` (informal), `su` (formal) | `sein` is now only the numeral six |
| `sebm` | `dehyeselb` | themselves |
| `reflektk` | `sheselb` | herself |
| `verlass` (as the root) | `verlassen` | leave / depart (already an `-en` form) |
| `jade` (as "food") | `izeug` | food (`jade` survives only inside `jad'ze`) |
| `ruhig` = "peace" | `friede` = peace; `ruhig` = quiet | gloss correction |
| `spilzung` (rule-derived) | `spilezung` | game |
| `xneksn` | `xnekstn` | greater (typo) |
| `Ya doun es` (Guide's "I do it") | see FIN-7 | pre-fusion form |

### 19.3 Dictionary facts that affect the rules
- **Removed in 9.5 (spelled like English).** `Dictionary_removed.json` holds the 140 deleted entries, among them `name`, `person`, `door`, `dude`, `data`, `date`, `hand`, `finger`, `enter`, `betwen`, `taskz` and the `-k` verb forms. A removed word has no Schalowitsk form until it is coined under Module 16A (Route B respelling, COIN-5). `key` and `task` stay guide-only words only until you replace them.
- **Confirmations of grammar rules:** the digits 1-9 exist and ten / twenty / thirty are deliberately empty (numbers are generated, Module 15); `mi` is listed as the dative / experiencer form (EXP-2); `Et` is the abstract "it" and `Daz` the physical "there" (REF-1, REF-4); `fast` = "almost" (the idiom `Doun fast apel`); `went` = `shoun gehk` and `drank` = `shoun trink` (TNS-9); `derzhe` -> `derzheni` follows the plural rule; `-mann` words (`spilemann`, `oyemann`) attach whole.
- **Homographs:** `er` = "he" and "ear"; `sein` = "six"; `morgen` = "tomorrow" and "morning"; `briv` = "bro" (casual brother / friend); `liebe` = "love" (verb and noun).
- **People words:** `penk` = "people" (the collective, and `Seckeh penk` = who); `drhn` = friend. The entry `person` was removed in 9.5 (straight English); one person is coined under Module 16A.
- **Copula:** the dictionary lists `am` = `doun` (separated 1SG, FIN-7) and `are` = `dorn`.
- **Inflected entries.** Several generated entries carry an inflected English form in the `english` field (`has` = `habe`, `trolling`, `rules`, `sells`...). They are defects (LEM-6). Use the lemma's entry. `Dictionary_review.txt` lists them.
- **Casual markers:** `bofik` (wanna), `briv`, `rofl`, `brach`, `oye`, `sup` are tagged casual or slang and select the informal register (DIC-5, REG-4).

---

## MODULE 20 - ENGLISH -> SCHALOWITSK TRIGGER MAP (ANTI-LEAK)

Scan the English for these structures **before** writing anything. Each row is a place where English grammar tries to leak into the output.

| English structure | Never output | Output instead | Rule |
| :--- | :--- | :--- | :--- |
| "must / have to / need to + verb" | `haben tu`, `muss tu` | modal frame `S muss ... V-en` | MOD-1..5 |
| "can / want to + verb" | `kahn tu`, `wolt tu` | `S kahn ... V-en` / `S wolt ... V-en` | MOD-3 |
| "going to + **verb**" | `gehk tu`, `Yem doun geht` | future core: `Yeht`, `Su geht`... | FIN-2, TNS-2 |
| "going to + **place**" | `Yeht ...` | `gehk` + `tu'den` + place | TNS-4 |
| "will / shall / 'll" | `will`, `wil` | `geht` / `Yeht` / `Yahlt` / `Dehyt` | TNS-2 |
| "-ing" (am playing, was eating) | `spileing`, `doun spile-ing` | plain verb: `Yem spile`, `Ya shoun iz` | TNS-3 |
| "-s / -ed" on a verb | `spiles`, `spiled` | dictionary form | FIN-6 |
| "-ly" (quickly) | `kvikly` | `kvik` after the verb | ADJ-1 |
| "'s" (king's) | `konig's` | `deny aufsita av den konig` / `den konig av-aufsita` | POS-1 |
| "my / your / his / her / our / their" | `mi briv`, `my briv` | `briv av'mi`, `briv av'er`... | POS-2 |
| "of" | `of` | `av` | POS-3 |
| "do / does / did" as negation or question helper | `doun nucht`, `doun Ya spile?` (as do-support) | negation algorithm; plain Yes/No order | NEG-1, QST-1 |
| "don't / doesn't / didn't + verb (+ object)" | `Yem don't spile` | `Yem spilenu Roblox.` / `Yem spile nucht.` | NEG-2/3 |
| "never" | `nie`, `never` | `alsitnu` (and no `-nu`) | NEG-4 |
| "nothing / no one" | `nu iz` | `nikscht` / `nimkto` | NEG-4 |
| "to the / in the / at the" | `tu den`, `en den`, `zu den` | `tu'den` / `tu'deny`, `en'den` / `en'deny`, `zu'den` / `zu'deny` (by gender) | PRP-2, GEN-6 |
| "it" (weather, time, idea) | `Es` | `Et` | REF-1 |
| "it" (physical thing) | `Et` | `Es` | REF-2 |
| "there is / are" | `Daz doun` | `Dah doun` / `Dah dorn` | REF-3 |
| "there" (place) | `Dah` | `Daz` | REF-4 |
| "how" | `Seckeh`, fronted `Schalowit` | terminal `Schalowit` | QST-4 |
| "what / who / when / why / where" | any English WH-word | `Seckeh` (+ `zeit` / `penk` / `prichin` / `plas`) at Index 0, then `chel` / `kel` | QST-2, HLP-2 |
| any informal question | no helper | `kez` / `kel` / `kaz` / `kom` | HLP-1 |
| tag ("isn't it?", "right?", "okay?") | plain Yes/No or `nu?` | `[Clause], chom?` / `kom?` | QST-9 |
| "how many / how much" | `[UNKNOWN:how many]` | `Seckeh viel [plural noun]` / `Seckeh melok [noun]` | QST-7 |
| "how old / far / long / fast / often" | `Seckeh [adj]` or `[UNKNOWN]` | `Seckeh grad [adj]` | QST-7 |
| "which one" / "whose [noun]" | `[UNKNOWN]` | `Seckeh wehl` / `Seckeh penk av-[noun]` | QST-12 |
| "whether / if" (embedded) | `wehn` | `obe` | QST-10 |
| "Today / Tomorrow, I ..." (fronted) | `Heute Yem ...`, `Heute Ya ...` | `Heute doun Ya ...` | V2-1 |
| "If / when / because ... " clause | helper in the middle | helper last | SUB-1 |
| "..., then ..." after a fronted "if" | `, Yem gehk` with no connector | `, dashe Yem gehk` | SUB-6 |
| an imperative aimed at a person | `Stevad es!` | `Stevad Ben es!` | IMP-2 |
| an imperative with no addressee | `Stevad Ben es!` | `Stevad es!` | IMP-3 |
| "please" | `please` | `Plis` start (formal) / end (casual) | PLS-2 |
| "a / an" | `a`, `an` | `ein` / `eine` (by gender) | NP-2, GEN-4 |
| "the" | `the` | `den` / `deny` (by gender) | NP-2, GEN-4 |
| plural "-s" | `apels` | `apeleni` | PLU-1 |
| number words ("twenty-nine") | `twenty-nine`, `29` | `doiwikn Nein` | NUM-1..3, NUM-8 |
| phrasal / particle verbs ("set off", "finish drinking", "redo") | `gehk an`, `trink aus` | `angehk`, `austrink`, `wiedermek` | MOR-5, MOR-6 |
| "than" | `than`, `-er` | `als` + comparative `-n` | CMP-1..3 |
| names, brands, games | translated or inflected forms | verbatim | NAM-1, NAM-4 |
| a missing content word (finish, feel, fun, window...) | the English word | a word coined by Module 16A | COIN-1 to COIN-9 |
| a missing function word (for, on, after, without...) | the English word | the PRP-1 safe equivalence, else `[UNKNOWN:word]` | PRP-1, LEX-4 |
| English contractions | `I'm`, `don't` | expand first (Step 0), then translate | OUT-3 |
| reflexives ("myself", "himself", "themselves") | `mi selb`, `er selb`, `sebm`, `reflektk`, a plain object pronoun | `yaselb`, `erselb`, `dehyeselb`, `sheselb` | RFL-1..5 |
| any inflected English word ("-ing", "-ed", "-s", "has", "does") | a new coined word (`habe`, a `trosh`-type entry) | the lemma's entry (`haben`, the `troll` root) | LEM-1, LEM-2 |
| "you are", "you do" | `Su dorn`, `Ben dorn` | `Su doun`, `Ben doun` | FIN-5a |
| "like / love / enjoy + verb" | `Yem muss spilen` | `Yem lyuba spilen` | MOD-16 |
| "that has" / "which has" | `dehyss doun ein ...` | `Seckeh ... haben doun` | REL-4 |
| acronym (AI, UI) | `ui`, a coined word | `UI`, `AI` verbatim | NAM-7 |
| non-English input (German `Sie`) | a copied or fused German word | the meaning, with `Su` | OUT-7 |
| subject WH ("who is doing", "what is going on") | a WH helper with no core | `Seckeh penk chel doun ...` | QST-14 |
| "do" as the main verb | `mek` | `tyern` | FIN-12 |

---

## MODULE 21 - ANTI-PATTERN LIBRARY (WRONG -> RIGHT)

Each row is an error an AI has actually made, or is likely to make.

| # | ✘ Wrong | ✔ Right | Rule |
| :--- | :--- | :--- | :--- |
| 1 | `Ya yem spile Roblox.` | `Yem spile Roblox.` | FIN-1 |
| 2 | `Ya yeht mek eine spilezung.` | `Yeht mek eine spilezung.` | FIN-1 |
| 3 | `Yem doun spile Roblox.` | `Yem spile Roblox.` | FIN-1 |
| 4 | `Er spile Roblox.` (no helper) | `Er doun spile Roblox.` | FIN-1, FIN-3 |
| 5 | `Yem spileing Roblox.` | `Yem spile Roblox.` | TNS-3 |
| 6 | `Yem gehk tu mek eine spilezung.` | `Yeht mek eine spilezung.` | FIN-2 |
| 7 | `Yem gehk tu'den mek ein smonav.` (English-style "going to" **and** an invented noun) | `Yeht mek eine spilezung.` | FIN-2, LEX-2 |
| 8 | `Heute Yem spile Roblox.` | `Heute doun Ya spile Roblox.` | V2-1 |
| 9 | `Heute doun Yem spilenu Roblox.` | `Heute doun Ya spilenu Roblox.` | V2-5 |
| 10 | `Heute Ya doun spile Roblox.` | `Heute doun Ya spile Roblox.` | V2-1 |
| 11 | `Wehn Su doun gehk, dashe Yem gehk.` | `Wehn Su gehk doun, dashe Yem gehk.` | SUB-1 |
| 12 | `Wehn Yem gehk doun, ...` | `Wehn Ya gehk doun, ...` | FIN-4 |
| 13 | `Wehn Su gehk doun, Yem gehk.` | `Wehn Su gehk doun, dashe Yem gehk.` | SUB-6 |
| 14 | `Wehn Su gehk tu'deny aufsita doun.` | `Wehn Su tu'deny aufsita gehk doun.` | SUB-3 |
| 15 | `Yem muss spilen mit briv av'mi.` | `Yem muss mit briv av'mi spilen.` | MOD-2 |
| 16 | `Yem muss mit briv av'mi spilen eine spilezung.` | `Yem muss eine spilezung mit briv av'mi spilen.` | MOD-2 |
| 17 | `Yem muss eine spilezung mit briv av'mi spile.` | `... spilen.` | MOD-3, MOD-6 |
| 18 | `Yem haben tu gehk!` | `Yem muss verlassen!` | MOD-5, MOD-14 |
| 19 | `Yem muss tu spilen.` | `Yem muss spilen.` | MOD-5 |
| 20 | `Yem doun muss spilen.` | `Yem muss spilen.` | MOD-4 |
| 21 | `Yem spile nucht Roblox.` | `Yem spilenu Roblox.` | NEG-2 |
| 22 | `Yem spilenu.` (no object) | `Yem spile nucht.` | NEG-3 |
| 23 | `Ya alsitnu iznu apeleni.` | `Ya alsitnu iz apeleni.` | NEG-4 |
| 24 | `Yem nu spile Roblox.` | `Yem spilenu Roblox.` | NEG-6 |
| 25 | `Yem nucht spile.` | `Yem spile nucht.` | NEG-1 |
| 26 | `Schalowit Ben doun?` | `Kaz Ben doun Schalowit?` | QST-4 |
| 27 | `Seckeh Ben doun?` meaning "How are you?" | `Kaz Ben doun Schalowit?` | QST-4 |
| 28 | `Kaz Ben doun Schalowit daz?` | `Kaz Ben doun daz Schalowit?` | QST-4 |
| 29 | `Seckeh penk Su doun bist?` (no helper) | `Seckeh penk chel Su doun bist?` | HLP-1, ROL-7 |
| 30 | `Seckeh penk chel Ben doun bist?` (formal helper with `Ben`) | `Seckeh penk kel Ben doun bist?` | HLP-6, ROL-7 |
| 31 | `Seckeh doun Ben spile?` (V2 applied to a WH-question) | `Seckeh kel Ben doun spile?` | QST-3 |
| 32 | `Stevad Ben et!` (physical object) | `Stevad Ben es!` | REF-2 |
| 33 | `Stevad es!` (said to a specific person) | `Stevad Ben es!` | IMP-2 |
| 34 | `Stevad Ben es!` (broad announcement) | `Stevad es!` | IMP-3 |
| 35 | `Ben stevad es!` | `Stevad Ben es!` | IMP-2 |
| 36 | `Gehken daz!` | `Gehk daz!` | IMP-1 |
| 37 | `konig's aufsita` | `deny aufsita av den konig` | POS-1 |
| 38 | `mi briv` / `briv's mi` | `briv av'mi` | POS-2 |
| 39 | `tu deny aufsita` | `tu'deny aufsita` | PRP-2 |
| 40 | `mit'den key` | `mit deny key` | PRP-2 |
| 41 | `Es doun regen.` | `Et doun regen.` | REF-1 |
| 42 | `Daz doun ein konig.` / `Gehk dah!` | `Dah doun ein konig.` / `Gehk daz!` | REF-3, REF-4 |
| 43 | `spilzung` (rule-derived) / `Spilezung` (capitalized mid-sentence) | `spilezung` | MOR-1, ORT-4 |
| 44 | `apels`, `hzes`, `spilezungeni` | `apeleni`, `hzeni`, `spilezeng` | PLU-1, PLU-2 |
| 45 | `jad'zeeni` | `jad'zeni` | PLU-3 |
| 46 | `doiwik n Nein`, `doiwikn nein` | `doiwikn Nein` | NUM-3, NUM-8 |
| 47 | `doiwiknjein`, `doiwiknnein` | `doiwikn Nein` | NUM-3, NUM-8 |
| 48 | `twenty-nine penkeni` | `doiwikn Nein penkeni` | NUM-7, OUT-3 |
| 49 | `Yem gehk an.` / `Yem gehk ... an` | `Yem angehk.` | MOR-6 |
| 50 | `xneksn` | `xnekstn` | CMP-1 |
| 51 | `Robloxeni`, `Roblocs` | `Roblox` | NAM-1, NAM-4 |
| 52 | `Yem ruhn kvikly.` | `Yem ruhn kvik.` | ADJ-1 |
| 53 | `Roblox doun Ya xnekst.` | `Roblox doun mi xnekst.` | EXP-2 |
| 54 | `Sure! Here is the translation: Yem spile Roblox.` | `Yem spile Roblox.` | OUT-1 |
| 55 | `Yem [English word] eine key.` | `Yem [word coined by Module 16A] eine key.` (`[UNKNOWN:word]` only if coining fails) | COIN-1, LEX-4 |
| 56 | `Yem kann Roblox spilen.` / `Yem wolle Roblox spilen.` | `Yem kahn Roblox spilen.` / `Yem wolt Roblox spilen.` | MOD-3 |
| 57 | `... darum ...` / `... pahr ...` | `... wahn ...` / `... darab ...` | SUB-2, PRP-1 |
| 58 | `kastelv`, `klikat`, `run`, `ruks`, `alvse`, `irgenkto`, `start` | `aufsita`, `kluk`, `ruhn`, `rukz`, `alscht`, `irgkto`, `begin` | DIC-1, Module 19.2 |
| 59 | `Yem [UNKNOWN:have] eine key.` (the dictionary has the word) | `Yem haben eine key.` | DIC-1 |
| 60 | `Yem zhumem deny spilezung.` / a guessed word for an empty entry that skipped the COIN-6 checks | a word that passed COIN-1 to COIN-8, else `Yem [UNKNOWN:finish] deny spilezung.` | DIC-2, COIN-6 |
| 61 | `briv av'sein` ("your brother") | `briv av'ben` (informal) / `briv av'su` (formal); `sein` is the numeral six | POS-2 |
| 62 | `Yem muss den konig sehenen.` (extra `-en` on a root that already ends in `-en`) | `Yem muss den konig sehen.` | MOR-3 |
| 63 | `den aufsita`, `den key`, `ein key`, `ein spilezung` | `deny aufsita`, `deny key`, `eine key`, `eine spilezung` | GEN-4 |
| 64 | `eine konig`, `deny spilemann`, `deny wasser` | `ein konig`, `den spilemann`, `den wasser` | GEN-3, GEN-4 |
| 65 | `deny konigeni`, `den aufsitaeni` | `den konigeni`, `deny aufsitaeni` | GEN-5 |
| 66 | `tu'den aufsita`, `tu deny aufsita` | `tu'deny aufsita` | PRP-2, GEN-6 |
| 67 | `denya aufsita`, `den-y aufsita` | `deny aufsita` | GEN-1 |
| 68 | `Ben doun spile Roblox?` (informal, no helper) | `Kez Ben doun spile Roblox?` | HLP-1 |
| 69 | `Chez Ben doun spile Roblox?` | `Kez Ben doun spile Roblox?` | HLP-6 |
| 70 | `Kez Su doun spile Roblox?` | `Chez Su doun spile Roblox?` | HLP-6 |
| 71 | `Chez Su doun Schalowit?` (old how-helper) | `Chaz Su doun Schalowit?` | HLP-2 |
| 72 | `Seckeh penk chez Su doun bist?` (old WH-helper) | `Seckeh penk chel Su doun bist?` | HLP-2, ROL-7 |
| 73 | `Chez Kez Ben doun spile?` (two helpers) | `Kez Ben doun spile?` | HLP-3 |
| 74 | `Ben doun spile Roblox kom?` (no comma) | `Ben doun spile Roblox, kom?` | QST-9 |
| 75 | `Ben doun spile Roblox, doun nucht Ben?` (English tag) | `Ben doun spile Roblox, kom?` | QST-9 |
| 76 | `Kez Ben doun spile Roblox, kom?` (Yes/No helper plus tag) | `Ben doun spile Roblox, kom?` | HLP-3 |
| 77 | `Yem sehen Seckeh kel Ben spile doun.` (helper in an embedded clause) | `Yem sehen Seckeh Ben spile doun.` | HLP-4, QST-10 |
| 78 | `Seckeh viel spilezung kel Ben doun spile?` | `Seckeh viel spilezungeni kel Ben doun spile?` | QST-7 |
| 79 | `Seckeh kvik kel Ben doun ruhn?` (for "how fast") | `Seckeh grad kvik kel Ben doun ruhn?` | QST-7 |
| 80 | `Yem sehen wehn Su spile doun.` (for "whether") | `Yem sehen obe Su spile doun.` | QST-10 |
| 81 | `Su dorn Schalowit?` | `Chaz Su doun Schalowit?` | L27, FIN-5a, HLP-1 |
| 82 | `Ben dorn tyern` / `Su dorn tyern dehyss` | `Ben doun tyern dehyss` / `Su doun tyern dehyss` | FIN-5a |
| 83 | `Seckeh chel Ben dorn tyern?` (formal helper with `Ben`, plural helper) | `Seckeh kel Ben doun tyern?` (formal: `Seckeh chel Su doun tyern?`) | L29, HLP-6, FIN-5a |
| 84 | `Seckeh plas chez Su dorn tyern dehyss?` (Yes/No helper in a WH question) | `Seckeh plas chel Su doun tyern dehyss?` | HLP-2, L29 |
| 85 | `Kez Su doun iz izeug?` (informal helper with `Su`) | `Chez Su doun iz izeug?` | L29, HLP-6 |
| 86 | `Kez Su haben ein schreibklav?` (mixed helper, no core) | `Chez Su doun haben ein schreibklav?` | L29, FIN-1, G-103 |
| 87 | `Seckeh kel Ben doun den usernam?` for "What is your username?" ("your" lost, `Ben` made the subject) | `Seckeh chel usernam av'su doun?` | QST-15, POS-2, REG-1 |
| 88 | `Kaz Ben dorn dehyss tyern?` (no `Schalowit`, object before verb, `dorn`) | `Chaz Su doun tyern dehyss Schalowit?` (informal: `Kaz Ben doun tyern dehyss Schalowit?`) | QST-4, ISO-1, FIN-5a |
| 89 | `Su dorn dehyss tyern` (object before the verb) | `Su doun tyern dehyss` | ISO-1, SVO-1 |
| 90 | `Seckeh penk kel tyern dehyss?` (WH-subject with no core) | `Seckeh penk chel doun tyern dehyss?` | QST-14, FIN-1 |
| 91 | `Seckeh chel doun gehk an?` ("what is going on", word for word) | `Seckeh chel doun pass?` | LEX-6, MOR-6 |
| 92 | `Su dorn zirkusnu.` (`-nu` with no object, `dorn`) | `Su doun zirkus nucht.` | NEG-3, FIN-5a |
| 93 | `Yeht meknu es.` for "I am not going to do it" (`mek` = make) | `Yeht tyernnu es.` | FIN-12, NEG-2 |
| 94 | `Yem kahn size den text how Ya like et Schalowit?` (English words left, `?` for a `.`) | `Yem kahn den tekst merkaen Ya et lyuba doun Schalowit.` | OUT-2, OUT-3, QST-16 |
| 95 | `Dehyss ui doun xnekst!` (lower-case acronym) | `Dehyss UI doun xnekst!` | NAM-7 |
| 96 | `Schreiben Ben dehyss.` (German word, infinitive in a command, `Ben` with no cue) | `Schrei dehyss.` | IMP-1, IMP-4, L30, L31 |
| 97 | `Habensu?` for German "Haben Sie?" (invented fused word) | `Chez Su doun haben?` | OUT-7 |
| 98 | `Stevad Ben es jetzt.` (no addressee cue) | `Stevad es jetzt.` | IMP-4 |
| 99 | `Yem lyuba penk troshkeni.` (invented plural on a verb) | `Yem lyuba penk troshen.` | MOD-16, FIN-6 |
| 100 | `Yem muss spilen.` for "I like to play" (`muss` = must) | `Yem lyuba spilen.` | MOD-16, MOD-3 |
| 101 | `Vak ein.` for "Go for a walk" (stray `ein`) | `Vak.` | LEX-6, OUT-5 |
| 102 | `Den trahnslotzung kompletnu.` (wrong gender, added article, `-u` on an adjective, no core) | `Trahnslotzung doun kompletn.` | GEN-4, OUT-5, ADJ-5, SVO-4 |
| 103 | `Ben muss dehyss kompletn.` (adjective used as the verb) | `Su muss dehyss kompletn meken.` | ADJ-5, LEX-3, REG-1 |
| 104 | `Er doun nucht hilfen mi.` (`hilfen` is not a word; `nucht` before an object) | `Er doun hilfenu mi.` | FIN-6, NEG-2 |
| 105 | `She doun verruckt gehk.` (German spelling kept, "going" translated literally) | `She doun tudoun verrukt.` | COIN-5, LEX-6 |
| 106 | `Dehye dorn tu'den duvad gehken.` (infinitive in a finite clause) | `Dehye dorn gehk tu'den duvad.` | L30, TNS-4 |
| 107 | `AI yeht verstehennu dehyss.` (`Yeht` = "I will") | `AI geht verstehennu dehyss.` | FIN-11, NAM-7 |
| 108 | `Dojtska doun ein stark europana nation.` (continent word as adjective, English `nation`) | `Dojtska doun eine stark europanisk derzhe.` | NAM-8, COIN-1, GEN-4 |
| 109 | `Deny United States doun ein vrolev kraft derzheni, dehyss doun ein schpize xnekst kriegsvalt.` (name untranslated, added `Deny`, plural nation, "that has" became "this is") | `Ferjed Derzheni doun eine vrolev kraft derzhe, Seckeh ein schpize xnekst kriegsvalt haben doun.` | NAM-8, REL-4, LEM-5, GEN-4 |
| 110 | a new word `habe` coined for "has" | `haben` (the entry for "have") | L28, LEM-2, LEM-5 |
| 111 | a new entry or word for "trolling", "chatting", "sizes" or any other inflected form | the lemma's entry (`troll`, `chat`, `size`) | L28, LEM-1, LEM-2 |
| 112 | `Dehyss doun ein bervin.` (verb root used as a noun) | `Dehyss doun eine bervinzung.` | MOR-1, GEN-4 |

---

## MODULE 22 - GOLD TRANSLATION SUITE (REGRESSION TESTS)

Use these as ground truth. `[D]` = derived by strict analogy (no source gave the exact sentence); untagged = attested in a source file (spelling normalized per Module 25).

### 22.1 Plain main clauses and tense
| ID | English | Schalowitsk | Rules |
| :--- | :--- | :--- | :--- |
| G-001 | I play Roblox today. | `Yem spile Roblox heute.` | FIN-3, SVO-2 |
| G-002 | I played Roblox. [D] | `Ya shoun spile Roblox.` | Table A |
| G-003 | I will play Roblox. [D] | `Yeht spile Roblox.` | FIN-2 |
| G-004 | You play Roblox. (informal) [D] | `Ben doun spile Roblox.` | Table A, REG-2 |
| G-005 | You play Roblox. (formal) [D] | `Su doun spile Roblox.` | Table A |
| G-006 | We play Roblox. [D] | `Yalm spile Roblox.` | Table A |
| G-007 | They eat apples. [D] | `Dehye dorn iz apeleni.` | Table A, PLU-1 |
| G-008 | I run quickly. | `Yem ruhn kvik.` | ADJ-1 |
| G-009 | I will make a game. | `Yeht mek eine spilezung.` | FIN-2, MOR-1 |
| G-010 | I'm going to make a game. | `Yeht mek eine spilezung.` | TNS-2 |
| G-011 | I'm going to the castle. [D] | `Yem gehk tu'deny aufsita.` | TNS-4, PRP-2 |
| G-012 | He remade the task. | `Er shoun wiedermek den task.` | MOR-5 |
| G-013 | You will finish drinking the water. | `Su geht austrink den wasser.` | MOR-5 |
| G-014 | I set off. | `Yem angehk.` | MOR-5 |
| G-015 | I need a key to the home. | `Yem brauch eine key tu'den heim.` | MOD-12, PRP-2 |
| G-016 | I need a teammate. | `Yem brauch ein samspilemann.` | MOR-7 |
| G-017 | I play every game. | `Yem spile vsespilezung.` | MOR-7 |
| G-018 | The high king built the castle. | `Den urzkonig shoun bau deny aufsita.` | FIN-8 |

### 22.2 V2 fronting
| ID | English | Schalowitsk | Rules |
| :--- | :--- | :--- | :--- |
| G-019 | Today I play Roblox. | `Heute doun Ya spile Roblox.` | V2-1 |
| G-020 | Today I do not play Roblox. | `Heute doun Ya spilenu Roblox.` | V2-5, NEG-2 |
| G-021 | Tomorrow I will make a game. [D] | `Morgen geht Ya mek eine spilezung.` | Table B |
| G-022 | In the castle I play Roblox. [D] | `En'deny aufsita doun Ya spile Roblox.` | V2-2 |
| G-023 | Today we play Roblox. [D] | `Heute dorn Yal spile Roblox.` | Table B |
| G-024 | Today I need a key. [D] | `Heute doun Ya brauch eine key.` | V2-1 |

### 22.3 Subordinate and relative clauses
| ID | English | Schalowitsk | Rules |
| :--- | :--- | :--- | :--- |
| G-025 | If you go, then I go. | `Wehn Su gehk doun, dashe Yem gehk.` | SUB-1, SUB-6 |
| G-026 | ... when you go to the castle. | `... wehn Su tu'deny aufsita gehk doun.` | SUB-3 |
| G-027 | I go if you go. [D] | `Yem gehk wehn Su gehk doun.` | SUB-6 |
| G-028 | If you go to the castle, I will make a game. [D] | `Wehn Su tu'deny aufsita gehk doun, dashe Yeht mek eine spilezung.` | SUB-3, SUB-6 |
| G-029 | If I play Roblox, you go. [D] | `Wehn Ya Roblox spile doun, dashe Su doun gehk.` | FIN-4 |
| G-030 | ... a king who rules twenty-nine people. | `... ein konig Seckeh penk doiwikn Nein penkeni rukz doun.` | REL-1, REL-2, NUM-7 |

### 22.4 Modal frames
| ID | English | Schalowitsk | Rules |
| :--- | :--- | :--- | :--- |
| G-031 | I have to go! | `Yem muss verlassen!` | MOD-14 |
| G-032 | I have to play with my brother. | `Yem muss mit briv av'mi spilen.` | MOD-2 |
| G-033 | I have to play a game with my brother. | `Yem muss eine spilezung mit briv av'mi spilen.` | MOD-2 |
| G-034 | Today I have to play a game with my brother. [D] | `Heute muss Ya eine spilezung mit briv av'mi spilen.` | MOD-7 |
| G-035 | You can play Roblox. [D] | `Ben kahn Roblox spilen.` | MOD-3 |
| G-036 | Can you play Roblox? (formal) [D] | `Chez Su kahn Roblox spilen?` | MOD-9 |
| G-037 | I want to build the castle. [D] | `Yem wolt deny aufsita bauen.` | MOD-6 |
| G-038 | You have to finish drinking the water. [D] | `Su muss den wasser austrinken.` | MOR-6 |

### 22.5 Negation
| ID | English | Schalowitsk | Rules |
| :--- | :--- | :--- | :--- |
| G-039 | I am not playing. | `Yem spile nucht.` | NEG-3 |
| G-040 | I am not playing Roblox. | `Yem spilenu Roblox.` | NEG-2 |
| G-041 | I never eat apples. | `Ya alsitnu iz apeleni.` | NEG-4, FIN-9 |
| G-042 | I am not playing with my brother. [D] | `Yem spile nucht mit briv av'mi.` | NEG-3 |
| G-043 | No one plays Roblox. [D] | `Nimkto doun spile Roblox.` | NEG-4 |
| G-044 | I will not make a game. [D] | `Yeht meknu eine spilezung.` | NEG-8 |
| G-045 | Tomorrow you will not finish drinking the water. [D] | `Morgen geht Su austrinknu den wasser.` | V2, NEG-2, MOR-6 |

### 22.6 Imperatives
| ID | English | Schalowitsk | Rules |
| :--- | :--- | :--- | :--- |
| G-046 | Find it! (to a specific person; physical object) | `Stevad Ben es!` | IMP-2, REF-2 |
| G-047 | Find it! (general announcement) | `Stevad es!` | IMP-3 |
| G-048 | Find the key! (to a specific peer) | `Stevad Ben deny key!` | IMP-2 |
| G-049 | Find the key! (general) | `Stevad deny key!` | IMP-3 |
| G-050 | Go there! (to a specific person) | `Gehk Ben daz!` | IMP-2, REF-4 |
| G-051 | Go there! (general) | `Gehk daz!` | IMP-3 |
| G-052 | Click this! | `Kluk dehyss!` | IMP-3 |
| G-053 | Please find the key. (formal, to a person) [D] | `Plis stevad Su den schluessel!` | PLS-2, IMP-5 |
| G-054 | Find the key, please. (casual, to a peer) [D] | `Stevad Ben deny key plis!` | PLS-2 |
| G-055 | Don't go! [D] | `Gehk nucht!` | NEG-7 |

### 22.7 Questions
| ID | English | Schalowitsk | Rules |
| :--- | :--- | :--- | :--- |
| G-056 | How are you? (informal) | `Kaz Ben doun Schalowit?` | QST-4, HLP-2 |
| G-057 | How are you? (formal) | `Chaz Su doun Schalowit?` | QST-4, HLP-2 |
| G-058 | How are you doing there? (informal) | `Kaz Ben doun daz Schalowit?` | QST-4, HLP-2 |
| G-059 | Who are you? (formal) | `Seckeh penk chel Su doun bist?` | QST-2, HLP-2, ROL-7 |
| G-060 | Who are you? (informal) | `Seckeh penk kel Ben doun bist?` | QST-2, HLP-2, ROL-7 |
| G-061 | What are we doing? (formal default) | `Seckeh chel Yalm?` | QST-3, HLP-2 |
| G-062 | Where are you going? (informal) [D] | `Seckeh plas kel Ben doun gehk?` | QST-2, HLP-2 |
| G-063 | When do you play? (informal) [D] | `Seckeh zeit kel Ben doun spile?` | QST-2, HLP-2 |
| G-064 | What game are you playing? (informal) [D] | `Seckeh spilezung kel Ben doun spile?` | QST-2, HLP-2 |
| G-065 | Do you play Roblox? (informal) [D] | `Kez Ben doun spile Roblox?` | QST-1, HLP-2 |
| G-066 | Do you play Roblox? (formal) [D] | `Chez Su doun spile Roblox?` | QST-1 |
| G-Q01 | You play Roblox, don't you? (informal) [D] | `Ben doun spile Roblox, kom?` | QST-9 |
| G-Q02 | You play Roblox, don't you? (formal) [D] | `Su doun spile Roblox, chom?` | QST-9 |
| G-Q03 | You don't play Roblox, do you? (informal) [D] | `Ben doun spilenu Roblox, kom?` | QST-9, NEG |
| G-Q04 | How many games do you play? (informal) [D] | `Seckeh viel spilezungeni kel Ben doun spile?` | QST-7 |
| G-Q05 | How much food do you have? (formal) [D] | `Seckeh melok izeug chel Su doun haben?` | QST-7 |
| G-Q06 | How fast do you run? (informal) [D] | `Seckeh grad kvik kel Ben doun ruhn?` | QST-7 |
| G-Q07 | How often do you play? (informal) [D] | `Seckeh grad ofte kel Ben doun spile?` | QST-7 |
| G-Q08 | Whose castle do you see? (formal) [D] | `Seckeh penk av-aufsita chel Su doun sehen?` | QST-12 |
| G-Q09 | Which of the games do you play? (informal) [D] | `Seckeh wehl av deny spilezungeni kel Ben doun spile?` | QST-12 |
| G-Q10 | What can you play? (informal) [D] | `Seckeh kel Ben kahn spilen?` | MOD-9 |
| G-Q11 | Can you play Roblox? (informal) [D] | `Kez Ben kahn Roblox spilen?` | MOD-9 |
| G-Q12 | I see what you play. [D] | `Yem sehen Seckeh Ben spile doun.` | QST-10 |
| G-Q13 | I see whether you play Roblox. [D] | `Yem sehen obe Su Roblox spile doun.` | QST-10 |
| G-Q14 | Do you see what I play? (informal) [D] | `Kez Ben doun sehen Seckeh Ya spile doun?` | QST-10, HLP-4 |

### 22.8 Referents, noun phrases, adjectives
| ID | English | Schalowitsk | Rules |
| :--- | :--- | :--- | :--- |
| G-067 | It is raining. | `Et doun regen.` | REF-1 |
| G-068 | This is it. | `Dehyss doun es.` | REF-2 |
| G-069 | There is a king. | `Dah doun ein konig.` | REF-3 |
| G-070 | There is unrest. | `Dah doun unruhig.` | REF-3 |
| G-071 | The king's castle. | `deny aufsita av den konig` (also valid: `den konig av-aufsita`) | POS-3 |
| G-072 | My brother. | `briv av'mi` (also valid: `av'mi briv`) | POS-2 |
| G-073 | A blue house. | `eine blau hze` | NP-1 |
| G-074 | Blue houses. | `blau hzeni` | PLU-1 |
| G-075 | Three games. [D] | `Dry spilezeng` | NUM-7 |
| G-076 | Roblox is great to me. [D] | `Roblox doun mi xnekst.` | EXP-2 |
| G-077 | Roblox is great. [D] | `Roblox doun xnekst.` | EXP-3 |
| G-078 | Roblox is greater than Minecraft. [D] | `Roblox doun xnekstn als Minecraft.` | CMP-1, CMP-3 |
| G-079 | The head hurts. / Headache. | `Deny golowa doun bol.` | SPC-2 |
| G-080 | That's close enough. | `Doun fast apel.` | 18.4 |

### 22.9 Numbers and morphology
| ID | English | Schalowitsk |
| :--- | :--- | :--- |
| G-081 | 10 | `dezi` |
| G-082 | 11 | `dezin Ein` |
| G-083 | 19 | `dezin Nein` |
| G-084 | 21 | `doiwikn Ein` |
| G-085 | 29 | `doiwikn Nein` |
| G-086 | 90 | `neinik` |
| G-087 | 99 | `neinikn Nein` |
| G-088 | game / games | `spilezung` / `spilezeng` |
| G-089 | player / players | `spilemann` / `spilemaneni` |
| G-090 | supermarket / supermarkets | `jad'ze` / `jad'zeni` |
| G-091 | house / houses | `hze` / `hzeni` |
| G-092 | apple / apples | `apel` / `apeleni` |

### 22.10 Dictionary-driven sentences, greetings and missing-word handling
| ID | English | Schalowitsk | Rules |
| :--- | :--- | :--- | :--- |
| G-093 | Hello! | `Halo!` | 5.3 |
| G-094 | Thank you. | `Grahdtuhd.` | 5.3 |
| G-095 | Hello, I play Roblox. [D] | `Halo, Yem spile Roblox.` | V2-3 |
| G-096 | I have a key. [D] | `Yem haben eine key.` | DIC-1 |
| G-097 | I know the king. [D] | `Yem kehn den konig.` | DIC-1 |
| G-098 | I went to the castle. [D] | `Ya shoun gehk tu'deny aufsita.` | TNS-9 |
| G-099 | I drank the water. [D] | `Ya shoun trink den wasser.` | TNS-9 |
| G-100 | Yesterday I played Roblox. [D] | `Gestern shoun Ya spile Roblox.` | V2-1 |
| G-101 | I want to play Roblox. [D] | `Yem wolt Roblox spilen.` | MOD-3 |
| G-102 | I have to see the king. [D] | `Yem muss den konig sehen.` | MOR-3 |
| G-103 | You have a key. [D] | `Su doun haben eine key.` | FIN-6 |
| G-104 | I live in Canada. [D] | `Yem einkombt av Kanada.` | NAM-2 |
| G-105 | I always play Roblox. [D] | `Ya alzeit spile Roblox.` | TNS-7 |
| G-106 | Hello, friend! (informal) [D] | `Halo, drhn!` | V2-3 |
| G-107 | Sorry! [D] | `Verzei!` | 18.5 |
| G-108 | The tasks. [D] | `den taskz` | PLU-7 |
| G-109 | 0 / 100 | `Zer` / `hundert` | NUM-6 |
| G-110 | I finish the game. [GAP: `finish` is an empty dictionary entry] | `Yem zhumem deny spilezung.` | DIC-2 |

### 22.11 Reflexive pronouns
| ID | English | Schalowitsk | Rule |
| :--- | :--- | :--- | :--- |
| G-111 | myself | `yaselb` | RFL-1 |
| G-112 | yourself (formal) | `suselb` | RFL-1 |
| G-113 | yourself (casual) | `benselb` | RFL-1 |
| G-114 | himself | `erselb` | RFL-1 |
| G-115 | herself | `sheselb` | RFL-1, RFL-5 |
| G-116 | ourselves | `yalselb` | RFL-1 |
| G-117 | themselves | `dehyeselb` | RFL-1, RFL-5 |

### 22.12 Log-derived regression tests (9.5)
Each English line below came from a real mistake in `translation_log.json`. Formal register is the default (REG-1); the informal variant swaps `Su` -> `Ben` and `ch-` -> `k-` helpers.
| ID | English | Schalowitsk | Rules |
| :--- | :--- | :--- | :--- |
| G-118 | What is going on? [D] | `Seckeh chel doun pass?` | QST-14 |
| G-119 | What is your username? [D] | `Seckeh chel usernam av'su doun?` | QST-15, POS-2 |
| G-120 | This UI is great! [D] | `Dehyss UI doun xnekst!` | NAM-7 |
| G-121 | This is a test. [D] | `Dehyss doun eine bervinzung.` | MOR-1 |
| G-122 | You are not chatting. [D] | `Su doun zirkus nucht.` | NEG-3, FIN-5a |
| G-123 | I am going to do it. [D] | `Yeht tyern es.` | FIN-12 |
| G-124 | I am not going to do it. [D] | `Yeht tyernnu es.` | FIN-12, NEG-2 |
| G-125 | What are you doing? [D] | `Seckeh chel Su doun tyern?` | QST-3, FIN-5a |
| G-126 | Why are you doing that? [D] | `Seckeh prichin chel Su doun tyern dehyss?` | QST-2, ISO-1 |
| G-127 | Where are you doing this at? [D] | `Seckeh plas chel Su doun tyern dehyss?` | QST-2, QST-13 |
| G-128 | How are you doing that? [D] | `Chaz Su doun tyern dehyss Schalowit?` | QST-4 |
| G-129 | Who's doing that? [D] | `Seckeh penk chel doun tyern dehyss?` | QST-14 |
| G-130 | Write this. [D] | `Schrei dehyss.` | IMP-1, IMP-4 |
| G-131 | Do you have a keyboard? [D] | `Chez Su doun haben ein schreibklav?` | LEM-5, G-103 |
| G-132 | Haben Sie? [D] | `Chez Su doun haben?` | OUT-7 |
| G-133 | Find it now. [D] | `Stevad es jetzt.` | IMP-4, REF-2b |
| G-134 | I like trolling people. [D] | `Yem lyuba penk troshen.` | MOD-16 |
| G-135 | I like to play. [D] | `Yem lyuba spilen.` | MOD-16 |
| G-136 | I like to play something. [D] | `Yem lyuba manscht spilen.` | MOD-16 |
| G-137 | Are you eating food? [D] | `Chez Su doun iz izeug?` | QST-1, TNS-3 |
| G-138 | Go for a walk. [D] | `Vak.` | LEX-3, IMP-3 |
| G-139 | Translation complete [D] | `Trahnslotzung doun kompletn.` | SVO-4, ADJ-5 |
| G-140 | You must complete this. [D] | `Su muss dehyss kompletn meken.` | ADJ-5, MOD-1 |
| G-141 | He is not helping me. [D] | `Er doun hilfenu mi.` | NEG-2 |
| G-142 | She is going insane. [D] | `She doun tudoun verrukt.` | LEX-3, COIN-5 |
| G-143 | They are going to the park. [D] | `Dehye dorn gehk tu'den duvad.` | TNS-4, L30 |
| G-144 | AI won't understand this. [D] | `AI geht verstehennu dehyss.` | FIN-11, NEG-2 |
| G-145 | Germany is a strong european nation. [D] | `Dojtska doun eine stark europanisk derzhe.` | NAM-8, GEN-4 |
| G-146 | He has a castle. [D] | `Er doun haben eine aufsita.` | LEM-5, FIN-1 |
| G-147 | I can size the text how I like it. [D] | `Yem kahn den tekst merkaen Ya et lyuba doun Schalowit.` | QST-16, MOD-2 |
| G-148 | United States is a world power nation, that has a really great military. [D] | `Ferjed Derzheni doun eine vrolev kraft derzhe, Seckeh ein schpize xnekst kriegsvalt haben doun.` | NAM-8, REL-4, LEM-5 |

---

## MODULE 23 - WORKED TRACES

### Trace A - V2 + modal + possession
**Input:** "Today I have to play a game with my brother."
| Step | Result |
| :--- | :--- |
| 0 Normalize | Today / I / have to / play / a game / with my brother. Names: none. |
| 1 Clauses | One main clause. Fronted time word "Today". Contains "have to + verb". |
| 2 Register | No "you". Not relevant. |
| 3 Lookup | today -> `Heute`; have to -> `muss`; play -> `spile`; a game -> `eine spilezung`; with -> `mit`; my brother -> `briv av'mi` |
| 4 Semantics | modal `muss` + verb -> frame MOD. Fronted time -> V2 as well. |
| 5 Morphology | `spile` -> infinitive `spilen` (MOR-3: ends in `e`, add `n`). `spilezung` from MOR-1. |
| 6 Frame | 7.9 combination "V2 + modal": `[Front] [Modal] [Ya] [O / PP] [V-en]` |
| 7 Insertions | none |
| 8 Audit | modal at Index 1; subject `Ya` standalone; infinitive last; no `tu`; no extra helper -> pass |
**Output:** `Heute muss Ya eine spilezung mit briv av'mi spilen.` [D]

### Trace B - fronted conditional + "going to" future
**Input:** "If you go to the castle, I'm going to make a game."
| Step | Result |
| :--- | :--- |
| 0 | Expand `I'm` -> "I am". "going to make" -> verb follows -> future. |
| 1 | Subordinate "If you go to the castle" (fronted) + main "I am going to make a game". |
| 2 | No register cue -> FORMAL -> `Su`. |
| 3-4 | if -> `wehn`; go -> `gehk`; to the castle -> `tu'deny aufsita`; will make -> future `Yeht`; game -> `spilezung`. |
| 6 | Subordinate (Table C, complements before the verb, helper last): `Wehn Su tu'deny aufsita gehk doun`. Main after `dashe`: Table A future `Yeht mek eine spilezung`. |
| 8 | helper last in subordinate; `Su` not fused; `dashe` present; `tu'den` fused; no `gehk tu` future -> pass |
**Output:** `Wehn Su tu'deny aufsita gehk doun, dashe Yeht mek eine spilezung.`

### Trace C - how-question
**Input:** "How are you doing there?" (to a gaming friend)
| Step | Result |
| :--- | :--- |
| 1 | Question containing "How". |
| 2 | Explicit informal cue -> `Ben` and the informal helper `kaz`. |
| 3-4 | "there" = a physical place -> `daz`; how -> `Schalowit`. |
| 6 | Helper first (`Kaz`), normal order `Ben doun daz`, then `Schalowit` last. |
| 8 | `Schalowit` is the last token; no `Seckeh` -> pass |
**Output:** `Kaz Ben doun daz Schalowit?`

### Trace D - negation with PP and time
**Input:** "I am not playing Roblox with my brother today."
| Step | Result |
| :--- | :--- |
| 1 | Plain SVO; time word at the end -> no V2 (V2-4). |
| 4 | Direct object `Roblox` exists -> transitive negation. The PP and `heute` are not objects. |
| 5-7 | `spile` + `nu` -> `spilenu`. |
**Output:** `Yem spilenu Roblox mit briv av'mi heute.`

### Trace E - targeted imperative with Es
**Input:** "Find it!" (shouted at a teammate; the thing is a hidden key)
| Step | Result |
| :--- | :--- |
| 1 | Command. Addressee is a specific person -> TARGETED. |
| 2 | Teammate/peer context -> informal -> `Ben`. |
| 4 | "it" = a tangible key -> `es`. |
| 6 | `[V] [Ben] [O]` |
**Output:** `Stevad Ben es!`

### Trace F - V2 + future + negation + prefix
**Input:** "Tomorrow you will not finish drinking the water."
| Step | Result |
| :--- | :--- |
| 1 | Fronted time word -> V2. Future. |
| 2 | Default formal -> `Su`. |
| 4 | Direct object `den wasser` -> `-nu`. "finish drinking" -> prefix `aus-` + `trink`. |
| 5 | `austrink` + `nu` -> `austrinknu`. |
| 6 | Table B future: `geht Su`. |
**Output:** `Morgen geht Su austrinknu den wasser.` [D]

---

## MODULE 24 - PRE-OUTPUT AUDIT (MANDATORY)

Run every line. If any check fails, repair and run the whole list again. Emit only when all pass.

### A. Finite core
| # | Check | Scan for | Rule |
| :--- | :--- | :--- | :--- |
| A1 | No stacked subject + fused form | `Ya yem`, `Ya yeht`, `Yal yalm`, `Yal yahlt`, `Dehye dehyt` | FIN-1 |
| A2 | Exactly one core per clause | `doun doun`, `Yem doun`, `Yeht geht`, `doun muss` | FIN-1 |
| A3 | Every finite clause has a core | a subject followed directly by a verb (`Er spile`) | FIN-1 |
| A4 | Fused forms only where legal | `Yem` / `Yeht` / `Yalm` / `Yahlt` / `Dehyt` right after a fronted element, or in a clause opened by `wehn` / `wahn` / `dass` / `whilst` / `Seckeh`, or after `alsitnu` | FIN-3, FIN-4 |
| A5 | Helper agrees with subject number | `dorn` with singular, `doun` with plural | FIN-5 |
| A6 | No `gehk` + `tu` future | `gehk tu`, `gehk tu'den` + verb | FIN-2 |
| A7 | No verb inflection or adverb suffix | `-s`, `-ed`, `-ing`, `-ly` on any Schalowitsk word | FIN-6, TNS-3, ADJ-1 |

### B. Clause frames
| # | Check | Rule |
| :--- | :--- | :--- |
| B1 | Fronted element at Index 0 -> helper at Index 1 -> subject at Index 2 | V2-1 |
| B2 | Nothing fronted that the English did not front; nothing un-fronted that it did | V2-4 |
| B3 | Subordinate / relative clause ends with its helper | SUB-1 |
| B4 | Complements stand between subject and verb inside subordinate clauses | SUB-3 |
| B5 | Fronted `wehn` clause is followed by `dashe`; `dashe` is not followed by V2 | SUB-6 |
| B6 | Modal sits directly after the subject token; all objects/PPs/adverbials come before the infinitive | MOD-1, MOD-2 |
| B7 | The `-en` verb is the last word before the final punctuation | MOD-2 |
| B8 | Infinitive formed correctly (`spilen`, `meken`, `gehken`, `austrinken`) | MOD-6 |
| B9 | No `tu` + verb anywhere | MOD-5, L8 |
| B10 | No separate helper beside a modal | MOD-4 |
| B11 | WH-question has no V2 inversion | QST-3 |

### C. Negation
| # | Check | Rule |
| :--- | :--- | :--- |
| C1 | Direct object present -> `V+nu`; absent -> `V nucht` | NEG-2, NEG-3 |
| C2 | `nucht` directly after the verb | NEG-3 |
| C3 | No `-nu` / `nucht` together with `alsitnu`, `nikscht`, `nimkto` | NEG-4 |
| C4 | No standalone `nu` inside a clause | NEG-6 |
| C5 | Core words never carry negation | NEG-1 |
| C6 | No `-nu` on an infinitive | MOD-10 |
| C7 | At most one negation per clause | NEG-4 |

### D. Questions, commands, register
| # | Check | Rule |
| :--- | :--- | :--- |
| D1 | `Seckeh` at Index 0 for WH; never used for "how" | QST-2, QST-4 |
| D2 | `Schalowit` appears once and is the last token before `?` | QST-4 |
| D3 | Every direct question has exactly one helper of the right type and slot; none in statements, commands or embedded clauses | HLP-1 to HLP-4 |
| D4 | Register consistent: `Su` + formal helper + `schluessel` / `Ben` + informal helper + `key` | REG-1, REG-2, HLP-6 |
| D8 | Tag helper is last, after a comma, with no other helper or `Seckeh` | QST-9 |
| D9 | `viel` has a plural noun, `melok` a singular noun; degree questions use `Seckeh grad [adj]` | QST-7 |
| D10 | Embedded question is verb-final with no helper and no `?` of its own | QST-10 |
| D5 | Imperative has no subject, no helper, no fused form, no infinitive | IMP-1 |
| D6 | Targeted command has `Ben`/`Su` directly after the verb; general command has none | IMP-2..4 |
| D7 | `Plis` only if "please" was in the English; start (formal) / end (casual) | PLS-1, PLS-2 |

### E. Noun phrase
| # | Check | Rule |
| :--- | :--- | :--- |
| E1 | No `'s`, no `s'` | POS-1 |
| E2 | Pronoun possession as `[noun] av'[pron]` with no article on the noun | POS-2 |
| E3 | `tu'den`/`tu'deny`, `en'den`/`en'deny`, `zu'den`/`zu'deny` fused; no other fusion; no unfused `tu den` / `tu deny` | PRP-2 |
| E3b | Every article matches its noun's gender (GEN-3 people, GEN-4 ending); plurals keep the singular's gender; `ein` / `eine` match too | GEN-1..6 |
| E4 | Only listed prepositions used | PRP-1 |
| E5 | `Et` / `Es` and `Dah` / `Daz` chosen by meaning | REF-1..4 |
| E6 | Plurals built by algorithm; plural noun after numbers above one | PLU-1..4 |
| E7 | Adjectives precede nouns; adverbs are base adjectives after the verb | NP-1, ADJ-1 |
| E8 | Comparative `-n`, superlative `-t`, `als` for "than" | CMP-1..3 |
| E9 | Predicate adjective: dative pronoun only if subject != experiencer | EXP-1..3 |
| E10 | Object = subject uses the one-word reflexive (`yaselb`...), never `sebm` / `reflektk` / an object pronoun | RFL-1..5 |

### F. Morphology
| # | Check | Rule |
| :--- | :--- | :--- |
| F1 | `-zung` drop rule applied to verb roots, but dictionary headwords win (`spilezung`, never `spilzung`) | MOR-1 |
| F2 | Verb prefixes glued to the verb everywhere | MOR-6 |
| F3 | Numbers generated, spaced `[Tens]n [Unit]`, unit capitalized | NUM-1..3, NUM-8 |
| F4 | Noun-prefixed words written as one lower-case word | MOR-7 |

### G. Vocabulary and output
| # | Check | Rule |
| :--- | :--- | :--- |
| G1 | Every content word has a non-empty `Dictionary.json` entry, a Module 19.1 guide-only form, a Module 16A coinage, or is `[UNKNOWN:word]` | LEX-1..5, DIC-2, COIN-1 |
| G2 | No English word remains (except verbatim names) | OUT-3 |
| G3 | Proper names verbatim; no morphology on names | NAM-1, NAM-4 |
| G4 | Capitalization per ORT-4 | ORT-4 |
| G5 | End punctuation preserved | OUT-2 |
| G6 | Only the translation is emitted (TRANSLATE mode) | OUT-1 |
| G7 | Hyphen appears only in `av-`; apostrophe only in `X'den`, `av'pron`, `jad'ze` | ORT-2, ORT-3 |
| G8 | Exactly one canonical translation per sentence | OUT-4 |
| G9 | No superseded guide form appears (`kastelv`, `kann`, `wolle`, `darum`, `pahr`, `run`, `klikat`, `ruks`, `alvse`, `irgenkto`, `vseNm`, `schtojem`, `vsedeng`, `etvasch`, `luboman`, `anyvasch`, `start`, `sein` as "your") | Module 19.2 |
| G10 | Every coined word passed COIN-6, is reused consistently, and no sentence has more than 2 coinages unless rephrasing failed | COIN-6, COIN-8 |

### H. Added in 9.5
| # | Check | Rule |
| :--- | :--- | :--- |
| H1 | `Su`, `Ben`, `Er`, `She`, names, `AI`, singular nouns carry `doun` / `shoun`; `dorn` / `shorn` only with plural subjects | L27, FIN-5a |
| H2 | Every English word was reduced to its dictionary form; no word exists for an inflection; `has` = `haben` | L28, LEM-1 to LEM-6 |
| H3 | Question helper family matches the pronoun (`Su` with `ch-`, `Ben` with `k-`); `chez` only in Yes/No | L29, HLP-6 |
| H4 | No `-en` infinitive outside a modal or `lyuba` frame; commands use the root | L30, MOD-16, IMP-1 |
| H5 | `Yem` `Yeht` `Yalm` `Yahlt` `Dehyt` appear only with their own pronoun | FIN-11 |
| H6 | No English or German word the dictionary lacks; acronyms in capitals | L31, NAM-7 |
| H7 | End punctuation equals the input's | OUT-2 |
| H8 | Every article has the right gender (`-ung` -> `deny` / `eine`); no article was added that the English lacked | GEN-4, OUT-5 |
| H9 | `-nu` only on a verb with a direct object; no adjective or noun ends in an accidental `-nu` | NEG-2, ADJ-5, COIN-6 |
| H10 | In finite clauses the object follows the verb | ISO-1 |
| H11 | "Like + verb" uses `lyuba` + `-en`, never `muss` | MOD-16 |
| H12 | Subject-WH questions keep `doun` after the helper | QST-14 |

---

## MODULE 25 - RESOLVED CONFLICTS LOG

These are the places where the five source files contradicted one another or themselves. The **wrong** form in each row is now **forbidden**.

| ID | Topic | What the sources said | Resolution (rule) |
| :--- | :--- | :--- | :--- |
| C-01 | Spelling of "game" | Guide, v5.0, v7.0 plural example: `spilzung` (rule-derived). v6.0, v7.0 note, v8.0 vocab and `Dictionary.json`: `spilezung`. | **`spilezung`** (lexicalized headword, MOR-1). The drop rule stays for other verbs (G-21). *This reverses the 9.0 edition, which had chosen `spilzung`.* |
| C-02 | Modal frame: object placement | v7.0/v6.0 example `Yem muss mit briv av'mi spilen` (no object). v8.0: all objects inside the frame, `Yem muss eine spilezung mit briv av'mi spilen`. | v8.0 (MOD-2). Both sentences remain valid (the first has no object). |
| C-03 | Subordinate clause: object position | v5.0/v7.0 template `S -> V -> O -> Helper`. v8.0 template `S -> Objects/PPs -> V -> Helper`, example `wehn Su tu'deny aufsita gehk doun`. | v8.0 (SUB-3). |
| C-04 | "Find it!" pronoun | v6.0/v7.0: `Stevad Ben et!`. v8.0: `Stevad Ben es!` | `es` for tangible referents (REF-2). |
| C-05 | Pronoun possession | Guide: "My: Mi". Later files: `av'mi`. v7.0: both `briv av'mi` and `av'mi briv` valid; v8.0 calls `av'mi briv` preferred but its own Gold example uses `briv av'mi`. | `[noun] av'[pron]` is the generated default; the other order is accepted (POS-2). Bare `mi briv` is not used. |
| C-06 | Pre-nominal noun possessor | v5.0 `Den konig av-aufsita`; dropped silently in v6.0-v8.0. | **Restored** as an accepted equivalent (POS-3). |
| C-07 | Plural of mash-ups | Rule text: "add `eni` to the absolute end" (gives `jad'zeeni`). Example: `jad'zeni`. | Apply the e/n-drop rule at the absolute end: `jad'zeni` (PLU-3). |
| C-08 | Mash-up rule vs its own example | Rule: keep word 1 whole, drop 2 leading letters of `hze`. Result stated: `Jad'ze` (word 1 loses `e`, word 2 loses only `h`). | Lexicalized `jad'ze` verbatim; algorithm not used for new words (MOR-4b/c). Open gap G-05. |
| C-09 | Number joiner | Old guides: `Einik n Ein` (detached `n`) and `Bieiniknjein` (fused, old digits). | `[Tens]n [Unit]`: `doiwikn Nein` (NUM-3, NUM-8). |
| C-10 | Comparative of `xnekst` | Guide: `xnekstn`. v7.0: `xneksn`. | `xnekstn` (CMP-1). |
| C-11 | "Today" | `Heut` (v5.0-v7.0), `Heute` (v8.0 canonical + `Heut`). | Same word; output `Heute` (V2-7). |
| C-12 | "Key" | v8.0: canonical `schluessel`, slang `key`; v5.0 uses `key` in a Gold sentence. | Formal `schluessel`, informal `key` (REG-2). |
| C-13 | English number in relative-clause example | v8.0: `... twenty-nine penkeni ...` | `doiwikn Nein penkeni` (NUM-7, OUT-3). |
| C-14 | Spelling of "rule" | v8.0 vocab `ruks`; v8.0 example `rukz`. | `rukz` (`Dictionary.json`: "rules" = `rukz`). |
| C-15 | "What are we doing?" | Guide: `Seckeh Yal dorn?` (also lists `Yalm` as present). | `Seckeh chel Yalm?` (QST-3, HLP-2; formal default). |
| C-16 | "I do it" | Guide: `Ya doun es.` (pre-fusion) | Superseded by fusion rules (FIN-7). Open gap G-09. |
| C-17 | Capitalization of derived nouns | v8.0 algorithm capitalizes (`Spilemann`); v5.0 and Gold sentences mix cases. | Lower-case mid-sentence (ORT-4). |
| C-18 | `verlassen` and the `-en` rule | v6.0: "Modal forces raw verb" and the Gold uses `verlassen`. | `verlassen` is the dictionary root; it already ends in `-en`, so it is its own infinitive (MOR-3). *9.0 wrongly treated it as `verlass` + `en`.* |
| C-19 | Corrupted text in v5.0 | Blank fields: tens examples (`10 = ` `` ``), `kvikly -> ` ``, `Yem  spile Roblox!`, `Roblox doun mi .` | Reconstructed from the rules (NUM-2, ADJ-1, EXP-2 with `xnekst`). |
| C-20 | Default register | Guide: `Su` default. Many examples use `Ben`. | Default formal; informal only on cues (REG-1). |
| C-21 | Command targeting default | v6.0 showed errors in both directions. | No addressee cue -> general (IMP-4). |
| C-22 | `n` joining digits vs clause "and" | `n` is both the conjunction and the number joiner. | Separate word between clauses/phrases (COO-1); spaced inside numerals (`doiwikn Nein`, NUM-3, NUM-8). |
| C-23 | Invented word in v6.0 error column | `smonav` (not a Schalowitsk word). | Game = `spilezung`; invented words forbidden (LEX-2). |
| C-24 | Infinitive of `-e` verbs | `spilen` attested; plain "add `-en`" would give `spileen`. | Add only `n` after `e` (MOR-3). |
| C-25 | Castle | Guide examples: `kastelv`. Dictionary: `aufsita`. | `aufsita` (DIC-1). |
| C-26 | Run / click | Guide: `run`, `klikat`. Dictionary: `ruhn`, `kluk`. | `ruhn`, `kluk`. |
| C-27 | Modals | Guide: `kann`, `wolle`. Dictionary: `kahn` (the only entry tagged `modal`; also inside `kahn-plas`), `wolt` (want), `bofik` (wanna); `wolle` = cotton. | `kahn`, `wolt`, `bofik` (MOD-3). |
| C-28 | Because / about | Guide: `darum`, `pahr`. Dictionary: `wahn`, `darab`. | `wahn`, `darab` (SUB-2, PRP-1). |
| C-29 | Indefinites | Guide: `alvse`, `irgenkto`. Retired dictionary/guide forms: `vsedeng`, `luboman`, `etvasch`, `vseNm`, `schtojem`, `anyvasch`. | Current forms `alscht`, `irgkto`, `manscht`, `alkto`, `mankto`, `irgscht` (Module 18.1, 19.2). |
| C-30 | `nucht` | The dictionary note on `nucht` calls it the standard negation marker "for intransitive or transitive clauses"; the Guide's rule is dual (`-nu` with an object, `nucht` without). | Guide rule kept: the dictionary note is generic boilerplate and does not contradict the explicit rule (NEG-1..4). Open gap G-22. |
| C-31 | `sein` | Guide: "your = `sein`". Dictionary: `sein` = six. | `ben` / `su` / `av'ben` / `av'su`; `sein` is only the numeral (6.1). |
| C-32 | Start, food, peace | Guide: `start`, `jade` = food, `ruhig` = peace. Dictionary: `begin`, `izeug`, `ruhig` = quiet, peace = `friede`. | Dictionary forms; `unruhig` and `jad'ze` kept as guide-only items (Module 19.1). |
| C-33 | Drink | Dictionary headword `drink` = `trink`, but its entry `drank` = `shoun trink` and the Guide's prefix example `austrink` use `trink`. | `trink` kept (two sources agree). Open gap G-23. |
| C-34 | Order | Dictionary: `order` = `brivav`. Guide: `schtobe` in `mek schtobe` (configure). | Both kept: `schtobe` only inside `mek schtobe`. |
| C-35 | People / person | Guide: `penk` = person. Dictionary: `penk` = people, `person` = person. | `penk` (plural-collective, `Seckeh penk` = who); `person` removed in 9.5. |
| C-36 | "Again" | Dictionary adverb `wieda`; Guide prefix `wieder-`. | Both kept: the prefix is MOR-5, the adverb is separate. |
| C-37 | Hyphens | ORT-3 said the only hyphen is `av-`; the dictionary has `kahn-plas`, `high-security`. | Dictionary hyphenated headwords are verbatim (DIC-4). |
| C-38 | `quick` | Dictionary entry `quick` is empty, but `kviklusep` (easily) contains `kvik`. | `kvik` kept as guide-only. |
| C-39 | Participle entries | Dictionary: `built` = `urzbau`, `made` = `favr`. Gold sentence: `shoun bau`. | Finite past = `shoun` + root; participle entries only name a state (DIC-6). |
| C-40 | WH domain nouns | Dictionary: reason = `grund`, place = `punkt`. Guide: `Seckeh prichin`, `Seckeh plas`. | `prichin` and `plas` kept inside the WH phrases (QST-2); the nouns are `grund` / `punkt`. |
| C-41 | Reflexives | Old dictionary: only `sebm` (themselves) and `reflektk` (herself); no other form. | `yaselb`, `suselb`, `benselb`, `erselb`, `sheselb`, `yalselb`, `dehyeselb` (RFL-1..5). |
| C-42 | Word invention | v9.1: all invention forbidden (L21, LEX-2, DIC-2); missing words became `[UNKNOWN]`. | 9.2: invention allowed **only** through Module 16A for content words; closed-class words, names, numbers and idioms stay excluded (COIN-1). |
| C-43 | Gendered articles | 9.2 and earlier: `den` / `ein` for every noun, no gender (G-18). Owner decision in 9.3: two genders (`den` neutral-male, `deny` female) assigned by noun ending; `ein` / `eine`; plurals keep the singular's gender. | GEN-1 to GEN-8. All examples re-gendered. |
| C-44 | Question helpers | 9.3 and earlier: `chez` in formal questions only; informal questions had no helper (REG-3). WH and how used `chez` too. | 9.4 owner decision: one helper per question type in both registers (HLP-1, HLP-2). `chez` stays for formal Yes/No. |
| C-45 | Closed-class coinage | COIN-1 forbade coining question words. | Exception for the helper family and `grad`, `wehl`, `obe` (HLP-7). |
| C-46 | Quantity, degree, which, whose | QST-7 and POS-6 were gaps. | `Seckeh viel/melok/grad`, `Seckeh wehl`, `Seckeh penk av-[noun]` (QST-7, QST-12). |
| C-47 | Inflected English words coined as new words (`has` -> `habe`, "trolling" -> `trosh`, a long list of `-s` verbs) | Lemma first. No word, coining or entry for an inflection (LEM-1 to LEM-6, L28). |
| C-48 | `Su dorn`, `Ben dorn` in the log | `Su` and `Ben` always take `doun` (FIN-5a, L27). |
| C-49 | "I like to play" rendered with `muss` (must) | `lyuba` + `-en` frame (MOD-16). |
| C-50 | Imperative with a German infinitive (`Schreiben`) | Dictionary root `schrei`; imperatives use the root (IMP-1, L30). |
| C-51 | Lower-case `ui` for "UI" | Acronyms verbatim in capitals (NAM-7). |
| C-52 | "United States" left in English; `europana` used as an adjective; English `nation` | `Ferjed Derzheni`, `europanisk`, `derzhe` (NAM-8). |
| C-53 | "that has" translated as "this is" | `Seckeh ... haben doun` (REL-4). |
| C-54 | "What is going on?" translated word for word with a detached `an` | Idiom: `pass` (LEX-3, LEX-6). |
| C-55 | Subject WH-question with no core, and "your username" turned into `Ben doun` | QST-14, QST-15. |

---

## MODULE 27 - COMPLETION RULES (new in 10.0)

All words in this module are owner-approved fixed text (G-40). Tag: [DERIVED] unless stated.

### 27.1 Modal negation and tense
- **MNEG-1** Negate a modal by suffixing `-nu` to the modal: `kahnnu`, `mussnu`, `woltnu`, `bofiknu`. This holds with or without an object. The infinitive is untouched. ✔ `Yem kahnnu Roblox spilen.` ✔ `Su mussnu verlassen.` ✘ `Yem kahn nucht spilen.` ✘ `Yem kahn Roblox spilenu.`
- **MFUT-1 Modal + tense.** Future: `geht` before the modal (Table A future core; fused `Yeht` etc. only for their own pronoun): `Yeht kahn Roblox spilen.` `Su geht muss verlassen.` Past: `shoun` / `shorn` before the modal: `Ya shoun kahn Roblox spilen.` In V2: `Morgen geht Ya kahn Roblox spilen.` Negation still sits on the modal: `Yeht kahnnu Roblox spilen.`

### 27.2 Prepositions
- **PREP-N1** `radi` for, `na` on, `posle` after, `ohne` without, `vne` out (of), `nieder` down; "onto" = the two words `tu na` (never fused, never one word). They never fuse with `den` / `deny` (PRP-2): `radi deny aufsita`, `na den heim`, `posle den task`, `ohne briv av'mi`. Prepositional phrases are never direct objects (NEG-5).

### 27.3 Passive
- **PAS-1** `gewor` is an invariant passive helper placed right after the finite core, before the root verb. The agent is introduced by `sorgfalt` (by). The core carries tense. ✔ `Deny aufsita doun gewor bau sorgfalt den konig.` (The castle is built by the king.) ✔ `Deny aufsita shoun gewor bau.` ✔ `Deny aufsita geht gewor bau.`
- Negation: no direct object follows, so `nucht` after the verb: `Deny aufsita doun gewor bau nucht.`
- Modal: `Deny aufsita muss gewor bauen.` In questions: `Chez deny aufsita doun gewor bau?`

### 27.4 Conditional
- **CND-1** `wurd` = "would". It acts exactly like `geht` (Tables A to D) but has **no fused form**: `Ya wurd spile Roblox.` `Wurd Ya spile Roblox?` is wrong (a question needs a helper, HLP-1): `Chez Su wurd spile Roblox?` In V2: `Heute wurd Ya spile Roblox.` Subordinate: last word. "Would be able" = `wurd kahn`: `Ya wurd kahn Roblox spilen.` "could" (polite) = `wurd kahn`; "could" (past ability) = `shoun kahn`. If-then: `Wehn Su gehk doun, dashe Ya wurd gehk.`

### 27.5 Numbers 100 and above
- **NUM-10** `hundert` = 100, `Digit hundert` = 200 to 900: `Doiw hundert`. `tausend` = 1,000, `[1-999] tausend` for more: `Doiw tausend`. Remainder follows after a space with no joiner: 325 = `Dry hundert doiwikn Foiw`; 2,014 = `Doiw tausend dezin Caut`; 101 = `hundert Ein`; 1,000,000 stays `milion` only as a bare word (`milion` = 10^6; larger numbers: NUM-14). Digit words are capitalized (NUM-5); `hundert`, `tausend`, `milion` stay lower-case. A noun after a number above one is plural (PLU-4).
- **ORD-1 Ordinals.** `vralet` (first) and `flumed` (second) stay. From third on: cardinal (lower-case, final word only) + `te`, collapsing a double `t`: `dryte` 3rd, `caute` 4th, `foiwte` 5th, `seizte` 6th, `siebte` 7th, `akchte` 8th, `neinte` 9th, `dezite` 10th, `doiwikte` 20th, 21st = `doiwikn einte`, `hunderte` 100th, `tausendte` 1,000th. An ordinal is an adjective: `dryte spilezung` (no gender change).

### 27.5a Decimals, fractions and percent (10.1)
- **NUM-11 Decimals.** `[integer] mavud [digit] [digit] ...`. The integer part is generated by NUM-1 to NUM-10; `mavud` (the dictionary's "dot") is lower-case; every digit after it is read one by one as a capitalized digit word. A noun after a decimal is plural (PLU-4).
  ✔ `Dry mavud Ein Caut` (3.14) ✔ `Zer mavud Foiw` (0.5) ✔ `Doiw mavud Zer Foiw` (2.05) ✔ `Dry mavud Foiw spilezeng` (3.5 games)
- **NUM-12 Fractions.** `[numerator] [denominator]`. The denominator is the ordinal of ORD-1 used as a noun. With numerator 1 it stays singular; above 1 it takes the plural (MOR-4a, an `e` is dropped before `-eni`). One half is the coined noun `halb` (never `flumed`), plural `halbeni`. A mixed number joins the whole part and the fraction with `n` (and).
  ✔ `Ein dryte` (1/3) ✔ `Doiw dryteni` (2/3) ✔ `Dry cauteni` (3/4) ✔ `Sieb hunderteni` (7/100) ✔ `Ein halb` (1/2) ✔ `Dry halbeni` (3/2)
  ✔ `Ein n Ein halb` (1 1/2) ✔ `Doiw n Ein dryte` (2 1/3) ✔ `Ein halb av den apeleni` (half of the apples)
  ✘ `Ein flumed` ✘ `Doiw dryte` (denominator not plural)
- **NUM-13 Percent.** `[number] prozent`. `prozent` (coined) is a **measure word and stays singular** after any number (it is the one exception to PLU-4). Decimals work as in NUM-11.
  ✔ `foiwik prozent` (50%) ✔ `Ein prozent` (1%) ✔ `Zer mavud Foiw prozent` (0.5%) ✔ `hundert prozent` (100%)
  ✘ `foiwik prozenteni`
- **NUM-14 Millions (10.1).** `[1-999] milion`, then the remainder after a space with no joiner (as NUM-10). `milion` is lower-case and **invariant** after any number, like `tausend`. The range ends at 999,999,999; nothing above is generated. The ordinal is `milionte` (ORD-1). A noun after a number above one is plural (PLU-4).
  ✔ `Ein milion` (1,000,000) ✔ `Doiw milion` (2,000,000) ✔ `Doiw milion Foiw hundert tausend` (2,500,000) ✔ `Ein milion dezin Caut` (1,000,014)
  ✔ `hundert milion` (100,000,000) ✔ `Nein hundert neinikn Nein milion Nein hundert neinikn Nein tausend Nein hundert neinikn Nein` (999,999,999)
  ✘ `Doiw milioneni` ✘ `Ein milion` for 1,000 (use `tausend`)
- **NUM-15 Negative numbers (10.1).** `minus` (coined, lower-case) goes **before** the whole number, which is built unchanged. It works with integers, decimals (NUM-11) and fractions (NUM-12). `minus` is a number marker, not a negation: it never takes `-nu` and is not an absolute negative (NEG-4). The noun after follows PLU-4 on the number's size (`minus Ein` is singular).
  ✔ `minus Foiw` (-5) ✔ `minus doiwikn Ein` (-21) ✔ `minus Dry mavud Ein Caut` (-3.14) ✔ `minus Ein halb` (-1/2) ✔ `minus Doiw milion` (-2,000,000)
  ✘ `Foiw minus` ✘ `minusnu Foiw`

### 27.6 Reflexive "itself" and free-standing possessives
- **RFL-7** itself = `esselb` (tangible, `Es`) or `etselb` (abstract, `Et`). Same rules as RFL-1 to RFL-4.
- **POSF-1** Mine / yours / his / hers / ours / theirs = the possessive alone: `av'mi`, `av'ben`, `av'su`, `av'er`, `av'she`, `av'yemvyeni`, `av'dehyr`, with no noun. ✔ `Dehyss doun av'mi.` (This is mine.)

### 27.7a Subjunctive
- **SBJ-1** `konj` marks an unreal or hypothetical **if-clause** ("if I were", "if he came") and the clause after "wish". It replaces the tense core of that clause: one helper per clause (FIN-1), the same form for every person, no fused form. The **result** clause uses `wurd` (CND-1), not `konj`. Subordinate order (Table C): `konj` is the last word.
  ✔ `Wehn Ya xnekst konj, dashe Ya wurd spile Roblox.` (If I were great, I would play Roblox.)
  ✔ `Wehn Su Roblox spile konj, dashe Ya wurd gehk.` (If you played Roblox, I would go.)
  ✔ `Yem wunsch dass Er kome konj.` (I wish he came.)
  ✔ A fronted `wehn konj` clause is followed by `dashe` (SUB-6). Negation as usual: `Wehn Su Roblox spilenu konj, ...`
  ✘ `Wehn Ya konj xnekst` (helper not last) ✘ `Ya konj spile Roblox, ...` in a result clause.
- **SBJ-2 Past unreal (10.1).** "If I had played" = the clause's subject and verb, then the **past helper**, then `konj` as the last word: `[Sub] [S] [O] [V] shoun konj` (`shorn konj` for a plural subject, FIN-5). This is the **one stated exception to FIN-1**: `shoun` / `shorn` + `konj` count together as one core. The result clause is **`shoun wurd`** (`shorn wurd` for a plural subject) + verb, the tense helper before `wurd` like MFUT-1. A fronted `wehn` clause is followed by `dashe` (SUB-6). No fused forms.
  ✔ `Wehn Ya Roblox spile shoun konj, dashe Ya shoun wurd gehk.` (If I had played Roblox, I would have gone.)
  ✔ `Wehn Yal Roblox spile shorn konj, dashe Yal shorn wurd gehk.` (If we had played Roblox, we would have gone.)
  ✔ `Yem wunsch dass Er kome shoun konj.` (I wish he had come.)
  ✔ `Wehn Su Roblox spilenu shoun konj, ...` (negation stays on the verb)
  ✘ `Wehn Ya Roblox spile shoun, ...` (reads as a real past) ✘ `Wehn Ya Roblox spile konj shoun` (`konj` must be last) ✘ `dashe Ya wurd shoun gehk` (wrong order)

### 27.7 Suffixes
- **SUF-1** `-heit` on an adjective makes a quality noun (-ness): `kvik` -> `kvikheit` (always female, GEN-4): `deny kvikheit`. `-isk` on a noun or adjective makes "-ish / relating to": `konig` -> `konigisk`. Both attach whole, drop nothing, and are lower-case. `-isk` also forms demonyms (NAM-8). Plural by PLU-1: `kvikheiteni` (GEN-5 keeps `deny`).

---

## MODULE 28 - ROLES, IDENTITY AND THE HORTATIVE (10.1)

All rules in this module are **owner decisions** (10.1). Words are checked against `Dictionary.json` (G-42).

### 28.1 The identity verb `bist`
- **ROL-1 `bist` = "to be [someone]".** It is an ordinary action verb: invariant (FIN-6), placed after the normal core (Tables A to D), never fused. It is **required** when the predicate is an identity: a nationality, job, title, role, name or relationship. The core supplies tense and person; `bist` adds nothing else.
  ✔ `Yem bist Deutschmann.` (I am German.)
  ✔ `Yem bist ein sicherbremol.` (I am a security guard.)
  ✔ `Yem bist den sicherbremol.` (I am the security guard.)
  ✔ `Er doun bist den sicherbremol.` (He is the security guard.)
  ✔ `Ya shoun bist ein sicherbremol.` (I was a security guard.)
  ✔ `Yeht bist den sicherbremol.` (I will be the security guard.)
  ✔ `Heute doun Ya bist den sicherbremol.` (Today I am the security guard; V2, FIN-4.)
  ✘ `Yem Deutschmann.` ✘ `Yem doun bist Deutschmann.` (double core, FIN-1) ✘ `Yem bisten Deutschmann.` (`-en` only in modal frames)
- **ROL-2 `bist` is not the general copula.** Adjectives, locations and states keep the plain copula (SVO-3): `Er doun xnekst.`, `Yem sicher.` ✘ `Yem bist xnekst.`
- **ROL-3 Articles follow English.** A bare nationality, job or name takes no article; "a ..." takes `ein` / `eine`; "the ..." takes `den` / `deny` (GEN). `Yem bist Deutschmann.` ("I am German"), `Yem bist ein Deutschmann.` ("I am a German").
- **ROL-4 Female role nouns.** When the person is a woman, the role noun takes a suffix chosen by its **last letter**. All other nouns only change their article (GEN-3).
  | Role noun ends in | Female form | Examples |
  | :--- | :--- | :--- |
  | `-mann` | replace `mann` with `-in` | `Deutschmann` -> `Deutschin`; `spilemann` -> `spilein`; `aufgibalmann` -> `aufgibalin` |
  | a consonant | add `-in` | `bremol` -> `bremolin`; `sicherbremol` -> `sicherbremolin`; `briv` -> `brivin`; `komrad` -> `komradin` |
  | a vowel (`a e i o u y`) | add `-ka` | `lehre` -> `lehreka` |
  The female form is always `deny` / `eine` (GEN-3, GEN-4). Lexicalized female words (`medla`) are used as listed.
  ✔ `She doun bist Deutschin.` ✔ `She doun bist eine sicherbremolin.` ✔ `She doun bist deny sicherbremolin.`
  ✘ `She doun bist eine Deutschmann.` (male form for a woman)
- **ROL-5 Plural.** Plural by MOR-4a (a final `n` or `e` is dropped before `-eni`) on the role noun; the gender article stays (GEN-5). ✔ `Yalm bist Deutschmaneni.` ✔ `Dehye dorn bist bremolieni.`
- **ROL-6 Negation.** A predicate noun is never a direct object (NEG-5), so `nucht` goes **directly after `bist`**, before the predicate. Never `-nu` on `bist`.
  ✔ `Yem bist nucht Deutschmann.` ✔ `Er doun bist nucht den sicherbremol.` ✘ `Yem bistnu Deutschmann.`
- **ROL-7 Questions.** Helper rules (Module 12) are unchanged; `bist` stays after the core.
  ✔ `Chez Su doun bist Deutschmann?` (Are you German?) ✔ `Kez Ben doun bist den sicherbremol?`
  ✔ `Seckeh penk chel Su doun bist?` (Who are you?) ✔ `Seckeh penk kel Ben doun bist?`
- **ROL-8 Subordinate and modal frames** [DERIVED] [GAP G-44]. Subordinate (Table C, helper last): `... dass Er Deutschmann bist doun.` Modal (MOD-2, MOD-8): `Yem muss den sicherbremol bisten.` (I must be the security guard.)
- **ROL-9 Names.** "I am Tom" takes `bist`: ✔ `Yem bist Tom.` A name takes no article (OUT-5, NAM-7).
- **ROL-10 Relationships.** Every relationship word (friend, brother, boss, teammate) is an identity and takes `bist`. The possessor follows the noun with `av'` (POS-2).
  ✔ `Er doun bist komrad av'mi.` ✔ `She doun bist brivin av'mi.` ✔ `Su doun bist aufgibalmann av'mi.` ✔ `Yem bist briv av'er.`
- **ROL-11 "As a [role]" has no separate word.** "I work as a guard" is `Yem bist ein bremol.` Do not use `als` (it means "than", CMP-3).
- **ROL-12 Role compounds.** A modifier plus a head noun is glued into one lower-case word; the **head** (last element) decides gender (GEN-4). Fixed: security guard = `sicherbremol` (`sicher` safe + `bremol` guard). It forms the female with ROL-4 and the plural with MOR-4a: `sicherbremolin`, `sicherbremoleni` (female plural `sicherbremolieni`). The general compound rule is MOR-4 (plain glue, two elements maximum).

### 28.5 The hortative "Let's"
- **HRT-1 `lez`** (new, fixed) + `Yal` + verb + object, with no core and no helper. `lez` is for "let us" only; it is not a general "let" (G-45). Negation is `-nu` on the verb (NEG-2, IMP-8) or `nucht` when intransitive (NEG-3). Fused forms are illegal here (IMP-1).
  ✔ `Lez Yal spile Roblox!` (Let's play Roblox!)
  ✔ `Lez Yal spilenu Roblox!` (Let's not play Roblox!)
  ✔ `Lez Yal gehk nucht!` (Let's not go!)
  ✘ `Yalm spile Roblox!` (statement, not a hortative) ✘ `Lez Er spile Roblox!`

### 28.6 Modal subject tokens by tense (closes G-13)
- **MOD-17 Present: no helper, any person.** The modal is the finite verb. Present tokens come from Table D: `Yem`, `Yalm`, `Ben` / `Su`, `Er`, `She`, `Dehye`.
- **MOD-18 Past and future: tense helper + modal, any person** (MFUT-1). The fused forms carry the tense, so "we" and "I" change with it.
  | Person | Present | Future | Past |
  | :--- | :--- | :--- | :--- |
  | I | `Yem muss` | `Yeht muss` | `Ya shoun muss` |
  | we | `Yalm muss` | `Yahlt muss` | `Yal shorn muss` |
  | you | `Su muss` / `Ben muss` | `Su geht muss` / `Ben geht muss` | `Su shoun muss` / `Ben shoun muss` |
  | he / she | `Er muss` / `She muss` | `Er geht muss` / `She geht muss` | `Er shoun muss` / `She shoun muss` |
  | they | `Dehye muss` | `Dehyt muss` | `Dehye shorn muss` |
  `Su` and `Ben` take `shoun` even when plural (FIN-5a). Negation stays on the modal (MNEG-1): `Er shoun mussnu spilen.`
  ✔ `Er muss spilen.` ✔ `Er geht muss spilen.` ✔ `Yal shorn muss spilen.` ✔ `Yahlt muss spilen.`
  ✘ `Er doun muss spilen.` (MOD-4) ✘ `Yal muss spilen.` in the present (the fused `Yalm` is required, FIN-3c)

### 28.9 Gold tests (this module)
| # | English | Schalowitsk | Rules |
| :--- | :--- | :--- | :--- |
| G-R01 | I am German. | `Yem bist Deutschmann.` | ROL-1, ROL-3 |
| G-R02 | She is German. | `She doun bist Deutschin.` | ROL-1, ROL-4 |
| G-R03 | I am the security guard. | `Yem bist den sicherbremol.` | ROL-1, ROL-12 |
| G-R04 | She is the security guard. | `She doun bist deny sicherbremolin.` | ROL-4, GEN-3 |
| G-R05 | I am not a security guard. | `Yem bist nucht ein sicherbremol.` | ROL-6 |
| G-R06 | Are you the security guard? (formal) | `Chez Su doun bist den sicherbremol?` | ROL-7 |
| G-R07 | Who are you? (informal) | `Seckeh penk kel Ben doun bist?` | ROL-7 |
| G-R08 | I am Tom. | `Yem bist Tom.` | ROL-9 |
| G-R09 | He is my friend. | `Er doun bist komrad av'mi.` | ROL-10 |
| G-R10 | She is my sister. | `She doun bist brivin av'mi.` | ROL-4, ROL-10 |
| G-R11 | We are Germans. | `Yalm bist Deutschmaneni.` | ROL-5 |
| G-R12 | I work as a guard. | `Yem bist ein bremol.` | ROL-11 |
| G-R13 | I will be the security guard. | `Yeht bist den sicherbremol.` | ROL-1 |
| G-R14 | He is great. | `Er doun xnekst.` (adjective, no `bist`) | ROL-2 |
| G-R15 | Let's play Roblox! | `Lez Yal spile Roblox!` | HRT-1 |
| G-R16 | Let's not play Roblox! | `Lez Yal spilenu Roblox!` | HRT-1, NEG-2 |
| G-R17 | He must play. | `Er muss spilen.` | MOD-17 |
| G-R18 | He will have to play. | `Er geht muss spilen.` | MOD-18 |
| G-R19 | We had to play. | `Yal shorn muss spilen.` | MOD-18 |
| G-R20 | They will have to play. | `Dehyt muss spilen.` | MOD-18 |
| G-R21 | a food house | `ein izeughze` | MOR-4, GEN-4 |
| G-R22 | the food houses | `deny izeughzeni` | MOR-4d, MOR-4a |
| G-R23 | the king's castle | `deny konigaufsita` | MOR-4, GEN-4 |
| G-R24 | the female security guards | `deny sicherbremolieni` | ROL-4, MOR-4a |
| G-R25 | If I had played Roblox, I would have gone. | `Wehn Ya Roblox spile shoun konj, dashe Ya shoun wurd gehk.` | SBJ-2 |
| G-R26 | If we had played Roblox, we would have gone. | `Wehn Yal Roblox spile shorn konj, dashe Yal shorn wurd gehk.` | SBJ-2, FIN-5 |
| G-R27 | I wish he had come. | `Yem wunsch dass Er kome shoun konj.` | SBJ-2 |
| G-R28 | 3.14 | `Dry mavud Ein Caut` | NUM-11 |
| G-R29 | two thirds | `Doiw dryteni` | NUM-12 |
| G-R30 | one and a half | `Ein n Ein halb` | NUM-12 |
| G-R31 | 50% | `foiwik prozent` | NUM-13 |
| G-R32 | 50% at the start of a sentence | `Foiwik prozent` | ORT-4.1, ORT-4.4 |
| G-R33 | She is German. | `She doun bist Deutschin.` | ORT-4.7 |
| G-R34 | John, find it! | `John, stevad Ben es!` | ORT-4.8, IMP-9 |
| G-R35 | I don't like Roblox. | `Yem lyubanu Roblox.` | LNEG-1 |
| G-R36 | I don't like playing. | `Yem lyubanu spilen.` | LNEG-1 |
| G-R37 | I didn't like to play Roblox. | `Ya shoun lyubanu Roblox spilen.` | LNEG-1 |
| G-R38 | 2,500,000 | `Doiw milion Foiw hundert tausend` | NUM-14 |
| G-R39 | 1,000,014 | `Ein milion dezin Caut` | NUM-14 |
| G-R40 | -5 | `minus Foiw` | NUM-15 |
| G-R41 | -3.14 | `minus Dry mavud Ein Caut` | NUM-15, NUM-11 |
| G-R42 | There is no king. | `Dah doun kein konig.` | NEG-11 |
| G-R43 | There are no kings. | `Dah dorn kein konigeni.` | NEG-11, PLU-1 |
| G-R44 | I have no keys. | `Yem haben keine keyeni.` | NEG-11, GEN-4 |
| G-R45 | He is not great. | `Er doun nucht xnekst.` | NEG-12 |
| G-R46 | There is not a king. | `Dah doun nucht ein konig.` | NEG-12 |

---

## MODULE 26 - OPEN GAPS AND SAFE FALLBACKS

Everything here is **undefined** in all five sources. The AI applies the fallback; the owner may later replace it with a real rule. Each row says what to decide.

| ID | Gap | Fallback in force | Owner decision needed |
| :--- | :--- | :--- | :--- |
| G-01 | ~~Modal + negation~~ **RESOLVED** in 10.0 | `-nu` on the modal (MNEG-1) | none |
| G-02 | ~~Modal + past / future~~ **RESOLVED** in 10.0 | tense helper + modal (MFUT-1) | none |
| G-03 | ~~Prepositions: for, on, after, without~~ **RESOLVED** in 10.0 (`radi`, `na`, `posle`, `ohne`); `vne`, `nieder`, `tu na` added too | none | none |
| G-04 | ~~Numbers above 100, ordinals, decimals, fractions, negatives, millions~~ **RESOLVED** in 10.0 and 10.1 (NUM-10 to NUM-15, ORD-1). Only 1,000,000,000 and above remains | Arabic digits | A word for 10^9, if ever needed |
| G-05 | ~~Mash-up rule contradicts its own example~~ **RESOLVED** in 10.1 | plain glue, two elements max (MOR-4, MOR-4e) | none |
| G-06 | ~~"how many / much / long / old / far"~~ **RESOLVED** in 9.4 | `Seckeh viel` / `melok` / `grad` (QST-7) | none |
| G-07 | Object pronouns (me, him, us...) | reuse the Object/Dative column (FIN-10); the dictionary lists `mi` as dative | Confirm or replace |
| G-08 | ~~Passive, "would", subjunctive~~ **RESOLVED** in 10.0 (PAS-1, CND-1, SBJ-1) | `gewor`, `wurd`, `konj` | none |
| G-41 | ~~Past unreal ("if I had played")~~ **RESOLVED** in 10.1 | `shoun konj` if-clause, `shoun wurd` result (SBJ-2) | none |
| G-09 | Main-clause "I do it" (the dictionary confirms `doun` = am for separated 1SG) | `Yem es` (FIN-7) | Confirm |
| G-10 | ~~Negated copula, existential and modal~~ **RESOLVED** in 10.0 and 10.1 (MNEG-1, ROL-6, NEG-11, NEG-12) | `kein` for "no X", `nucht` after the helper for the plain copula | none |
| G-11 | ~~"Let's ..." (hortative)~~ **RESOLVED** in 10.1 | `lez Yal [V] [O]!` (HRT-1) | none. "Let him / let them" is not covered (G-45) |
| G-12 | Possessive forms for `Ben`, `Su`, `Er`, `She`, `Yal`, `Dehye` | `av'` + object form (6.1, POS-2) | Confirm each form |
| G-13 | ~~Modal subject token for non-1SG persons~~ **RESOLVED** in 10.1 | present: no helper; past / future: tense helper (MOD-17, MOD-18) | none |
| G-14 | ~~`ruks` or `rukz`~~ **RESOLVED** by the dictionary | `rukz` | none |
| G-15 | Modal inside a subordinate clause | `V-en` then modal (SUB-7) | Confirm |
| G-16 | `alsitnu` with past / future | Subject + `alsitnu` + helper + verb (FIN-9) | Confirm |
| G-17 | Countries, languages, continents: **RESOLVED** by the dictionary. Major cities: no entries seen | keep city names verbatim (NAM-2) | City names |
| G-18 | ~~Plural of `den`, `ein`~~ **RESOLVED** in 9.3 | plural article = the singular noun's article (GEN-5); bare plural for indefinite | none |
| G-19 | ~~`itself`; free-standing possessives~~ **RESOLVED** in 10.0 (RFL-7, POSF-1) | `esselb` / `etselb`; `av'mi` alone | none |
| G-20 | Headwords whose `schalowitsk` field is empty in `Dictionary.json` | coin under Module 16A (DIC-2) | Fill the empty entries with the coined or chosen words |
| G-21 | `e`-final verb roots and `-zung`: the rule drops `e`, the only attested example (`spilezung`) keeps it | rule text for new words; headword for `spile` (MOR-1) | Does the drop rule apply to `e` at all? |
| G-22 | The dictionary note on `nucht` says it serves transitive clauses too | Guide's dual negation kept (C-30) | Confirm dual negation |
| G-23 | `trink` (Guide, and the dictionary entry `drank`) vs `poler` (dictionary headword `drink`) | `trink` (C-33) | Pick one |
| G-24 | Do `alzeit`, `meystens`, `ofte`, `mankzeit` drop the helper like `alsitnu`? | yes, same slot (TNS-7) | Confirm |
| G-25 | Coined words exist only in the session, so another chat may coin differently if the procedure is not followed exactly | the fixed tie-break COIN-7; session table COIN-8 | Move approved coinages into `Dictionary.json` (or a list in Module 19.1) |
| G-26 | Gender of nouns that fit no listed ending and are not people (e.g. words ending in `x`, `z`, `ch`) | default `den` (GEN-2c) | Add more endings if you want them female |
| G-27 | Dictionary nouns whose gender by ending feels wrong, and lexicalized female-person words (mother, queen; `medla` = girl exists). **Female role nouns RESOLVED in 10.1** (ROL-4) | rule only (GEN-3, GEN-4, ROL-4) | List lexicalized exceptions to be hard-coded |
| G-28 | The seven new helpers and `grad`, `wehl`, `obe` were checked only against this file; `Dictionary.json` was not available | fixed forms stay (HLP-7) | Check for clashes; rename the clashing word here |
| G-29 | Adjectives for old, far, long that the dictionary lacks, used after `grad` | coin under Module 16A | Add the adjectives |
| G-30 | Several questions joined by `n` | each direct question keeps its own helper | Confirm |
| G-31 | Tag questions with a changed polarity ("is it? isn't it?") | one invariant tag helper, no polarity change (QST-9) | Confirm |
| G-32 | Embedded manner "how I like it" | `Schalowit` closes the embedded clause (QST-16) | Confirm the placement |
| G-33 | ~~Negation of `lyuba`~~ **RESOLVED** in 10.1 | `-nu` on `lyuba` always (LNEG-1, MOD-16) | none |
| G-34 | A verb for "complete / finish" (`finish` is an empty entry; `kompletn` is an adjective) | `mek` + object + `kompletn` (ADJ-5) | Choose a verb |
| G-35 | Demonym adjectives other than `europanisk` | `-isk` (NAM-8, SUF-1) | Approve the pattern |
| G-36 | Multi-word country names such as United States | word by word, capitalized (NAM-8) | Add an entity entry |
| G-37 | Subject-WH core for plural subjects | `doun` unless plural is stated, then `dorn` (QST-14) | Confirm |
| G-38 | `enter` was removed in 9.5 (straight English) | coin a verb under Module 16A | Pick a word |
| G-39 | Verb roots used as nouns (`bervin`) | add `-zung` (MOR-1) | Confirm |
| G-026 | the castle (female noun) | `deny aufsita` | GEN-4 |
| G-027 | a game | `eine spilezung` | GEN-4 |
| G-028 | a king | `ein konig` | GEN-4 |
| G-029 | to the castle [D] | `tu'deny aufsita` | GEN-4 |
| G-030 | to the king | `tu'den konig` | GEN-4 |
| G-031 | the kings | `den konigeni` | GEN-4 |
| G-032 | the castles | `deny aufsitaeni` | GEN-4 |
| G-42 | The 10.1 words `kein`, `bist`, `lez`, `sicherbremol`, `halb`, `prozent`, `minus`, `tausend`, `milion` were checked against the 1,374-entry `Dictionary.json` supplied with this edition and are free there. `bist` coexists with the existing `existend` (exist / be) | fixed forms stay | Decide whether `existend` should stay |
| G-43 | The header says 1,762 dictionary entries; the supplied file has 1,374, none empty, so G-20 may be stale | treat the supplied file as complete | Supply the full dictionary or correct the count |
| G-44 | `bist` in subordinate and modal frames (ROL-8) | derived from Table C and MOD-8 | Confirm |
| G-45 | Permissive "let him / let them" (not `lez`, which is `Yal` only) | rephrase with a modal or a plain statement | A permissive form |
| G-40 | The 10.0 words (`radi`, `na`, `posle`, `ohne`, `vne`, `nieder`, `gewor`, `wurd`, `konj`, `tausend`, `milion`, `esselb`, `etselb`, `-heit`, `-isk`, ordinals) were checked only against this file;  | fixed forms stay | Check against `Dictionary.json`; confirm `gewor` / `wurd` |

**Where the missing words are:** every headword in `Dictionary.json` whose `schalowitsk` field is empty. Module 16A coins them on demand, but adding approved words to the dictionary is the only way to make them permanent across chats.

---

**END OF SPECIFICATION - Schalowitsk Master Lexicon v10.1**