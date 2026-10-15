# Library Index — Beneficiary Service Desk

Five approved templates. Each one passed the three tests: prompt quality 5/5, template quality 6/6 and output quality 5/5 (see `Test_Results_Report.pdf`).

| Template | Task | Variables | Version | Status |
|---|---|---|---|---|
| [SD-Reply-Inquiry](templates/SD-Reply-Inquiry-v2_2026_10_14.md) | Reply to a beneficiary inquiry, with a CHECK section for the reviewer | `[INQUIRY]` `[LANGUAGE]` `[TONE]` `[MAX_WORDS]` `[DESK_FACTS]` | v2 | Approved |
| [SD-Summarize-Message](templates/SD-Summarize-Message-v1_2026_10_13.md) | Summarize a long message for the team | `[MESSAGE]` `[LANGUAGE]` `[MAX_WORDS]` `[FOCUS]` | v1 | Approved |
| [SD-Classify-Inquiry](templates/SD-Classify-Inquiry-v1_2026_10_13.md) | Sort an inquiry into one category | `[INQUIRY]` `[CATEGORIES]` `[LANGUAGE]` | v1 | Approved |
| [SD-Rewrite-Tone](templates/SD-Rewrite-Tone-v1_2026_10_15.md) | Rewrite a rushed or rude staff draft as a calm message | `[DRAFT]` `[LANGUAGE]` `[TONE]` `[MAX_WORDS]` | v1 | Approved |
| [SD-Draft-Reminder](templates/SD-Draft-Reminder-v1_2026_10_15.md) | Draft a reminder about a booked visit | `[VISIT_DATE]` `[VISIT_TIME]` `[LANGUAGE]` `[TONE]` `[MAX_WORDS]` `[DESK_FACTS]` | v1 | Approved |

## Shared blocks

| Block | Used by | File |
|---|---|---|
| Desk facts (v2) | SD-Reply-Inquiry, SD-Draft-Reminder | `blocks/SD-Facts-v2_2026_10_14.md` |

## Rules

| File | What it is |
|---|---|
| `rules/SD-Rules-v1_2026_10_14.md` | The five responsible-use rules written in Lab 4 |

## Report

| File | What it is |
|---|---|
| `Test_Results_Report.pdf` | A summary page and one page for each template: scores, sample input and one screenshot |

## Archive

Older versions stay in `_archive/` so the library keeps its history: `SD-Reply-Inquiry-v1_2026_10_13.md` and `SD-Facts-v1_2026_10_13.md`.

## `[LANGUAGE]` values (same in every template that writes text)

| Value | Meaning |
|---|---|
| Arabic | Answer in Arabic only |
| English | Answer in English only |
| Automated | Reply in the main language of the input |
| Bilingual | Two separate versions: Arabic, then English |
| Mixed | One reply that merges Arabic and English |

## Change log

| Date | Change |
|---|---|
| 2026_10_13 | Starter library: Reply v1, Summarize v1 |
| 2026_10_14 | Reply v2 (CHECK section), Facts v2 (48 hours), Classify v1, five rules v1 |
| 2026_10_15 | Day 5 project: Rewrite-Tone v1, Draft-Reminder v1; all five templates tested; report added |
