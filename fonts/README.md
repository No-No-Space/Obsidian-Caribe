# Fonts

`build.py` embeds the fonts in this folder into `theme.css` as base64. That is what makes the theme look the same on the iPad, where you can't install desktop fonts. On desktop, installed fonts are used first (`local()`).

Copy these files from the AAJ Design System artifact (`project/fonts/`) into this folder:

| File | Use |
| --- | --- |
| `Gully-Bold.woff2` | Headings, buttons, tabs (700 only) |
| `Moderustic-Regular.woff2` | Body and interface text |
| `Moderustic-Bold.woff2` | `**bold**` |
| `FliegeMono-Light.woff2` | Code, figures (300) |
| `FliegeMono-Regular.woff2` | Labels, H6, status bar (400) |
| `FliegeMono-Medium.woff2` | Table headers, H5 (500) |

Also copy the licence files: `Gully-OFL.txt`, `Moderustic-OFL.txt` and `FliegeMono-OFL.txt`. All three families are under the SIL Open Font License 1.1, which allows embedding and redistribution as long as the licence travels with the fonts. Keep the licence files here before you publish the theme.

`.ttf` and `.otf` files with the same names work too, but `woff2` keeps `theme.css` smaller.
