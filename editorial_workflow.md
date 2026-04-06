# Editorial Workflow – Quarto Book Project

This document describes the recommended process for writing, revising, and
finalising each chapter of a book produced with this Quarto template.

The workflow combines AI-assisted drafting with structured human review to
produce publication-ready content efficiently.

---

## The Four Phases

### Phase 1 – AI-Assisted First Draft

**Who:** Author / editorial operator + AI tool (e.g. Claude, GPT-4)  
**Input:** Chapter outline (topics, goals, target word count)  
**Output:** First draft (`_draft_v1.md`)

**Steps:**
1. Open the chapter file (e.g. `chapter_1.qmd`) and read the outline section at the top.
2. Use the prompts in [`ai_prompts.md`](./ai_prompts.md) to generate a first draft.
3. Save the raw AI output as `_draft_v1.md` alongside the chapter file.

**Rules:**
- Never publish AI output without human review.
- Mark every AI draft clearly as `[AI DRAFT – NOT REVIEWED]` at the top.
- Provide as much specific context as possible in the prompt for better results.

---

### Phase 2 – Human Revision

**Who:** Author or editor  
**Input:** AI draft (`_draft_v1.md`)  
**Output:** Revised draft (`_draft_v2.md`)

**Steps:**
1. Read the draft once without editing to get an overall sense.
2. Identify and flag:
   - Factual errors or unverifiable claims
   - Tone inconsistencies with the rest of the book
   - Weak or underdeveloped sections
   - Passages that need the author's personal voice or expertise
3. Rewrite, expand, and cut as needed.
4. Save as `_draft_v2.md` with revision notes inline.

**Quality criteria:**
- The text must sound like the author, not an AI.
- Every technical claim must be verifiable.
- Narrative rhythm must be consistent across chapters.

---

### Phase 3 – Author / Expert Validation

**Who:** Subject-matter expert or author  
**Input:** Revised draft (`_draft_v2.md`) + list of open questions  
**Output:** Validated draft (`_draft_v3.md`)

**Steps:**
1. Expert reviews the draft and answers the editor's open questions.
2. Expert identifies technical inaccuracies, missing nuance, or personal details to add/remove.
3. Editor integrates feedback into the draft.
4. Save as `_draft_v3.md`.

**Note:** The expert always has the final say on technical and personal content.

---

### Phase 4 – Final Editing

**Who:** Editor (linguistic and stylistic)  
**Input:** Validated draft (`_draft_v3.md`)  
**Output:** Final chapter (`chapter_N.qmd` updated)

**Steps:**
1. Full grammar and punctuation pass.
2. Stylistic consistency check against other chapters.
3. Verify all citations and bibliography entries in `references.bib`.
4. Check image captions and cross-references.
5. Update the chapter `.qmd` file with the final text.
6. Update [`progress_tracker.md`](./progress_tracker.md).

---

## File Naming Convention

For each chapter, the draft files follow this progression:

```
chapter_1_draft_v1.md      # AI draft
chapter_1_draft_v2.md      # Human-revised draft
chapter_1_draft_v3.md      # Expert-validated draft
chapter_1.qmd              # Final (updated in place)
```

Keep draft files outside the Quarto source tree (e.g. in a `drafts/` folder)
so they are not rendered.

---

## General Rules

1. **Never publish unreviewed AI text** as final content.
2. **Expert approval is required** for technical claims before publishing.
3. **Version everything** – use Git commits as checkpoints after each phase.
4. **One chapter at a time** – finish all four phases before moving to the next chapter.
5. **Track progress** in [`progress_tracker.md`](./progress_tracker.md).
