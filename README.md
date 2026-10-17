# PAYBOY

A payment landing page built as a working Game Boy.

**Live:** https://bartlettdmarkel.github.io/payboy.brave/

Tap a tab, tap a row, and it copies an address or opens a payment link. The
D-pad, A/B, START and SELECT all work. The power switch on top flips the whole
thing from Game Boy green to a Miami-neon night mode, shell and all.

## Features

- **Four cartridges** — cash apps, crypto wallets, contact, and exchange sign-ups
- **Two themes** — DMG green (`#9bbc0f`) and a translucent atomic-grape night mode
  with a neon perspective grid, palm trees, and a striped sun
- **Working controls** — SELECT steps through the list, START opens what's
  selected, A confirms, B goes back, left/right change cartridges
- **Side volume wheel** — toggles the sound effects
- **Chiptune audio** — square and sawtooth blips synthesised live with the Web
  Audio API, including a cartridge-insertion sound on every tab change
- **Boot sequence** — the logo drops, the falling `$ ₿ 1 0` cascade plays, then
  the punchline lands
- **Haptic feedback** on copy, where the browser supports it

## Built with

Plain HTML, CSS, and JavaScript. No frameworks, no build step, no dependencies —
one file you can open by double-clicking it. Fonts are Press Start 2P and VT323.

Everything visual is CSS: the shell gradients, the dot-matrix screen overlay, the
pixel-art clouds drawn with `box-shadow`, the perspective grid via
`transform: perspective()`, and the cartridge glyphs rendered from ASCII strings
into CSS Grid. The only images are two inline SVG palm trees.

## Making it your own

Everything editable lives in the `CONFIG` object at the top of the `<script>`
block. Change the handles, addresses, and links there — nothing else needs
touching.

```js
const CONFIG = {
  email: "you@example.com",
  github: "https://github.com/yourname",
  deal: ["DEAL!! PAY 10% LESS", "IF PAID IN CRYPTO."],
  quip: "You owe me money?!",
  fiat: [ ... ],
  crypto: [ ... ],
  exchanges: [ ... ]
};
```

## Accessibility & compatibility

Keyboard playable: arrow keys, Enter/Z for A, X/Escape for B, Space for START,
S for SELECT, P for theme, M for sound. Every control is a real `<button>` with
an ARIA label, focus is visible throughout, and `prefers-reduced-motion` disables
all animation. Tested from 320px to 430px wide.

## Licence

MIT — take it, change it, ship your own.
