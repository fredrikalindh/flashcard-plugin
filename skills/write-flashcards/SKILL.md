---
name: write-flashcards
description: Write spaced repetition flashcards. ALWAYS invoke when users want to create flashcards.
---

Create flashcards that produce genuine understanding, not rote memorization. A flashcard is a task for your future self—design tasks that build real knowledge, not pattern-matching.

## Five Properties (Every Card Must Pass)

1. **Focused**: One atomic piece of knowledge
2. **Precise**: Unambiguous question with clear answer
3. **Consistent**: Same question → same answer every time
4. **Tractable**: Answerable in ~5 seconds with effort
5. **Effortful**: Requires genuine recall, not recognition

**Answers must be concise**—a few words or a short phrase. Each card should only take a few seconds.

## Knowledge Type Strategies

**Facts**: Direct Q→A. Add "why" prompts when explanation aids memory.

```
Q: What chicken parts are used in stock? → A: Bones
Q: Why bones? → A: Full of gelatin, produces rich texture
```

**Closed Lists (finite)**: Use cloze deletions or cloze deletion groups, never "List all X". These don't need a back.

```
Q: Stock aromatics: {{1::onion}}, {{2::carrots}}, {{3::celery}}, {{4::garlic}}, {{5::parsley}}

Q: What are the three main types of capabilities an MCP server can expose?
{{1::Tools (executable functions)}}, {{2::Resources (data/context access)}}, and {{3::Prompts (reusable prompt templates)}}

```

**Open Lists**: Link instances to context rather than listing:

- "When puréeing soup, how add richness without fat?" → "Use stock instead of water"
- "Name two uses for stock" → "e.g., cooking grains, deglazing pans"

**Procedures**: Extract meaningful keywords, skip obvious steps:

- "When lower the heat?" → "After reaching a simmer"
- "Why heat stock slowly?" → "Brighter, cleaner flavor"

**Concepts**: Multiple cards from different angles:

- Attributes: What makes X, X?
- Comparisons: How is X different from Y?
- Causes/effects: What does X do? What causes it?
- Significance: Why does X matter?

## Anti-Patterns

- **Binary**: "Is X true?" → "Why is X the case?"
- **Pattern-matchable**: Long questions with unusual words
- **Front-loaded**: Hints in question that give away answer
- **Passive recognition**: "X is called ___" → "What is the term for [definition]?"
- **Orphan knowledge**: Always connect to broader context
- **Exhaustive**: Focus on what matters, not everything

## Workflow

1. **Understand**: What would it mean to truly "know" this? What's essential?
2. **Draft**: Present cards clearly, write more than feels natural:

```
**1.** Q: [Question]
    A: [Answer]
```

1. **Select**: Ask user which cards to create (e.g., "1, 3, 5" or "all except 2")

## Example

**User**: "Help me learn about photosynthesis"

**1.** Q: What problem does photosynthesis solve for plants?
    A: Converting light energy into chemical energy (glucose)

**2.** Q: What two inputs does photosynthesis combine?
    A: CO₂ and H₂O

**3.** Q: What organelle performs photosynthesis?
    A: Chloroplast

**4.** Q: Plants are green because of {{chlorophyll}}

**5.** Q: What "waste product" of photosynthesis do animals depend on?
    A: Oxygen (O₂)

**6.** Q: Why is photosynthesis the foundation of most food chains?
    A: Converts solar energy into chemical energy that flows through all consumers

**7.** Q: What does adaptive bitrate streaming continuously monitor to make quality decisions? {{1::Available bandwidth}}, {{2::packet loss rate}}, {{3::buffer status (remaining video to play)}}, and {{4::CPU/device capabilities}}

Which cards would you like to create?