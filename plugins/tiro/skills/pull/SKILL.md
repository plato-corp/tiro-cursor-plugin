---
name: pull
description: Use when the user wants a specific Tiro note or transcript saved into the current project or folder as markdown, for example "pull the X meeting", "save that transcript here", "get the standup notes into this repo", "이 회의 트랜스크립트 가져와", "노트 마크다운으로 저장". Writes a clean markdown file from a Tiro note.
---

# Pull a Tiro note into the workspace

Fetch a Tiro note and save it as a clean markdown file in the current working directory, using the Tiro MCP tools.

## Steps

1. **Identify the note.** Use `search_notes` with the user's description (title, attendee, topic, date). If several match, list the top candidates and ask which one. Don't guess.
2. **Fetch the content.** Summary via `get_note`. The full transcript via `get_note_transcript` only when the user wants the verbatim record (ask if unclear, since transcripts are long).
3. **Write the file** into the current directory:
   - Filename: a slug of the note title + date, e.g. `2026-06-25-q3-planning.md`. Don't overwrite an existing file without confirming.
   - Heading: title, date, attendees, and the Tiro link.
   - Body: the summary first, then the transcript under a `## Transcript` heading if included.
4. **Report the saved path** (and size). Keep the chat output short. The file is the deliverable.

## Style

- Default to summary-only unless the user asks for the transcript.
- Preserve speaker labels and timestamps in the transcript when present.
