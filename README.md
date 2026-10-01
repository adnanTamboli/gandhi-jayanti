# Walk with Bapu — a Gandhi Jayanti scroll tribute

A single `index.html` that uses Three.js r160 from a CDN. There is no build step.

Scroll story:
1. A tribute note: an illustration only, with no denomination and no currency marks.
2. Bapu rises out of the portrait window in golden sparks: "My life is my message."
3. He walks a khadi path, leaving footprints. Sourced quotes pop up as paper slips.
4. The sky moves from dawn to sunset, and the sun is a spinning charkha.
5. He reaches the sea (a nod to Dandi), turns and raises his hand, while tricolour particles rise.

Bapu himself is hand-drawn. The user generated AI clips on green screen; they were keyed with ffmpeg into transparent WebP sprite sheets in `media/`, and scroll picks the frame:
- `rise.webp`: 6×6 frames. The portrait comes to life out of the paper (scrubbed for p 0.05–0.27).
- `walk.webp`: 7×5 frames. A seamless two-step loop, source frames 20–54; the frame follows the distance walked (1.5 m per loop).
- `wave.webp`: 8×4 frames. Seen from behind, he turns and waves (scrubbed for p 0.875–0.965).

The original clips and the keying script are in `_src/`, which is gitignored. The key is `chromakey=0x14C21E:0.16:0.08,despill=green`.

- Run it locally with `python -m http.server` in this folder, then open http://localhost:8000.
- The ♪ button plays a soft tanpura-like drone (Sa–Pa). It is off by default.
- Reduced-motion users get the scroll position without easing.
- Quotes and their sources are in the `QUOTES` array. Popular "Gandhi quotes" that are misattributed were left out on purpose.
