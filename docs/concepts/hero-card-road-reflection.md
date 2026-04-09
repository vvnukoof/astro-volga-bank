# Concept: "The Road Reflection" — Hero Card Element

## Visual

The card surface is glossy black — not matte gradient, but a reflective surface like polished obsidian or a car's fresh wax finish. The key trick: the card has a real-time reflection of the road/atmosphere behind it. Technically, this is a pseudo-element with the same `volga-bg.png` background but heavily blurred (`blur(20px)`), desaturated, and at 8-10% opacity, clipped to the card shape and offset slightly. As the user scrolls (parallax), this reflection layer shifts position subtly — the card "reflects" its environment. The card text and chip sit on top. A single diagonal specular highlight (thin, white, 6-8% opacity) runs from top-left to mid-right — like a window reflection on a car hood.

## Animation

1. At 450ms, the card appears via a vertical split-reveal: imagine two invisible shutters (top half and bottom half of the card area) that slide apart vertically, revealing the card behind them. This is achieved by clip-path animation — `inset(50% 0)` to `inset(0)` over 500ms. The card is already in position but hidden by the clip.
2. At 900ms, the specular highlight slides diagonally across the card surface (translate from bottom-left to top-right), 600ms — like turning a card in your hand and catching the light.
3. Idle: the reflection layer shifts with scroll parallax (0.05x factor — very subtle). On mouse hover (desktop), the card tilts toward the cursor (subtle `rotateX/rotateY` based on mouse position, max 5deg) — the reflection shifts accordingly. This is the "hold the card in your hand" moment.

## Relationship with Hero

The card literally contains the hero's atmosphere inside it — the Volga, the road, the sky are all reflected in its surface. It's not a separate element pasted into the layout; it's an object existing within the scene. The parallax reflection ties it to the scroll narrative. The "11%" on the left is the promise; the card on the right is the physical proof.

## Premium Factor

Interactive tilt-to-cursor is the Stripe/Revolut card trick, but the reflection layer makes it uniquely ours — it's a card that belongs to THIS brand because it reflects THIS world. The split-reveal entrance is uncommon and arresting. Nobody scrolls past a surface that responds to their mouse.
