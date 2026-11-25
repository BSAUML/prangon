# UML Prangon — streamlined website (draft v1)

## Files
- `index.html` — homepage
- `bulletin/index.html` — Bulletin page
- `community/index.html` — Community page
- `content.json` — all homepage/site text and page settings
- `database.xlsx` — records and **embedded pictures** for Bulletin, E-Board, Students
- `assets/` — permanent site branding and homepage pictures only
- `documents/` — constitution and guide PDFs (currently clearly labeled placeholders)

## Updating the website
1. Edit `database.xlsx` in Microsoft Excel. Keep the column names and sheet names unchanged.
2. **Insert pictures as traditional floating/over-cells images**, anchored inside the `photo` cell of the corresponding row. The site uses Excel drawing anchors to associate pictures with records. Excel's newer *Place in Cell* images use a different internal format and are not supported by this reader.
3. Move/resize each picture so its upper-left corner stays inside the `photo` cell. Save the XLSX and commit to GitHub. No extra image files or JSON exports are necessary.
4. Edit `content.json` for homepage content, labels, links and page headings.
5. Replace `documents/constitution.pdf` and `documents/new-student-guide.pdf` with real PDFs when available.
6. Upload the folder contents to the `BSAUML/prangon` repository root. GitHub Pages serves the pages.

## Testing
- Static pages fetch JSON/XLSX and should be tested via localhost or GitHub Pages (not double-clicked `file://`).
- In the project root run `python -m http.server 8000`, then open `http://localhost:8000/`.
- External CDN libraries: SheetJS xlsx 0.18.5, JSZip 3.10.1. These need an internet connection unless bundled locally.
- Supplied Bulletin and member entries are **sample data** taken from the old project; sample pictures are generated placeholders embedded inside the Excel workbook, not actual people/event photography.

## Important limitations
- Drawing-anchored JPG/PNG/GIF/WebP images work. Newer Excel *Place in Cell* / `DISPIMG` image format is not supported.
- Excel workbooks with many full-resolution images can be heavy to download; resize/compress pictures in Excel when needed.
- This is a static public website: do not put private student information in the workbook.
