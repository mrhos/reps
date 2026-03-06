# REPS — Color Tokens

## Theme Tokens (`T` object)

These are the tokens referenced throughout the app as `T.tokenName`.
Both modes must define all tokens. To redesign, replace the values in the Light column.

| Token     | Role                                      | Dark            | Light (current) |
|-----------|-------------------------------------------|-----------------|-----------------|
| `bg`      | Page background                           | `#0A0A0A`       | `#FBFBE7`       |
| `card`    | Card / panel background                   | `#141414`       | `#F0EDE2`       |
| `card2`   | Nested card / input background            | `#1C1C1C`       | `#E7DFD6`       |
| `border`  | Card borders, dividers                    | `#242424`       | `#D2C8BA`       |
| `border2` | Stronger border (inputs, active states)   | `#2E2E2E`       | `#C5BAB0`       |
| `lime`    | Primary accent — CTAs, active states      | `#C8FF00`       | `#3DAA95`       |
| `limeDim` | Lime tint background (banners, badges)    | `rgba(200,255,0,0.12)` | `rgba(61,170,149,0.12)` |
| `red`     | Destructive actions, errors               | `#FF3B30`       | `#E8341F`       |
| `redDim`  | Red tint background                       | `rgba(255,59,48,0.12)` | `rgba(232,52,31,0.10)` |
| `white`   | Primary content text / high-contrast text | `#FFFFFF`       | `#1A1A1A`       |
| `text`    | Body text (also used for CSS var)         | `#FFFFFF`       | `#1A1A1A`       |
| `dim`     | Secondary / muted text                    | `#777777`       | `#877A6C`       |
| `muted`   | SVG strokes, empty state icons            | `#3A3A3A`       | `#C5BAB0`       |
| `navBg`   | Bottom nav bar background (blur overlay)  | `rgba(14,14,14,0.95)` | `rgba(251,251,231,0.95)` |

> **Note:** `white` and `text` are the same value in both themes.
> `white` is used on coloured backgrounds (red buttons etc.) — keep it legible on those surfaces.
> `limeDim` / `redDim` should match their base colour at low opacity.

---

## Muscle Group Colours (`MG` object)

These are fixed — they don't change between dark and light mode.
Used for the left border accent on exercise cards and section headers.

| Muscle Group | Colour      | Hex       |
|--------------|-------------|-----------|
| Chest        | Coral red   | `#FF6B6B` |
| Back         | Teal        | `#4FC4CF` |
| Shoulders    | Yellow      | `#FFD93D` |
| Biceps       | Soft purple | `#A29BFE` |
| Triceps      | Indigo      | `#818CF8` |
| Quads        | Pink        | `#F472B6` |
| Hamstrings   | Orange      | `#FB923C` |
| Glutes       | Deep orange | `#F97316` |
| Calves       | Mint green  | `#34D399` |
| Core         | Sky blue    | `#60A5FA` |
| Full Body    | Slate       | `#94A3B8` |

---

## How to apply a redesign

1. Edit the values in the **Light** column of the theme tokens table above
2. Update `T_LIGHT` in `workout.html` to match — the structure is:

```js
const T_LIGHT = {
  bg:      '...',
  card:    '...',
  card2:   '...',
  border:  '...',
  border2: '...',
  lime:    '...',
  limeDim: '...',   // base lime colour at ~12% opacity
  red:     '...',
  redDim:  '...',   // base red colour at ~10% opacity
  white:   '...',
  dim:     '...',
  muted:   '...',
  text:    '...',   // same as white
  navBg:   '...',   // base bg colour at ~95% opacity
};
```

3. Also update the anti-flash init script near the top of `workout.html`
   (the inline `<script>` before the React CDN tag) to match the new `bg`, `text`, `card`, and `lime` values.
