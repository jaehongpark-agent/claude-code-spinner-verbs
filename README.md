# Claude Code Spinner Words

Ever wondered what those quirky loading messages in [Claude Code](https://docs.anthropic.com/en/docs/claude-code) are?

This tool extracts all spinner words from the Claude Code CLI binary and saves them as versioned markdown files for history tracking.

> [Korean (한국어)](README_KR.md)

## How It Works

1. Locates the Claude Code binary on your system
2. Runs `strings` to dump printable text from the binary
3. Uses seed-based bootstrapping to find the spinner word array — known rare words (e.g. *Flibbertigibbeting*, *Razzmatazzing*) pinpoint the right location
4. Parses out all gerund-form words and saves them to `words/<version>.md`
5. Shows a diff against the previous extraction, so you can spot additions and removals across versions

## Usage

```bash
python3 extract_spinner_words.py
```

Output example:

```
Binary:  /Users/you/.local/share/claude/versions/2.1.63
Version: 2.1.63
Seeds:   192 words (12 built-in)
Running strings...

Extracted 192 spinner words:

    1. Accomplishing
    2. Actioning
    3. Actualizing
  ...
  192. Zigzagging

Saved to words/2.1.63.md
```

## Requirements

- Python 3.10+
- Claude Code CLI installed
- `strings` command available (pre-installed on macOS/Linux)

## Project Structure

```
.
├── extract_spinner_words.py   # Main extraction script
└── words/
    └── 2.1.63.md              # Extracted words by version
```

## Sample Words

Some highlights from the 192 spinner words found in v2.1.63:

| | | | |
|---|---|---|---|
| Beboppin' | Flibbertigibbeting | Razzmatazzing | Discombobulating |
| Canoodling | Lollygagging | Shenaniganing | Tomfoolering |
| Clauding | Flambéing | Sautéing | Prestidigitating |
| Moonwalking | Spelunking | Hullaballooing | Whatchamacalliting |

## License

MIT
