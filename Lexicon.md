# Schalowitsk Grammar Reference & AI Translation Specification

## 1. Metadata

* Language: Schalowitsk

* Version: 5.0 (Inseparable Morphological Prefix System Update)

* Target Engine: Generative AI / Deterministic Translation Pipeline

* Scope: Fully explicit, machine-executable grammar reference for translation, generation, validation, and parsing

* Output mode: Strict Markdown / JSON-compatible rule enforcement

* System Constraints: Zero narrative conversational filler, strict rule adherence, deterministic output generation

## 2. AI Execution Pipeline & Translation Algorithm

When receiving an input text for translation into Schalowitsk, the AI engine **MUST** execute the following strict 5-step deterministic pipeline before generating output:

### Step 1: Input Analysis & Context Resolution

1. Parse input sentence into target clauses and identify main vs. subordinate clauses.

2. Identify sentence type: Declarative, Imperative, Conditional, Interrogative (WH-question or Yes/No).

3. Identify register: Formal (default or explicit polite) vs. Informal/Gaming/Casual.

4. Detect register slang: If casual, map non-standard input to 2000s-era equivalents.

### Step 2: Semantic & Syntactic Slot Mapping

For each clause, determine word order framework based on clause type and fronting:

* **Standard Main Clause (Default SVO)**:
  `[Subject] -> [Modifier] -> [Helper Verb] -> [Prefix-Action Word] -> [Object]`

* **Fronted Main Clause (Germanic V2 Rule - Section 3.1a)**:
  `[Fronted Adverbial/Time] -> [Helper Verb] -> [Subject] -> [Prefix-Action Word] -> [Object]`

* **Subordinate Clause (Verb-Final Rule - Section 3.3a)**:
  `[Conjunction] -> [Subject] -> [Prefix-Action Word] -> [Object] -> [Helper Verb]`

* Extract explicit or implicit Subject.

* Identify Helper Verb (Tense/Person alignment). **Note 1SG Present Contraction Rule (Section 5.3a):** `Yem` is a portmanteau of `Ya` + `em`. Never generate `Ya yem`.

* Identify Action Word and evaluate if a verb prefix applies (`an-`, `wieder-`, `aus-`). **Note Inseparable Prefix Constraint**: Verb prefixes NEVER detach or shift to the end of the clause.

* Classify Object: Tangible (`Es`), Abstract/State (`Et`), Direct Object, or Prepositional Object.

### Step 3: Rule Application & Constraint Verification

* **1SG Present Contraction Check**: Ensure `Yem` is used directly as Subject + Helper. Reject any string containing `Ya yem`.

* **Aspect Check**: Simple aspect is invariant. Do NOT use continuous suffixes or `-ing` markers.

* **Prefix Inseparability Check**: Verify that verb prefixes remain attached directly to the verb stem across all tenses, moods, and clause positions.

* **Negation Check**: Is clause Transitive (`[Action]-nu [Object]`) or Intransitive (`[Action] nucht`)? Verify no double negatives or absolute-negative conflicts (`alsitnu`).

* **Experiencer Check**: Does the clause contain a predicate adjective? If subject == experiencer, omit dative pronoun. If subject != experiencer, place dative pronoun (`mi`, `er`, etc.) between helper and predicate adjective.

* **Question Syntax Enforcement**: Place `Seckeh [Domain]` at index 0 or `Schalowit` at terminal position $N-1$. Insert `chez` only if register == Formal.

* **Number Parsing**: Translate numerical values using algorithmic rules (Section 14). Do not query standard dictionary for standalone digits/tens.

### Step 4: Lexical Lookup & Compound Generation

1. Query `Dictionary.json` for canonical roots.

2. Apply fallback strategies: Use single-word idiomatic equivalents over word-for-word English literal expressions.

3. Apply morphological rules: Nominalization (`-zung`), Agent (`-mann`), Pluralization (`-eni`/`-zeng`), Mash-ups (`Noun_A'Noun_B`), Pre-nominal Possessive Prefix (`av-`), Verb Prefixes (`an-`, `wieder-`, `aus-`), and Noun Prefixes (`un-`, `urz-`, `sam-`, `vse-`).

