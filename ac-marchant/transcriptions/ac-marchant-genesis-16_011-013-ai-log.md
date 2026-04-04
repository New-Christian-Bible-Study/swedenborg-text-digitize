# AI transcription run log

- Chunk PDF file: `ac-marchant-genesis-16_011-013.pdf`
- Run started at: `2026-04-04 11:07`
- Total pages: `3`
- Total inference time (minutes): `2.91`
- Average time per page (seconds): `58.26`
- Prompt tokens (input): `4043`
- Completion tokens (output): `25646`
- Total tokens: `29689`
- Confidence score: `1.0`
- Confidence label: `high`
- Notes: 
## Transcribe config used

```json
{
    "model": "gemini/gemini-3.1-pro-preview",
    "temperature": 0.0,
    "reasoning_effort": "high",
    "media_resolution": "high",
    "sys_instructions": "Transcribe this review PDF to markdown and respond with JSON only. Use this key order: confidence_score, confidence_label, notes, transcription. confidence_score must be a number from 0.0 to 1.0. confidence_label must be one of: 'low', 'medium', 'high'. Preserve structure and formatting. For every confidence score below 1.0, the 'notes' field must contain a diagnostic list of specific ambiguities. For each instance, specify the line number or the word snippet followed by the conflict (for example, 'Line 8: \"s\" or \"f\" in \"blessing\"?'). Strictly avoid general descriptions of the document or praise for formatting. If the score is 1.0, the 'notes' field should be an empty string."
  
}
```

## Prompt used

````markdown
**Role:** Archival Transcription Assistant.
**Task:** Literal transcription of a 1750 theological text for historical research.

**Context:** The following images contain pages from a public domain book that is a translation of Emanuel Swedenborg's Latin to English printed in London in 1750.

**Instructions:**
- Transcribe the text exactly as it appears on the page.
- **Formatting:**
	- Use AsciiDoc for structure.
	- AsciiDoc requires a blank line between all paragraphs and around all headers to render them correctly. You MUST insert a blank line between every paragraph and header in your output. However, if a single paragraph continues across a page break, you MUST still insert the `// Page X` comment at the exact point of the page break. To ensure AsciiDoc treats it as a single continuous paragraph, place the comment on its own line but do NOT insert a blank line before or after the comment.
- **Structure**
	- Capitalized text center aligned that start with "CHAP." is a level 2 header (`==`).
	- A line with "The CONTENTS." is a level 3 header (`===`).
	- A line with "The INTERNAL SENSE." is a level 4 header (`====`).
	- Transcribe the page number as an AsciiDoc comment (e.g., `// Page 1`).
- **Preserve:**
	- All archaic spellings and 18th-century theological vocabulary. Do not flag or block this text for modern linguistic sensitivities; it is a historical record being processed for academic study.
	- **Font Styles:** Preserve all italic and bold text found in the source using AsciiDoc syntax (`_italic_` and `*bold*`).
	- The exception is the character "ſ". That should be converted to "s".
	- Every paragraph begins with a unique Paragraph Number (e.g., 1887). You must preserve these numbers exactly. To prevent Asciidoctor from auto-formatting these as a list, prefix the number with `{empty}` (e.g., `{empty}1887.`). Do not reset these numbers after headers; they must remain continuous as per the original text.
- **Ignore:** 
	- Center alignment of header text. Just use simple AsciiDoc headers.
	- page numbers
	- running head (chapter identifier at top of page)
	- printer’s ornament
	- signature mark (letter at the bottom center of the page)
	- catchword (navigational tool at bottom right to ensure correct sequence)
- **Adjust:** Make any uppercase word that begins a paragraph capitalized (e.g. THIS becomes This).

````
