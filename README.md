# Swedenborg Text Digitize Workspace

This repository provides a workspace for digitizing handwritten and typewritten content related to Swedenborg.

## Purpose

Use this repository to organize transcription work and outputs for Swedenborg-related materials.

## AI Tooling

For AI-assisted digitizing, use the Python command-line tools from [doc-digitizer-ai](https://github.com/New-Christian-Bible-Study/doc-digitizer-ai).

## Per-Work Directory Expectations

The `doc-digitizer-ai` tools assume each transcription effort is organized as a dedicated directory for a single work, with specific subdirectories and files.

Follow the exact per-work layout and file expectations described in the [doc-digitizer-ai README](https://github.com/New-Christian-Bible-Study/doc-digitizer-ai?tab=readme-ov-file#working-directory-layout).

## Recommended Command Usage

Set an environment variable pointing to your local `doc-digitizer-ai` clone:

```bash
export DOC_DIGITIZER_AI_HOME=/path/to/doc-digitizer-ai
```

Then run the scripts in this order:

1. Generate a chunk PDF from a selected page range in a source PDF:

```bash
python $DOC_DIGITIZER_AI_HOME/generate-chunk-pdf.py
```

Example output location: `chunk-pdfs/<chunk_name>.pdf`

2. Transcribe that chunk PDF into markdown output and an AI log:

```bash
python $DOC_DIGITIZER_AI_HOME/transcribe-chunk-pdf.py
```

Example output locations:
- `transcriptions/<chunk_name>.md`
- `transcriptions/<chunk_name>-ai-log.md`
