# Dinsical

Dinsical os the main font used in [Whimsical whiteboard app](https://whimsical.com/).

It is a variable font derived from [DINish](https://github.com/playbeing/dinish) (itself a fork of Altinn-DIN / 
D-DIN).

## Glyphs

![](../images/dinsical@2x.png)

## Language support

Dinsical supports 243 Latin-based languages, full European Latin coverage, Cyrillic
(Russian, Bulgarian, Serbian), old-style numerals, and proportional/tabular
figure styles.

## Variable font axes

| Axis | Tag | Range |
|---|---|---|
| Weight | `wght` | 300 (Light) – 900 (Black) |
| Slant | `slnt` | 0 (upright) – −10 (italic) |

Static instances: Light, Regular, Medium, SemiBold, Bold, Heavy, Black
(+ Italic variants of each).

## OpenType features

By default, Dinsical uses **lining tabular figures**.

To opt into proportional lining figures, use:

```css
font-variant-numeric: proportional-nums;
```

Or equivalently:

```css
font-feature-settings: "pnum" 1;
```

| Feature | Description |
|---|---|
| default | Lining tabular figures |
| `pnum` | Proportional lining figures |
| `tnum` | Tabular figures (explicitly re-enable the default if needed) |
| `onum` | Old-style numerals |
| `frac` | Diagonal fractions |
| `ss01` | Stylistic set 1 (Dutch IJ) |
| `ss02` | Alternate `a` (activated automatically in italics) |

## Font metrics

| Metric | Value |
|---|---|
| UPM | 1000 |
| hhea ascender / descender / lineGap | 830 / −170 / 200 |
| sTypo ascender / descender / lineGap | 750 / −250 / 200 |
| OS/2 WinAscent / WinDescent | 850 / 350 |
| **Line height @ 100 px** | **120.000 px** |

## License

SIL Open Font License, Version 1.1 — see [OFL.txt](../OFL.txt).

Copyright © 2026 Whimsical, Inc.

Copyright © 2023–2024 Stefan Peev  

Copyright © 2021–2025 Bert Driehuis  

Copyright © 2019 Altinn  

Copyright © 2017 Datto Inc.