### Step 5: Post-Generation Validation Audit

Before output, verify:

* \[ \] Clause contains exactly **ONE** helper verb / pronoun-helper fusion.

* \[ \] No redundant subject pronoun before `Yem` (e.g., `Ya yem` is strictly forbidden; output MUST be `Yem`).

* \[ \] Helper verb is in slot 2 if an adverbial or time phrase is fronted in a main clause (V2 compliance).

* \[ \] Helper verb is in absolute terminal position of a subordinate clause.

* \[ \] Verb prefixes are glued to the verb stem and NOT separated to clause-final position.

* \[ \] No `-ly` or adverbial suffixes exist, and no `-ing` continuous suffixes exist.

* \[ \] Possessive forms use either post-nominal `av` or pre-nominal `av-` prefix structure.

* \[ \] Absolute terminal position of `Schalowit` in how-questions.

* \[ \] Proper names (except countries/languages/cities) are preserved verbatim without translation or morphological alteration.

## 3. Canonical Sentence Model

### 3.1 Main Clause Word Order & Germanic V2 Rule

* Default linear order (un-fronted):
  `[Subject] -> [Modifier] -> [Helper Verb] -> [Action Word] -> [Object]`

* **Rule 3.1a (Germanic V2 Rule)**: If an adverbial element, time phrase, or prepositional phrase is fronted to the absolute beginning of a main clause, Schalowitsk enforces strict Verb-Second (V2) order. The Helper Verb **MUST** shift to the second slot immediately following the fronted element, forcing the Subject after the Helper:
  `[Fronted Phrase] -> [Helper Verb] -> [Subject] -> [Action Word] -> [Object]`

  * *Standard SVO (1SG Present)*: `Yem spile Roblox heut.` ("I am playing Roblox today.")

  * *V2 Fronted (1SG Present)*: `Heut doun Ya spile Roblox.` ("Today am I playing Roblox.")

### 3.2 Standard Rule Summary

* Subject is omitted in imperative clauses.

* Modifier precedes the modified noun or verb.

* Helper verb indicates tense and person alignment.

* Action word remains uninflected across all tenses and aspects. Verb prefixes are strictly inseparable.

### 3.3 Subclause Patterns & Verb-Final Framing

* Standard Declarative: `[Subject] [Modifier] [Helper Verb] [Action Word] [Object]`

* Imperative: `[Action Word] [Object / Coordinate]`

* Conditional & Subordinate Clauses: `wehn [Condition Clause], dashe [Result Clause]`

* **Rule 3.3a (Subordinate Verb-Final Frame)**: In any subordinate clause introduced by a subordinating conjunction (`wehn`, `darum`, `whilst`, `dass`), the Helper Verb **MUST** shift to the absolute end of that subclause:
  `[Subordinator] -> [Subject] -> [Action Word] -> [Object] -> [Helper Verb]`

  * *Main Clause*: `Su doun gehk.` ("You go.")

  * *Subordinate Clause*: `...wehn Su gehk doun.` ("...when you go.")

  * *Full Conditional*: `Wehn Su gehk doun, dashe Yem gehk.` ("If you go, then I go.")

### 3.4 Aspect Uniformity Rule

* Schalowitsk does not distinguish continuous/progressive aspect from simple aspect morphologically.

* Do **NOT** introduce `-ing` suffixes, `doun-ing`, or auxiliary continuous markers.

* `Yem iz` covers both "I eat" and "I am eating".

### 3.5 Adjective and Adverb Behavior

* Adverbial suffixes are prohibited (e.g., `-ly`).

* Base adjective functions as adverb when used after a verb.

* Adjective-before-noun rule remains mandatory.

* A predicate adjective must make its experiencer/evaluator clear.

* **Rule 3.5a**: If clause subject == experiencer, omit dative pronoun.

  * *Correct*: `Yem schpavik spile Roblox!`

  * *Incorrect*: `Yem mi schpavik...`

* **Rule 3.5b**: If clause subject != experiencer, structure as:
  `[Subject] [Helper] [Experiencer/Dative Pronoun] [Predicate Adjective]`

  * Use `mi` for 1SG dative ("me / to me").

  * Use base pronoun forms (e.g., `er`) for 3SG dative.

  * Examples: `Roblox doun mi schpavik.`, `Roblox doun er schpavik.`

