# Surprise Site

A password-protected, single-page interactive website designed as a fun way to ask someone on a date and let them pick the details. Built as a single HTML file with no dependencies — just open it in a browser.

## Features

- Password-gated entry with show/hide toggle
- Playful "date ask" page with a trick No button and spongebob popup
- Customizable poem display
- Dynamic date picker showing the next upcoming weekend (Friday-Sunday)
- Time slot selection from 5:00 PM to 10:00 PM in 30-minute increments
- Food and activity preference selection via emoji buttons
- One-tap copy to clipboard for easy sharing
- "Change Choices" option to redo selections
- Fully responsive — works on iPhones, iPads, and desktop browsers
- Dark themed UI with smooth page transitions

## Page Flow

| Step | Page | Description |
| --- | --- | --- |
| 1 | **Secret Code** | Visitor enters a password to unlock the site. A peeking eye emoji toggle lets them show/hide what they typed. Wrong codes get a "Wrong code, try again!" message. |
| 2 | **Date Ask** | Asks "Do you want to go on a date with me?" with two buttons. **Yes** (right, green) advances to the poem. **No** (left, gray) triggers a popup with a spongebob "teehee" image and the message "Oops, wrong button teehee" with a Go Back button. |
| 3 | **Poem** | Displays a customizable poem with a "Next" button to continue. |
| 4 | **Pick a Day and Time** | Shows the next upcoming Friday, Saturday, and Sunday as selectable day buttons with formatted dates. After selecting a day, a grid of time slots (5:00 PM through 10:00 PM in 30-min increments) becomes active. |
| 5 | **Food Selection** | Six food emoji buttons in a 3-column grid: tacos, sushi, empanada, hamburgers, pasta, and ice cream. Clicking one records the choice and advances. |
| 6 | **Activity Selection** | Four activity emoji buttons in a 2-column grid: movies, books, games, and paint. Clicking one records the choice and advances. |
| 7 | **Thank You** | Displays "Thank you! Copy and paste into chat" with a **Copy Results** button and a smaller **Change Choices** button to go back to the day/time picker. |

## Clipboard Output

When the visitor clicks "Copy Results", the following is copied to their clipboard:

```
Date: Friday, Jun 20
Time: 7:00 PM
Food: tacos
Activity: movies
```

The clipboard copy uses the modern Clipboard API with a textarea fallback for older iOS Safari versions.

## Customization

Open `index.html` and edit these values in the `<script>` block:

| What | Where | Default |
| --- | --- | --- |
| Password | `const PASSWORD = "letmein";` | `letmein` |
| Poem text | `<div class="poem" id="poemText">POEM</div>` | `POEM` |

Use `<br>` tags for line breaks in the poem, or place text on multiple lines within the div.

## Tech Stack

- **Single HTML file** — no build tools, frameworks, or external dependencies
- **Vanilla JavaScript** — all logic is inline, no modules or libraries
- **CSS custom properties** — dark theme with `--bg`, `--card`, `--accent`, `--text`, `--muted` variables
- **CSS Grid & Flexbox** — responsive layouts that adapt to mobile screens
- **Clipboard API** — with `document.execCommand('copy')` fallback for compatibility

## Usage

Open `index.html` in any browser. No server, build step, or installation required. The spongebob image on the "Oops" popup loads from Pinterest, so an internet connection is needed for that image to display.

## Compatibility

Works on Safari (iPhone/macOS), Chrome, Firefox, and Edge. The layout uses `100dvh` for proper mobile viewport handling and `-webkit-tap-highlight-color: transparent` to remove tap highlights on iOS.
