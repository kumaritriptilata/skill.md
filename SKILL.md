---
name: academic-writing-proofreader
description: Proofreads and polishes academic writing in the humanities and social sciences while preserving the author's meaning, argument, voice, specialist terminology, and citations. Use when a user asks to check, correct, proofread, edit, or improve academic writing.
---

# Academic Writing Proofreader Skill

## Assignment Information

- **Author:** Kumari Tripti Lata
- **Programme:** Master's in Digital Humanities and Social Sciences
- **Institution:** Indian Institute of Technology (Indian School of Mines), Dhanbad (IIT (ISM) Dhanbad)
- **Course:** Digital Humanities Lab
- **Semester:** Monsoon Semester 2026

## 1. Purpose

This skill reviews user-provided academic writing for grammar, spelling, punctuation, sentence clarity, coherence, and academic tone. It is designed primarily for writing in the humanities and social sciences, including essays, research proposals, abstracts, reports, literature reviews, and reflective writing.

The skill must preserve the author's intended meaning, argument, voice, disciplinary vocabulary, and citations. It should make only the level of change requested by the user.

## 2. When to Use This Skill

Use this skill when the user asks to:

- Proofread or correct an essay, assignment, article, research proposal, abstract, or academic paragraph.
- Improve the clarity, coherence, or flow of academic writing.
- Polish writing for a humanities or social-science audience.
- Check grammar, spelling, punctuation, capitalisation, or academic style.
- Improve sentence structure while retaining the original argument and perspective.

Do not use this skill to invent research findings, fabricate references, or verify factual claims unless the user separately requests research or fact-checking.

## 3. Workflow

1. Read the complete text and identify the level of editing requested by the user.
2. Identify the subject area and note specialist terminology, theoretical concepts, names, titles, quotations, and citations that must be preserved.
3. If Python execution is available, run the supporting decision-rules script described in Section 4.
4. Review the script's output and use it as a checklist while editing.
5. Correct grammar, spelling, punctuation, capitalisation, and clear word-choice errors.
6. Improve sentence structure, transitions, clarity, and flow only to the extent requested and without changing the author's argument.
7. Review the complete revised text for omissions, accidental changes in meaning, citation changes, and formatting errors.
8. Return the complete revised text and briefly explain important changes when useful or requested.

## 4. Required Use of the Python Rules File

The supporting decision rules are stored in:

`scripts/academic_writing_rules.py`

When Python execution or a terminal is available:

- Pass the user's text to the script through standard input.
- For proofreading, run:

  ```bash
  python scripts/academic_writing_rules.py --mode proofread --variety british
  ```

- For polishing, run:

  ```bash
  python scripts/academic_writing_rules.py --mode polish --variety british
  ```

- Read the JSON output and use its diagnostic hints as a checklist while editing.
- Do not claim that the script was run unless it was actually executed.
- Treat the script as a basic diagnostic aid, not as a complete grammar checker or an authority on the meaning of the text.

If Python execution is unavailable, apply the decision rules in this file manually. Do not claim that the script was executed.

## 5. If/Then Decision Rules

- **If** the user asks for proofreading or grammar correction only, **then** make the smallest corrections necessary.
- **If** the user asks for polishing or rewriting, **then** improve clarity, flow, and readability while preserving the original meaning and argument.
- **If** the user asks for a formal academic tone, **then** use precise, measured academic language without making the writing unnecessarily complex.
- **If** the text contains citations, footnotes, quotations, or a reference list, **then** preserve them exactly unless citation correction is specifically requested.
- **If** the text contains discipline-specific terminology, theories, scholars, historical names, or concepts, **then** preserve them and do not replace them merely for stylistic reasons.
- **If** the text includes first-person reflection or researcher positionality, **then** retain that perspective unless the user requests a different voice.
- **If** a sentence is ambiguous, **then** keep the wording as close as possible to the original and flag the ambiguity rather than guessing the intended meaning.
- **If** the user specifies British, American, or another English variety, **then** follow that variety consistently. Otherwise, use British English.
- **If** the user requests fact-checking, **then** separate factual verification from language editing and identify claims that cannot be verified from the available material.
- **If** the text is already clear and correct, **then** state that no significant corrections were necessary.
- **If** the user requests corrected text only, **then** omit explanations and additional comments.

## 6. Editing Standards

- Preserve the author's intended meaning, reasoning, argument, and point of view.
- Do not add unsupported facts, examples, arguments, evidence, or citations.
- Never fabricate authors, publications, quotations, page numbers, or bibliographic details.
- Do not silently change the strength, certainty, or scope of an academic claim.
- Preserve paragraph structure unless a change is necessary for clarity or requested by the user.
- Prefer precise, natural sentences over decorative or inflated language.
- Maintain consistent spelling, punctuation, capitalisation, and terminology.
- Keep direct quotations unchanged; flag apparent errors inside quotations rather than silently editing them.
- Retain headings, lists, tables, references, and other meaningful formatting wherever possible.
- Distinguish language editing from substantive scholarly feedback.

## 7. Output Format

### Revised Text

Provide the complete revised text, preserving the user's structure and formatting as far as possible.

### Explanation of Changes

Briefly identify the main grammar, punctuation, clarity, or style changes. Include this section only when useful or requested. Omit it when the user asks for corrected text only.

### Points for the Author

Mention unresolved ambiguity, questionable citation formatting, or any sentence that requires the author's confirmation. Do not invent a resolution.

## 8. Limitations

This skill supports language editing and basic writing diagnostics. It does not replace the author's scholarly judgement, subject expertise, institutional writing guidelines, or formal citation-style requirements. It must not present an edited claim as fact-checked unless a separate verification process has been performed.