## 4. Pronouns and Possession System

### 4.1 Pronoun Lookup Table

| Role | Canonical Form | AI Parsing Rule | 
| ----- | ----- | ----- | 
| 1SG Subject | Ya | Use for non-present tenses or V2 inverted order | 
| 1SG Present Fused | Yem | Combined Subject + Present Helper (`Ya` + `em`). Do NOT prepend `Ya` | 
| 1SG Dative/Experiencer | mi | Use strictly for non-subject experiencer | 
| 2SG/PL Formal | Su | Use in polite or formal context | 
| 2SG/PL Informal | Ben | Use in casual, peer, or gaming context | 
| 3SG Masculine | Er | 3SG male referent | 
| 3SG Feminine | She | She 3SG female referent | 
| 1PL | Yal | 1PL group subject | 
| 3PL | Dehye | 3PL plural subject | 

### 4.2 Dual Possession Syntax

Saxon genitive (`'s`) is strictly prohibited. Possession must be rendered using one of two canonical structures:

1. **Post-Nominal Structure (Analytical `av`)**:
   `[Target] av [Possessor]`

   * Example: `Den kastelv av den konig.` ("The castle of the king.")

2. **Pre-Nominal Prefixed Structure (Saxon Hybrid `av-`)**:
   `[Possessor] av-[Target]`

   * Example: `Den konig av-kastelv.` ("The king's castle.")

*Both forms are grammatically valid; the pre-nominal `av-` prefix serves as a concise equivalent mimicking English possessive patterns.*

### 4.3 Determiners and Articles

| Meaning | Form | 
| ----- | ----- | 
| the | den | 
| a / one | ein | 
| this / that | dehyss | 
| these / those | dehysseni | 

### 4.4 Prepositional Fusion Rules

Prepositions ending in vowels fuse deterministically with `den` via apostrophe:

* `tu` + `den` $\rightarrow$ `tu'den`

* `en` + `den` $\rightarrow$ `en'den`

## 5. Universal Verb & Helper Resolution System

### 5.1 Base Verb Rule

* Action verbs are strictly invariant across person, number, tense, and aspect.

* Never add inflectional or aspectual suffixes (`-s`, `-ed`, `-ing`) to action verbs.

* Verb prefixes (`an-`, `wieder-`, `aus-`) are **strictly inseparable** and remain attached to the root at all times.

### 5.2 Universal Helper Forms

| Form | Function | Context | 
| ----- | ----- | ----- | 
| doun | singular present / is / do | 1SG (V2 only), 2SG, 3SG | 
| dorn | plural present / are / do | 1PL, 3PL | 
| shoun | singular past / was / did | 1SG, 2SG, 3SG | 
| shorn | plural past / were / did | 1PL, 3PL | 
| geht | future auxiliary / will | All persons | 

### 5.3 Pronoun + Helper Resolution Matrix

| Person / Register | Pronoun | Past | Present | Future | 
| ----- | ----- | ----- | ----- | ----- | 
| 1SG | Ya | Ya shoun | **Yem** (`Ya` + `em`) | Yeht | 
| 2SG/PL formal | Su | Su shoun | Su doun | Su geht | 
| 2SG/PL informal | Ben | Ben shoun | Ben doun | Ben geht | 
| 3SG masculine | Er | Er shoun | Er doun | Er geht | 
| 3SG feminine | She | She shoun | She doun | She geht | 
| 1PL | Yal | Yal shorn | Yalm | Yahlt | 
| 3PL | Dehye | Dehye shorn | Dehye dorn | Dehyt | 

#### 5.3a 1SG Present Portmanteau Rule (`Yem`)

* `Yem` represents the fused contraction of Subject (`Ya`) and 1SG Present Helper (`em`).

* **Strict Negative Constraint**: Generating `Ya yem` is grammatically invalid.

  * *Incorrect*: `Ya yem brauch ein key tu'den heim.`

  * *Correct*: `Yem brauch ein key tu'den heim.` ("I need a key to the home.")

## 6. Deterministic Negation Algorithm

