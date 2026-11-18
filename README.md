# Pompiere

The sources in `sources/` were converted from the fonts Google Fonts ships
with [babelfont-rs](https://github.com/felipesanches/babelfont-rs/tree/2026-11-02), and build with
[gftools-builder](https://github.com/simoncozens/gftools-rust) and fontc.

The FontLab (`.vfb`) and FontForge (`.sfd`) files that were in `src/` remain
in the git history, as do the fonts the sources were converted from. The
`.sfd` files are imports of those fonts, not working sources.

How these sources were checked against the released fonts (the tools, this family's plan and the logs): https://github.com/felipesanches/gf-source-modernization.

## Known differences from the released fonts

These sources rebuild the fonts Google Fonts ships, except for the following, which were reviewed and deliberately left as they are:

- Combining marks are placed by the shaper from glyph bounding boxes (the font has no GPOS). 174 of the released font's glyf bounding boxes are stale, while a compiled font's are exact, so 25596 of 26656 base+mark pairs place the mark differently, by up to 35 units (of 2048) (tools/probes/hg_forks_from_binary).
