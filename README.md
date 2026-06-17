# Surprise Site

A password-protected, single-page website that walks visitors through a short interactive flow.

## How It Works

1. **Password screen** - Visitor enters a code to unlock the site. A show/hide eye toggle lets them peek at what they typed.
2. **Poem page** - Displays a poem (customizable in the code). A "Next" button advances to the next step.
3. **Food selection** - Six food emoji buttons (tacos, sushi, empanada, hamburgers, pasta, ice cream). The visitor's choice is recorded.
4. **Activity selection** - Four activity emoji buttons (movies, books, games, paint). The visitor's choice is recorded.
5. **Thank you page** - Shows a "Copy Results" button. Clicking it copies the selections to the clipboard so the visitor can paste them into a chat.

Copied output looks like:

```
Food: tacos
Activity: movies
```

## Customization

Open `index.html` and edit these values near the top of the `<script>` block:

| What | Where | Default |
| --- | --- | --- |
| Password | `const PASSWORD = "letmein";` (line ~150) | `letmein` |
| Poem text | `<div class="poem" id="poemText">POEM</div>` (line ~135) | `POEM` |

Use `<br>` for line breaks in the poem.

## Usage

Open `index.html` in any browser. No server, build step, or dependencies required.

## Compatibility

Tested on Safari (iPhone/macOS), Chrome, Firefox, and Edge. Uses the Clipboard API with a textarea fallback for older iOS Safari.