```
IF Clause.HasDirectObject == TRUE:
  Verb_Syntax = Concatenate(ActionVerb, "-nu") + " " + DirectObject
ELSE:
  Verb_Syntax = ActionVerb + " nucht"

IF Clause.ContainsAbsoluteNegative ("alsitnu"):
  Suppress(Verb_Syntax.Negation)
```

### 6.1 Examples

* Intransitive: `Yem spile nucht.` ("I am not playing.")

* Transitive: `Yem spilenu Roblox.` ("I am not playing Roblox.")

* Absolute Negative Override: `Ya alsitnu iz apeleni.` ("I never eat apples.")

## 7. Semantic Bifurcation Engine

### 7.1 Referent Classification ("It" System)

When translating English "it", evaluate semantic category:

* **`Et`**: Abstract concepts, atmospheric conditions, weather, environmental states.

  * *Example*: `Et doun regen.` ("It is raining.")

* **`Es`**: Tangible, concrete physical objects.

  * *Example*: `Dehyss doun es.` ("This is it.")

### 7.2 Spatial Coordinates ("There" System)

* **`Dah`**: Existential declaration of presence ("There is...").

* **`Daz`**: Specific physical coordinate or destination ("Go there").

## 8. Interrogative System Rules

### 8.1 Fronted WH-Phrases (`Seckeh`)

For standard WH-questions, select the exact domain compound and place at index 0:

| Target Meaning | Syntactic Form | 
| ----- | ----- | 
| when | `Seckeh zeit` | 
| who | `Seckeh penk` | 
| why | `Seckeh prichin` | 
| where | `Seckeh plas` | 
| what | `Seckeh` | 

### 8.2 Terminal How-Marker (`Schalowit`)

* `Schalowit` is reserved exclusively for "how".

* **Strict Rule**: `Schalowit` MUST appear as the final token of the sentence before terminal punctuation.

* *Incorrect*: `Schalowit Ben doun?`

* *Correct*: `Ben doun Schalowit?`

### 8.3 Interrogative Register Matrix

| Type | Formal Syntax | Informal Syntax | 
| ----- | ----- | ----- | 
| WH-Question | `[WH phrase] chez [Clause]?` | `[WH phrase] [Clause]?` | 
| Yes/No | `chez [Clause]?` | `[Clause]?` | 
| How-Question | `chez [Clause] Schalowit?` | `[Clause] Schalowit?` | 

## 9. Morphological Algorithms for AI Processing

### 9.1 Nominalization (`-zung`)

```
FUNCTION Nominalize(verb):
  IF TerminalChar(verb) IN ['e', 't', 'z', 'x', 'd', 'r', 'a', 'i']:
    RETURN Slice(verb, 0, -1) + "zung"
  ELSE:
    RETURN verb + "zung"
```

### 9.2 Agent Derivation (`-mann`)

```
FUNCTION DeriveAgent(verb):
  RETURN verb + "mann"
```

### 9.3 Pluralization Engine

```
FUNCTION Pluralize(noun):
  IF EndsWith(noun, "zung"):
    RETURN ReplaceEnd(noun, "zung", "zeng")
  ELSE IF Contains(noun, "'"):
    RETURN noun + "eni"
  ELSE IF EndsWith(noun, "e") OR EndsWith(noun, "n"):
    RETURN Slice(noun, 0, -1) + "eni"
  ELSE:
    RETURN noun + "eni"
```

### 9.4 Compound Noun Generation ("Mash-Up")

```
FUNCTION CreateCompound(nounA, nounB):
  Prefix = nounA
  IF StartsWith(nounB, ConsonantCluster[length >= 2]):
    Suffix = Slice(nounB, 2, End)
  ELSE:
    Suffix = Slice(nounB, 1, End)
  RETURN Prefix + "'" + Suffix
```

### 9.5 Verb Prefix Engine (Inseparable)

Verb prefixes express aspectual phase or modification. They stay strictly glued to the verb stem and do **NOT** detach or shift to clause end.

