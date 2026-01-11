---
name: write-flashcards
description: Write spaced repetition flashcards using prompt-writing best practices. ALWAYS invoke when users want to create flashcards, study material, or memorize concepts.
---
This skill guides creation of high-quality spaced repetition flashcards that produce genuine understanding, not rote memorization. 

The user provides material to learn: text, concepts, procedures, or asks for help studying a topic. They may include context about why they're learning this or how they'll use it.

## Prompt Design Thinking

Before writing cards, understand what "knowing" this material actually means:

- **Purpose**: Why does the user want to remember this? How will they use it?
- **Knowledge type**: Is this facts, procedures, concepts, or open-ended patterns?
- **Connections**: How does this connect to things they already know?
- **Gaps**: What would someone need to understand to truly "know" this?

**CRITICAL**: A flashcard is a task you give your future self. Design tasks that produce the understanding you want—not tasks that can be gamed through pattern matching.

## The Five Properties of Effective Prompts

Every card must satisfy these properties. If a card fails any of them, rewrite it.

1. **Focused**: One atomic piece of knowledge. Too much detail dilutes retrieval and produces incomplete recall. If you can break it down further, do so.
2. **Precise**: Unambiguous questions with clear answers. Vague questions produce vague answers that don't reinforce the target knowledge. "What's the first step?" fails—first step of what, in what context?
3. **Consistent**: Same question → same answer, every time. Inconsistent answers cause retrieval-induced forgetting: what you recall is reinforced, but related knowledge you *didn't* recall is inhibited.
4. **Tractable**: Answerable with reasonable effort. If you consistently fail a card, break it into smaller pieces or add cues. Aim for ~90% success rate.
5. **Effortful**: Requires genuine retrieval from memory. Don't give away the answer through obvious cues or pattern matching. Effort drives learning.

## Knowledge Type Strategies

### Simple Facts

Direct Q→A format. Add explanation prompts when the "why" is interesting or aids memory:

```
Q: What type of chicken parts are used in stock?
A: Bones

Q: Why are bones used to make chicken stock?
A: They're full of gelatin, which produces rich texture
```

The explanation makes the fact meaningful and provides hooks for future connections.

### Lists (Closed)

Never ask "List all X"—it's unfocused and produces inconsistent retrieval. Use cloze deletions groups:

```
Q: Chicken stock aromatics: {{1::onion}}, {{2::carrots}}, {{3::celery}}, {{4::garlic}}, {{5::parsley}}
```

Keep list order consistent—you'll learn the visual "shape." Consider adding explanation prompts for *why* each item belongs.

### Lists (Open)

Open lists (like "ways to use chicken stock") can't use cloze deletion—any answer could fit. Instead:

1. **Link instances to the tag**: "When puréeing vegetables for soup, how can I add richness without fat?" → "Use chicken stock instead of water"
2. **Link tag to instances** (fuzzy): "Name two ways you might use chicken stock" → "e.g., cooking grains, steaming greens, making soup, deglazing pans"
3. **Creative prompts**: "Name a vegetable soup you might make with chicken stock (give an answer you haven't given before)"—these leverage the generation effect rather than retrieval.

### Procedures

Don't memorize steps verbatim. Extract the **keywords** that carry meaning:

- Key verbs and transitions: "When should you lower the heat?" → "After reaching a simmer"
- Important modifiers: "At what speed should you heat chicken stock?" → "Slowly"
- Timing/conditions: "How long must chicken stock simmer?" → "90 minutes"
- Explanations: "Why heat chicken stock slowly?" → "Produces brighter, cleaner flavor"

Skip obvious steps (combining ingredients in a pot) and focus on what's actually worth remembering.

### Concepts

Concepts require multiple cards from different angles. Use these lenses:

- **Attributes**: What makes X, X? What's always/sometimes/never true?
- **Comparisons**: How is X different from Y? Similar to Z?
- **Parts/wholes**: Examples of X? Is X part of something broader?
- **Causes/effects**: What does X do? What causes it? When is it used?
- **Significance**: Why does X matter? What does it imply for behavior?

```
Q: How is stock different from soup broth?
A: Broth has complete flavor; stock is a building block, not meant to stand alone

Q: What liquid explains why restaurant dishes often taste richer than home versions?
A: Stock (used where home cooks use water)
```

## Anti-Patterns to Avoid

**NEVER** write cards that exhibit these patterns:

- **Binary questions**: "Is X true?" → Rephrase as "Why is X the case?" or "What happens when X?"
- **Pattern-matchable**: Long questions with unusual words let you memorize the shape, not the knowledge
- **Front-loaded answers**: Don't put hints in the question that give away the answer
- **Passive recognition**: "X is called ___" → Flip it: "What is the term for [definition]?"
- **Orphan knowledge**: Always connect to broader context or personal meaning
- **Exhaustive coverage**: Don't write prompts about everything—focus on what matters to the user

## Elaborative Encoding

When knowledge seems arbitrary or hard to remember, create associations:

```
Q: Chicken stock aromatics: onion, {{Carrots (rhymes with "parrots"—picture parrots dropping carrots into a pot)}}, celery, garlic, parsley
```

Vivid, personal, or emotional associations stick better. Put mnemonics in the answer (in parentheses) so the focus remains on recall.

## Workflow

### Step 1: Understand the Material

- What would it mean to truly "know" this?
- What's essential vs. trivial?
- What knowledge types are involved?
- How does this connect to the user's goals?

### Step 2: Draft Cards

Present cards clearly:

```
**1.** Q: [Question]
    A: [Answer]

**2.** Q: [Question]
    A: [Answer]
```

Write MORE cards than feels natural—prompts are cheaper than you think (~10-30 seconds over the first year). But don't write cards about things the user already knows or doesn't care about.

### Step 3: User Selection

After presenting cards:

> Which cards would you like to create? (e.g., "1, 3, 5" or "all" or "all except 2")

## Quality Checklist

Before proposing each card:

- Tests ONE thing (focused)
- Question is unambiguous (precise)
- Answer won't vary by context (consistent)
- Can be answered in ~5 seconds with effort (tractable)
- Requires genuine recall, not recognition (effortful)
- Connected to something meaningful (not orphaned)

## Example Interaction

**User**: "Help me learn about photosynthesis"

**Response**:

Here are flashcards covering photosynthesis fundamentals. I've focused on the core mechanism and its significance rather than exhaustive details:

**1.** Q: What problem does photosynthesis solve for plants?
    A: Converting light energy into chemical energy they can use (glucose)

**2.** Q: What are the two inputs that photosynthesis combines?
    A: Carbon dioxide (CO₂) and water (H₂O)

**3.** Q: What organelle contains the machinery for photosynthesis?
    A: Chloroplast

**4.** Q: Why are plants green?
    A: Chlorophyll reflects green light while absorbing red and blue for photosynthesis

**5.** Q: What gas do plants release that animals depend on?
    A: Oxygen (O₂)—a "waste product" of photosynthesis

**6.** Q: Where in the chloroplast do light-dependent reactions occur?
    A: Thylakoid membranes (stacked discs that maximize surface area for light capture)

**7.** Q: Where does the Calvin cycle build glucose molecules?
    A: Stroma (the fluid surrounding the thylakoids)

**8.** Q: Why is photosynthesis considered the foundation of most food chains?
    A: It converts solar energy into chemical energy that flows through all consumers

Which cards would you like to create? What deck should I add them to?

---

Remember: The goal is understanding that persists and transfers to real situations—not the ability to parrot answers. Write cards that would make your future self grateful, not annoyed.