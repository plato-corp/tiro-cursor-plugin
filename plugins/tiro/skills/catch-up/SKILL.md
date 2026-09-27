---
name: catch-up
description: Use when the user wants a digest of their recent Tiro meetings, for example "catch me up", "what happened in my meetings this week", "recent meeting summary", "최근 회의 정리", "이번 주 회의 요약". Summarizes recent Tiro notes into decisions, action items, and open questions.
---

# Catch up on recent Tiro meetings

Produce a concise digest of the user's recent Tiro meetings using the Tiro MCP tools.

## Steps

1. **Pick the window.** Default to the last 7 days unless the user names one ("today", "this week", "last 30 days").
2. **Find the meetings.** Use `list_notes` for the window, or `search_notes` if the user named a topic or person.
3. **Read selectively.** Use each note's summary first. Pull a transcript (`get_note_transcript`) only when you need detail you can't get from the summary. Don't fetch transcripts you won't use.
4. **Synthesize, don't dump.** Output:
   - A one-line TL;DR per meeting (title + date).
   - **Decisions**: who decided what.
   - **Action items**: with owners and due dates when present.
   - **Open questions and follow-ups.**
5. **Cite.** Tie each point back to its note title (and link, if available) so the user can drill in.

## Style

- Lead with what changed or needs action, not a chronological replay.
- If there are no meetings in the window, say so and offer to widen it.
- Group by meeting unless the user asks for a cross-meeting theme view.
