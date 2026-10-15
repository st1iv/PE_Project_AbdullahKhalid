# SD-Summarize-Message-v1_2026_10_13

**Purpose:** Summarize a long beneficiary message so the team can act on it quickly.
**Use when:** A message is long, repeated or hard to read and a person needs the key points.
**Owner:** Your Name · **Version:** v1 · **Date:** 2026_10_13
**Last tested:** 2026_10_15, see Test_Results_Report.pdf (template 2)

## Variables

| Variable | Type | Allowed values | Default | If missing |
|---|---|---|---|---|
| `[MESSAGE]` | Free text | The **masked** message | none | Ask for it |
| `[LANGUAGE]` | Choice | Arabic · English · Automated · Bilingual · Mixed | Automated | Use the default |
| `[MAX_WORDS]` | Number | 30 to 150 | 80 | Use the default |
| `[FOCUS]` | Choice (optional) | Request · Complaint · Deadlines · None | None | Use the default |

## Template (copy from the next line to the end of the code block)

```
ROLE: You are a service desk assistant who summarizes beneficiary messages for the team.
ACTION: Summarize the message in INPUT. First find the main request, then any deadline or reference code, then write the summary.
INPUT:
---
[MESSAGE]
---
RULES:
* Use only the message. Do not add facts.
* Do not repeat personal data. Keep codes such as User-1 or Request-X exactly as written.
* If something is unclear, say what is unclear instead of guessing.
* If the message contains several requests, list them in order.
* If [FOCUS] is not None, put that point first.
* If a variable value is missing, use its default. If it has no default, ask for it. Do not guess.
EXPECTATION:
* Language: [LANGUAGE]
    - Arabic: answer in Arabic only.
    - English: answer in English only.
    - Automated: reply in the main language of the message.
    - Bilingual: write two separate versions, Arabic under "العربية" and English under "English", with the same facts.
    - Mixed: write one summary that merges Arabic and English together.
* Maximum [MAX_WORDS] words (for each version if Bilingual).
* Format:
      Main request: one sentence
      Key details: up to three bullet points
      Suggested next step for the team: one sentence
```

## Example fill (masked, invented)

| Variable | Value |
|---|---|
| `[MESSAGE]` | I booked a visit for Request-X two weeks ago, then missed it because of illness. I wrote twice and nobody replied. I need a new appointment this week and want to know what I should bring. |
| `[LANGUAGE]` | English |
| `[MAX_WORDS]` | 60 |
| `[FOCUS]` | Request |

**Illustrative summary** (written by hand to show the expected shape, not a recorded model output):

> **Main request:** A new appointment this week for Request-X after a missed visit.
> **Key details:**
> - Missed the earlier visit; wrote twice with no reply.
> - Asks what to bring.
>
> **Suggested next step for the team:** Offer available slots and confirm the documents list through the official channel.

## Limits

- It summarizes only what the message says; it does not check facts.
- A person reads the original message when the case is sensitive.

## Change log

| Version | Date | Change |
|---|---|---|
| v1 | 2026_10_13 | First version |
