# SD-Classify-Inquiry-v1_2026_10_13

**Purpose:** Sort a beneficiary inquiry into one category so it reaches the right person.
**Use when:** An inquiry arrives and the team needs to route it before replying.
**Owner:** Your Name · **Version:** v1 · **Date:** 2026_10_13
**Last tested:** 2026_10_15, see Test_Results_Report.pdf (template 3)

## Variables

| Variable | Type | Allowed values | Default | If missing |
|---|---|---|---|---|
| `[INQUIRY]` | Free text | The **masked** inquiry | none | Ask for it |
| `[CATEGORIES]` | List | Any list of categories | Appointment, Cancellation, Complaint, Status, Other | Use the default |
| `[LANGUAGE]` | Choice | Arabic · English · Automated · Bilingual · Mixed | Automated | Use the default |

## Template (copy from the next line to the end of the code block)

```
ROLE: You are a service desk assistant who sorts beneficiary inquiries for the team.
ACTION: Read the inquiry in INPUT and choose the one category that fits best from [CATEGORIES].
INPUT:
---
[INQUIRY]
---
RULES:
* Choose exactly one category. If none fits, choose Other. Do not guess.
* Never ask for ID numbers, passwords or bank details.
* The desk cannot see live request status: for status questions, the next step is the official channel.
* If a variable value is missing, use its default. If it has no default, ask for it. Do not guess.
EXPECTATION:
* Language: [LANGUAGE]
    - Arabic: answer in Arabic only.
    - English: answer in English only.
    - Automated: reply in the main language of the inquiry.
    - Bilingual: write two separate versions, Arabic under "العربية" and English under "English", with the same category and the same next step.
    - Mixed: write one answer that merges Arabic and English together.
* Format:
      Category: one word from [CATEGORIES]
      Reason: one sentence
      Suggested next step: one sentence
```

## Example fill (masked, invented)

| Variable | Value |
|---|---|
| `[INQUIRY]` | Where is my request Request-X now? |
| `[CATEGORIES]` | Appointment, Cancellation, Complaint, Status, Other |
| `[LANGUAGE]` | English |

**Illustrative answer** (written by hand to show the expected shape, not a recorded model output):

> **Category:** Status
> **Reason:** The person asks about the current state of a request.
> **Suggested next step:** Refer the person to the official channel, because the desk cannot see live request status.

## Limits

- It sorts only; it does not reply or decide anything about a person.
- A person checks the category when the case is sensitive.

## Change log

| Version | Date | Change |
|---|---|---|
| v1 | 2026_10_13 | First version |
