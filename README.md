# Flashcards Plugin for Claude Code

Create high-quality spaced repetition flashcards directly from Claude Code, saved to [Mochi](https://mochi.cards/).

## Features

- **Smart flashcard generation**: Uses proven spaced repetition principles to create cards that build genuine understanding, not rote memorization
- **Mochi integration**: Automatically saves flashcards to your Mochi decks via MCP

## Installation

### Prerequisites

- [Claude Code](https://code.claude.com) v1.0.33 or later
- A [Mochi](https://mochi.cards/) account with an API key

### Install the plugin

```bash
/plugin install <marketplace-url>
```

### Configure your Mochi API key

Set the `MOCHI_API_KEY` environment variable with your Mochi API key. You can find your API key in Mochi under Settings → API.

## Usage

Simply ask Claude to create flashcards on any topic:

```
Create flashcards about photosynthesis
```

```
Help me learn about the MCP protocol
```

Claude will:
1. Generate high-quality flashcard candidates
2. Present them for your review
3. Ask which cards you'd like to create
4. Save selected cards to your Mochi deck

## Flashcard Quality

The plugin follows five core properties for every card:

1. **Focused**: One atomic piece of knowledge
2. **Precise**: Unambiguous question with clear answer
3. **Consistent**: Same question → same answer every time
4. **Tractable**: Answerable in ~5 seconds with effort
5. **Effortful**: Requires genuine recall, not recognition

## License

MIT
