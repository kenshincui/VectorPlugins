---
name: process-pdf
description: Read, extract, OCR, create, merge, split, reorder, rotate, watermark, compress, redact, fill, or convert PDF files. Use whenever the user asks to inspect or change a PDF, create a searchable PDF, extract tables, combine documents, or validate PDF page layout.
---

# PDF 工具

## Select the path

- Text extraction: prefer `pdftotext` or PyMuPDF and preserve page boundaries.
- Scanned PDF: render pages, run OCR, and keep the original alongside searchable output.
- Merge/split/rotate/reorder: use pypdf or qpdf when available.
- Layout-sensitive creation: use a PDF-native library and render every page for inspection.
- Forms: inspect AcroForm fields before filling; do not flatten unless requested.
- Redaction: use real redaction that removes underlying content, not a black rectangle overlay.

## Workflow

1. Inspect page count, dimensions, encryption, text presence, forms, and attachments without mutating the original.
2. Copy to a new output path unless the user explicitly requests in-place replacement.
3. Perform the smallest requested operation.
4. Reopen the result and verify page count, order, metadata, expected text, and encryption state.
5. Render changed pages and visually inspect clipping, rotation, blank pages, font failures, and watermark/redaction placement.
6. Report the toolchain, output path, and exact verification performed.

Never attempt to bypass passwords or DRM. Do not claim secure redaction without checking that the removed text is absent from extraction and object content.