| Prefix | Aspect / Function | Base Example | Prefixed Form | Translation Example |
| ----- | ----- | ----- | ----- | ----- |
| `an-` | Inchoative (Onset / Start) | `gehk` (go) | `angehk` | `Yem angehk.` ("I set off.") |
| `wieder-` | Iterative / Excess (Redo / Over-) | `mek` (make) | `wiedermek` | `Er shoun wiedermek den task.` ("He remade the task.") |
| `aus-` | Completion / Thoroughness | `trink` (drink) | `austrink` | `Su geht austrink den wasser.` ("You will finish drinking the water.") |

```
FUNCTION ApplyVerbPrefix(prefix, verb):
  RETURN prefix + verb
  // Note: Prefix remains directly attached to verb root in all clause types
```

### 9.6 Noun Prefix Engine

Noun prefixes modify entity scope, negation, status, or collectivity.

| Prefix | Semantic Function | Base Example | Prefixed Form | Translation Example |
| ----- | ----- | ----- | ----- | ----- |
| `un-` | Negation / Antonym Noun | `ruhig` (peace) | `unruhig` | `Dah doun unruhig.` ("There is unrest.") |
| `urz-` | Origin / Arch- / Primeval | `konig` (king) | `urzkonig` | `Den urzkonig shoun bau den kastelv.` ("The high king built the castle.") |
| `sam-` | Collective / Co- / Teammate | `Spilemann` (player) | `samspilemann` | `Yem brauch ein samspilemann.` ("I need a teammate.") |
| `vse-` | Total Inclusion ("Every [Noun]") | `spilzung` (game) | `vsespilzung` | `Yem spile vsespilzung.` ("I play every game.") |

```
FUNCTION ApplyNounPrefix(prefix, noun):
  RETURN prefix + noun
```

## 10. Algorithmic Number Generation System

Do not query the dictionary for composite numbers. Execute the following generation logic:

### 10.1 Base Digits & Tens

* Digits: 1=`Ein`, 2=`Biein`, 3=`Trein`, 4=`Vein`, 5=`Funein`, 6=`Sein`, 7=`Xsein`, 8=`Achein`, 9=`Nein`.

* Tens Rule: Append `-ik` to base digit (e.g., 10 = `Einik`, 20 = `Bieinik`).

### 10.2 Number Compounding Algorithm

* Join tens and units with `n` ("and").

* **Phonetic Nine Mutation**: If compound sequence ends in 9, mutate `nein` to `jein`.

  * Example (21): `Bieinik n Ein`

  * Example (29): `Bieiniknjein`

## 11. Proper Name & Slang Preservation Protocol

1. **Entities to Preserve Verbatim**:

   * People, brand names, software, games, products, fictional characters, specific geographical landmarks.

   * *Example*: "Roblox", "Microsoft", "John".

2. **Entities Requiring Translation/Dictionary Lookup**:

   * Country names, national languages, demonyms, major international cities, continents.

3. **Slang Processing Rule**:

   * For casual register inputs, map raw English slang to designated Schalowitsk slang roots or 2000s-era equivalents. Never leave unparsed raw English slang in the final translation.

## 12. Strict AI Output Audit Checklist

Prior to outputting any translation, the AI model **MUST** validate against these negative constraints:

* \[ \] **NO** `Ya yem` double-subject-helper sequences. Must be `Yem`.

* \[ \] **NO** double helpers generated (e.g., `doun doun`).

* \[ \] **NO** separated verb prefixes placed at sentence end (e.g., must be `angehk`, not `gehk ... an`).

* \[ \] **NO** V2 order violations when time/adverbial phrases are fronted in main clauses.

* \[ \] **NO** non-final helpers in subordinate clauses (`wehn`, `darum`, `whilst`).

* \[ \] **NO** `-ing` continuous suffixes or aspectual verb markers.

* \[ \] **NO** adverbial suffixes added to adjectives (e.g., `kvikly` $\rightarrow$ `kvik`).

* \[ \] **NO** standard English possessive apostrophes (`'s`) remaining (use `av` or `av-`).

* \[ \] **NO** `Seckeh` used for "how" questions.

* \[ \] **NO** `Schalowit` placed anywhere except at sentence termination.

* \[ \] **NO** double negatives generated in a single clause.

* \[ \] **NO** verb inflections generated for person or tense.