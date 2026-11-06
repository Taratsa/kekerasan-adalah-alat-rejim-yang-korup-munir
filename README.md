# Kekerasan adalah Alat Rejim yang Korup: Transkrip Percakapan dengan Munir — EPUB source

Transkrip wawancara *Perspektif Baru*, Edisi 126 (PT InterMatrix), dibuat dari pindaian PDF (OCR via TurboOCR).

## Build

`book.md` is the hand-edited source (`book.json` `"source": "book.md"`). Edit it directly; it is never regenerated.

    cd /Users/sf/Documents/workspaces/pdf-to-epub-turboocr
    python3 pipeline.py "<path to this folder>" --steps build,verify,se

Do not run the `ocr` or `images` steps for this book.

## Outputs

- `Kekerasan adalah Alat Rejim yang Korup - Munir.epub`: finished edition (pandoc build, `finish` block in `book.json`)
- `Kekerasan adalah Alat Rejim yang Korup - Munir (SE).epub`: Standard Ebooks manual 1.9.1 edition (`--steps se`), Indonesian, white-label
- `verify.json`, `review.txt`: build checks

## Hand-editable files

- `book.md`: all text
- `license.html`, `colophon.html`: pages of the finished edition
- `se-imprint.md`, `se-colophon.md`, `se-license.md`: Keterangan Edisi, Kolofon and Lisensi pages of the SE edition

## Lineage OCR -> book.md

`ocr/md/pNN.md` (raw OCR, not tracked) -> `book.ocr-original.md` (frozen baseline) -> `book.md`.
`corrections.json` logs every change from the baseline to `book.md` (SymSpell and manual edits, scanner footers, paragraph joins)
and is written by `corrections.py` only. `python3 corrections.py check <this folder> --scan` replays it and must pass.
The corrections were not compared against the scan images; they rest on SymSpell suggestions, the dictionaries and sentence context.

## Rights

The editorial contributions (OCR, proofreading, typesetting, EPUB structure) are dedicated to the public domain under CC0 1.0.
The underlying interview text remains with its rights holders; this edition claims no rights in it.
