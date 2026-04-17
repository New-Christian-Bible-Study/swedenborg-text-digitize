# AI transcription summary

- Chunk file: `ac-marchant-genesis-16_011-013.pdf`
- Total pages: `3`
- Confidence score: `0.99`
- Confidence label: `high`
- Notes: Page 3 Line 9: "1" or "i" in "N. 1"?
## Transcribe config used

```json
{
  "model": "gemini/gemini-3.1-pro-preview",
  "temperature": 1.0,
  "reasoning_effort": "high",
  "media_resolution": "medium",
  "sys_instructions": "Respond with JSON only matching the provided schema. Key order: lines, confidence_score, confidence_label, notes. The \"lines\" array must contain one object per visible text line in reading order; each object has page_number (integer, 1-based within this chunk), text (string), and box_2d (four integers [ymin, xmin, ymax, xmax] in 0-1000 normalized coordinates for that line on that page). confidence_score must be a number from 0.0 to 1.0. confidence_label must be one of: 'low', 'medium', 'high'. For every confidence score below 1.0, the 'notes' field must contain a diagnostic list of specific ambiguities. For each instance, specify the line index or the word snippet followed by the conflict (for example, 'Line 8: \"s\" or \"f\" in \"blessing\"?'). Strictly avoid general descriptions of the document or praise for formatting. If the score is 1.0, the 'notes' field should be an empty string."
}
```

## Prompt used

````markdown
# Transcription & Spatial Detection Instructions (Chunk Mode)

**Role:** Archival Transcription Assistant with Spatial Awareness.
**Task:** Literal transcription and line detection of historical text for a specific PDF chunk.

**Context:** You are processing a chunk of a historical PDF (Pages {START_PAGE} to {END_PAGE}). This material is being digitized for academic study. You will provide a structured JSON response to facilitate a human-in-the-loop validation process.

**Output Format:**
Return a single JSON **object** with a key `"lines"` whose value is an array. Every line of text on every page must be its own element in that array. Each element is an object containing:
1. `"page_number"`: The page within **this chunk PDF** where the text appears (1-based).
2. `"text"`: The transcription of the line.
3. `"box_2d"`: `[ymin, xmin, ymax, xmax]` coordinates for the line bounding region, **normalized 0–1000** (integers) relative to that page’s width and height.

**Core Rule:** Every entry in the `"lines"` array must represent exactly one physical line of text on the page. The `"text"` field must contain *only* the characters physically located within the `"box_2d"` region. Do not complete words or sentences using text from other parts of the page.

**Transcription Rules:**
- **Literalness:** Transcribe the text exactly as it appears.
- **Hyphenation:** If a word is split across two lines by a hyphen, remove the hyphen and join the parts of the word together on the line where the word began.
- **Paragraph Numbers:** Prefix paragraph or verse numbers with `{empty}` (e.g., `{empty}123.`).
- **Structure:** 
    - Use AsciiDoc headers (`==`, `===`) for titles/major headings.
    - Start each new page with a line transcribed as `// Page X`.
- **Preservation:**
    - Preserve archaic spellings and punctuation.
    - Use AsciiDoc syntax (`_italic_` and `*bold*`).
    - Convert historical "long s" (`ſ`) to `s`.
    - Convert paragraph-starting ALL CAPS words to Sentence case.

**Ignore (Do not transcribe):** 
- Running heads (titles at the very top of pages).
- Ornaments and decorative horizontal bars.
- Signature marks and page numbers in the bottom margin (e.g., "A 2", "23181").
- Catchwords (the single word at the far bottom-right corner that anticipates the next page).

````
