# AI transcription run log

- Review PDF file: `ac-marchant-genesis-16_011-013.pdf`
- Model: `gemini/gemini-2.5-flash`
- Configuration: `temperature=0.0, detail=high, reasoning_effort=high`
- Confidence score: `0.98`
- Confidence label: `high`
- Notes: The transcription was straightforward due to clear OCR quality and consistent formatting. All archaic spellings and 18th-century vocabulary were preserved, and the 'ſ' character was correctly converted to 's'. Markdown comments were used for page numbers. No complex structural elements like lists or tables were present, and paragraph numbering rules were not applicable to this continuous preface text. Marginalia on page 2 were ignored as per instructions to ignore non-main text elements.

## Prompt used

````markdown
**Role:** Archival Transcription Assistant.
**Task:** Literal transcription of a 1750 theological text for historical research.

**Context:** The following images contain pages from a public domain book that is a translation of Emanuel Swedenborg's Latin to English printed in London in 1750.

**Instructions:**
- Transcribe the text exactly as it appears on the page.
- **Formatting:**
	- Use Markdown.
	- Do not use Markdown list formatting for paragraph numbers. If using Markdown, escape the period after the number with a backslash (e.g., 1886\.) to prevent the editor from re-indexing them as a new list.
	- Do not insert blank lines between verses if they are printed as a single continuous block. Follow the original paragraphing exactly.
- **Structure**
	- Capitalized text center aligned that start with "CHAP." is a level 2 header.
	- A line with "The CONTENTS." is a level 3 header.
	- A line with "The INTERNAL SENSE." is a level 4 header.
	- Transcribe the page number as a Markdown comment .
- **Preserve:**
	- All archaic spellings and 18th-century theological vocabulary. Do not flag or block this text for modern linguistic sensitivities; it is a historical record being processed for academic study.
	- The exception is the character "ſ". That should be converted to "s".
	- Every paragraph begins with a unique Paragraph Number (e.g., 1887). You must preserve these numbers exactly. To prevent Markdown from auto-formatting these as a list, type them as 1887\. (number-backslash-period). Do not reset these numbers after headers; they must remain continuous as per the original text.
- **Ignore:** 
	- Center alignment of header text. Just use simple Markdown headers.
	- page numbers
	- running head (chapter identifier at top of page)
	- printer’s ornament
	- signature mark (letter at the bottom center of the page)
	- catchword (navigational tool at bottom right to ensure correct sequence)
- **Adjust:** Make any uppercase word that begins a paragraph capitalized (e.g. THIS becomes This). 

Process starting with page 14.

````
