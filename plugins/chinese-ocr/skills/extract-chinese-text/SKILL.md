---
name: extract-chinese-text
description: Extract Chinese and mixed-language text, tables, and layout from images, screenshots, scanned PDFs, receipts, or photographed documents. Use when a user requests OCR, text recognition, scan-to-text, table extraction, or searchable output from image-based content.
---

# 中文 OCR

## Workflow

1. Inspect the input type, page count, resolution, rotation, and whether it contains handwriting, tables, seals, or multiple columns.
2. Check available engines in this order: an existing host vision tool for small visual reads; PaddleOCR for Chinese documents and tables; Tesseract with Chinese language data for simpler text; an authorized external OCR service only when the user accepts data leaving the device.
3. Preprocess only when useful: rotate, crop, deskew, denoise, or increase contrast while preserving the original.
4. Produce UTF-8 text. Preserve headings, paragraphs, page boundaries, reading order, and table structure when they can be inferred reliably.
5. Mark uncertain characters or cells instead of guessing. Include page or region references for low-confidence results.
6. Compare a sample of the output against the source image and report the engine and validation scope.

## Output

- Plain prose: Markdown or TXT.
- Tables: CSV/XLSX plus a short note about merged cells or ambiguous columns.
- Searchable archive: OCR text plus the untouched source; do not discard the original image.

Never upload confidential documents to a remote OCR service without explicit user authorization.
