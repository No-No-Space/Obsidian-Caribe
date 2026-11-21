# Caribe for Obsidian

> Created: 2026-11-20 · by Aksel Alvarez Jurgueson, with Claude
> Last updated: 2026-11-21 · by Claude
> Version: v0.1.2

An Obsidian theme built on the Caribe (AAJ) design system. The interface is neobrutalist: 2 px borders, hard offset shadows, square corners. The writing area stays clean.

**Status:** private, in development. Not yet submitted to the community theme directory.

## What it does

- **Heading hierarchy you can see at a glance.** Built for drafting the skeleton of a note first. H1 has a 3 px rule, H2 a 2 px rule, H3 is Salmón, H4 is Cielo Llanero, and H5–H6 are Fliege Mono caps labels.
- **Clean lists and tables.** Square bullets and mono numbering. Tables have a filled mono header and hairlines between rows, with no vertical rules.
- **Callouts in soft Caribe colours**, ready to use: note/info Cielo, todo/tip Mar Caribe, important/example Buganvilia, question Sol de Maíz, warning, failure/bug Salmón, abstract/quote Tierra. The tint is soft, the colour sits in the left rule and the icon, and the title stays in text colour so it reads in both modes.
- **Dark mode first**, with light mode too. Mar Caribe is the accent, and it overrides Obsidian's accent picker on purpose.
- **iPad.** The fonts are embedded in the CSS, and touch states are tuned.

## Structure

```
manifest.json         Obsidian theme manifest (name must match the theme folder: "Caribe")
theme.css             GENERATED: what Obsidian loads
build.py              builds theme.css
tokens/tokens.json    snapshot of the colour tokens from the AAJ Design System artifact
src/00-variables.css  roles: tokens → Obsidian variables, dark and light
src/10-note.css       the writing area
src/20-interface.css  the neobrutalist interface
src/30-mobile.css     iPad and phone
fonts/                woff2 files to embed (see fonts/README.md)
specimen/             a note with every styled element, to test the theme
```

The rule from the design system holds here too: **no hex code is written by hand in `src/`.** Every colour is a `var(--caribe-*)` generated from `tokens/tokens.json`.

## Build

```bash
python build.py                       # build theme.css
python build.py --check               # exit 1 if theme.css is out of date
python build.py --tokens path/to/tokens.json   # refresh the token snapshot from the full AAJ tokens.json
```

## Develop against a vault

Link the repo into a vault's themes folder, so every build shows up in Obsidian straight away. On Windows (cmd):

```bat
mklink /J "<vault>\.obsidian\themes\Caribe" "D:\404-Github\Obsidian-Caribe"
```

Then go to **Settings → Appearance → Themes → Caribe**. Obsidian reloads `theme.css` when it changes; after editing `manifest.json`, restart Obsidian.

For the iPad, the theme folder has to reach the vault through your sync method: `manifest.json` and `theme.css` are enough.

## Before publishing

- [ ] Fonts and their OFL licence files in `fonts/`, theme rebuilt
- [ ] A licence for the theme itself (`LICENSE`)
- [ ] Screenshot `screenshot.png` (512 × 288)
- [ ] GitHub release whose tag matches `manifest.json` `version`, with `manifest.json` and `theme.css` attached
- [ ] PR to `obsidianmd/obsidian-releases` (`community-css-themes.json`)
