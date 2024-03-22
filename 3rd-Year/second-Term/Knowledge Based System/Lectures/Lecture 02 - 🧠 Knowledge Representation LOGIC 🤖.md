## Listen [here](https://youtu.be/dz3YnLhIMqg), [here](https://youtu.be/lmGvrDzEzes), [here](https://youtu.be/TDajfY9PCtA), [here](https://youtu.be/OrhrCYfTISU)
## Knowledge representation
Objective: express the knowledge about the world in a computer-tractable form

### Key aspects:
- **Syntax:** describes how sentences are formed in the language
- **Semantics:** describes the meaning of sentences, what it refers to in the real world

## Logic 🎩
One of the earliest formalisms for the representation of knowledge.
- Propositional logic
- First-order predicate logic.

### Propositional logic 🤔
A language to express and reason with statements that are either true or false.
- Statements are called propositions
- Simple propositions are called atoms or atomic propositions

#### EXAMPLES:
- It is raining today ☔
- Dr. Hatem is the dean 🎓
- whereas the following are not:
  - Are you going out somewhere? 🤔
  - 2+x=13 ❌

#### Logical Connectives:
- Negation: ¬ (not) 
- Conjunction: ∧ (and)
- Disjunction: ∨ (or)
- Implication: → (if then)
- Bi-Implication: ↔ (if and only if)

### Truth table:
|  p  |  q  | ¬p  | p ∧ q | p ∨ q | p → q | p ↔ q |
| :-: | :-: | :-: | :---: | :---: | :---: | :---: |
|  T  |  T  |  F  |   T   |   T   |   T   |   T   |
|  T  |  F  |  F  |   F   |   T   |   F   |   F   |
|  F  |  T  |  T  |   F   |   T   |   T   |   F   |
|  F  |  F  |  T  |   F   |   F   |   T   |   T   |

### Equivalence:
Two formulas F and G are called equivalent, written as F ≡ G,
if the truth values of F and G are the same under all possible interpretations.
i.e., their truth tables are identical.

## Laws of Equivalence 💡
1. **Identity Laws:**
   - $p \land \text{T} \equiv p$
   - $p \lor \text{F} \equiv p$

2. **Domination Laws:**
   - $p \lor \text{T} \equiv \text{T}$
   - $p \land \text{F} \equiv \text{F}$

3. **Idempotent Laws:**
   - $p \lor p \equiv p$
   - $p \land p \equiv p$

4. **Commutative Laws:**
   - $p \lor q \equiv q \lor p$
   - $p \land q \equiv q \land p$

5. **Associative Laws:**
   - $(p \lor q) \lor r \equiv p \lor (q \lor r)$
   - $(p \land q) \land r \equiv p \land (q \land r)$

### Propositional logic limitations 🚫
- Limited expressive power
- Assumes the world contains facts
- How to represent complex sentences?

## First-order logic 🚀
An extension to propositional logic.

### Symbols:
- **Punctuation:** "(", ")", and "."
- **Connectives:** "¬," "^," "v," "∃," "∀," and "="
- **Variables:** x, y, z, a, b, ...
- **Function symbols:** sqrt, LeftLegOf, ...
- **Predicate symbols:** Brother, Father, >, ...
- **Constants:** 1, 2, A, John, Mumbai, cat, ...

### Atomic sentences:
- Formed from a predicate symbol followed by a sequence of terms.
- Example: Brothers(Ravi, Ajay), Cat(Chinky)

### Complex Sentences:
- Made by combining atomic sentences using connectives.

### Function:
- Allows functions that return objects associated with other objects.
- Examples: MedianOf(x, y, z)

### Quantifiers:
- **Existential Quantifier:** ∃
  - Example: ∃m. (Muggle(m) ∧ Intelligent(m))
- **Universal Quantifier:** ∀
  - Example: ∀n. (n ∈ N → (Even(n) ↔ Even(n^2)))

### Variables and Quantifiers:
- Each quantifier has two parts:
  - The variable introduced
  - The statement being quantified
- The variable introduced is scoped just to the statement being quantified.

#### Example:
(∃x. Loves (You, x)) ∧ (∃y. Loves(y, You))
