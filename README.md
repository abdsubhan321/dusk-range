# Dusk Range

A twilight archery game that runs in the browser. Draw the bow, read the wind, and use twelve arrows to hit wooden target boards and drifting paper lanterns.

**Play it:** `https://abdsubhan321.github.io/dusk-range/`

## How to play

- **Draw:** press and drag back anywhere on the field, away from where you want to shoot. Drag further for more power.
- **Aim:** the dotted arc shows your flight path but ignores the wind. Use the flag and the m/s reading in the top right to correct for it.
- **Loose:** release to shoot.

### Keyboard

| Key | Action |
| --- | --- |
| Up / Down arrows | Raise or lower the aim angle |
| Hold Space | Draw the bow |
| Release Space | Shoot |

## Scoring

- Target rings are worth 1 to 10 points, with 10 in the center.
- A gold hit (9 or 10) returns one arrow to your quiver.
- A lantern is worth 25 points.
- Every three hits in a row raises your multiplier, up to x4. A miss resets it.
- The round ends when you run out of arrows. Your best score is saved in your browser.

The game gets harder as you hit more targets: boards shrink, more of them swing on poles, and the wind gets stronger.

## Run locally

There is no build step and no dependencies. Open `index.html` in a browser.

If you prefer a local server:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Deploy with GitHub Pages

1. Push `index.html` to the root of your repository.
2. In the repository, open **Settings > Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select your main branch and the `/ (root)` folder, then save.
4. After a minute or two the game is live at `https://abdsubhan321.github.io/dusk-range/`.

## Tech notes

- A single HTML file with inline CSS and JavaScript, drawn on an HTML canvas.
- Scenery (sky, mountains, trees, mist) is pre-rendered once and redrawn on resize. Arrow flight uses a small physics step with gravity and wind.
- Sound effects are generated with the Web Audio API, so there are no audio files. Sound starts after your first tap or click and can be toggled in the corner.
- Fonts (Big Shoulders Display and Hanken Grotesk) load from Google Fonts. The game still works offline with fallback fonts.
- Works with mouse, touch, and keyboard, and adapts to phone and desktop screens. Screen shake is turned off if your device asks for reduced motion.

## License

Add a `LICENSE` file to choose how others may use this project. MIT is a common choice for small games.
