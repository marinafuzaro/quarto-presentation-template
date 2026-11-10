# Quarto presentation template

a minimal `reveal.js` template for academic and professional talks, built with `quarto`; it's meant for conference presentations.

the design is intentionally restrained: white background, black headings, gray body text and a single blue accent used for highlights. slides are 16:9 at 1280x720, and the deck renders to one self-contained `.html` file with fonts and images embedded, so it can be shared or presented offline without any extra files.

## what it can do

- **cover + closing slide**: event logo on top, big title + subtitle, authors bottom left, any number of logos bottom right. the closing slide reuses the same layout
- **incremental bullets**: wrap a list in `.incremental` and each one shows up on click
- **quote cards**: plain `>` gets a gray card with a black rule on the left. add `[author (date)]{.source}` for the reference
- **highlighter**: `[some text]{.fragment .highlight}` draws a marker stroke left to right on click, then fades back once you move on
- **columns**: `.columns` + `.column` splits the width evenly with a gap
- **boxes**: `.box` adds a thick black line on top. good for compare/contrast
- **kickers**: `###` works as a small label above a box
- **text sizes**: `.detail` for a smaller supporting line, `.source` for tiny italic references

`template.qmd` includes a working example of each feature. 

## files

| file | description |
|---|---|
| `template.qmd` | source of the presentation; where you write your slides |
| `template.html` | rendered presentation (regenerated on every render) |
| `www/css/style.scss` | theme definitions |
| `www/fonts/SpaceGrotesk-VariableFont_wght.ttf` | font (space grotesk) |
| `www/img/template-logo-event.png` | event logo shown at the top of the cover and closing slides |
| `www/img/template-logo-footer-1.png` | first logo in the cover footer |
| `www/img/template-logo-footer-2.png` | second logo in the cover footer |

## how to run

you'll need [quarto](https://quarto.org/docs/get-started/) installed. from the project folder, there are two ways to work with the deck.

while editing, use preview. it starts a local server, opens the presentation in your browser and reloads it every time you save:

```bash
quarto preview template.qmd
```

when you're ready, render the final file:

```bash
quarto render template.qmd
```

this generates `template.html`, which opens in any browser. during the presentation, `f` toggles fullscreen, `s` opens the speaker view and `e` switches to a print-friendly layout for exporting to pdf.

## customizing

- **logos**: replace the images in `www/img/` keeping the same file names, or update the image paths in `template.qmd`
- **colors**: edit the variables at the top of `style.scss`. `$highlight` controls the marker color and `$gray` the body text
- **font**: add a new font file to `www/fonts/`, then update the `@font-face` block and the `$font` variable in `style.scss`
- **slide size**: adjust `width` and `height` in the yaml header of `template.qmd`
