# tigodeken.github.io

Static portfolio site. Plain HTML/CSS, no build step. GitHub Pages serves the `main` branch root.

## Structure

```
index.html          home: hero, 3 project rows, about, contact
flipcap.html        Recharge Flip Cap (school project)
air-intake.html     air intake for carburetted motorcycles (personal project)
body-panels.html    plastic motorcycle body parts (personal project)
style.css           all styles, including print styles for the PDF
print.html          combines the 3 project pages for the PDF (not linked)
img/                WebP images (max 1600 px wide, max 200 KB), SVG schematics, og.jpg
favicon.svg
portfolio-tigo-deken.pdf
```

## Run locally

```bash
python -m http.server 8080
```

Open http://localhost:8080.

## Add a project

1. Copy `flipcap.html` to `<name>.html` and replace the content. Keep the title block (`<dl class="title-block">`) and the section order: result, problem, role, method, results, what I would change, files.
2. Put images in `img/` as WebP, max 1600 px wide and max 200 KB. Always set `width`, `height`, `alt` and `loading="lazy"`.
3. Add a `<a class="row">` entry in `index.html`.
4. Add the page to the list in `print.html` and update the prev/next links in `.pager`.

## Rebuild the PDF

With the local server running:

```bash
"/c/Program Files/Google/Chrome/Application/chrome.exe" --headless=new --no-pdf-header-footer --virtual-time-budget=8000 --print-to-pdf=portfolio-tigo-deken.pdf http://localhost:8080/print.html
```

`TODO:` markers are hidden in the PDF but visible on the site.
