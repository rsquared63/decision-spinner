# Roundabout

A browser-only decision spinner. Open `index.html` to play, or host it with GitHub Pages. No dependencies, build step, accounts, or API keys.

- Up to 30 unique options, with equal probability per option
- Dinner, movie night, and weekend starters
- Named lists and recent picks stored in this browser
- No-repeat rounds: every option wins once before the round resets
- Keyboard support and reduced-motion support

## Publish on GitHub Pages

1. Create a public GitHub repository, such as `decision-spinner`.
2. Upload `index.html` to the root of its `main` branch.
3. In the repository, open **Settings → Pages**.
4. Select **Deploy from a branch**, then **main** and **/ (root)**. Save.
5. GitHub Pages will display the published URL when deployment finishes.

Lists are saved locally per browser and website address. They do not sync between devices or between the local preview and GitHub Pages.

## Local preview

Run `python3 -m http.server 8765` in this folder, then open `http://localhost:8765`.

## How selection works

The spinner chooses a random option using `crypto.getRandomValues` with rejection sampling, then animates to the matching wheel segment. Long labels are shortened on the wheel; the full winning label appears beneath it. Extra options past the first 30 unique entries are ignored.
