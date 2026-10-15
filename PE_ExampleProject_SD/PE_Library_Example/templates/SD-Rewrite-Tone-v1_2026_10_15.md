# SD-Rewrite-Tone-v1_2026_10_15

**Purpose:** Rewrite a rushed or rude staff draft as a calm, polite message to a beneficiary, without changing any fact.
**Use when:** A staff member wrote a draft that sounds abrupt, blaming or sarcastic and a person will review the new version before sending.
**Owner:** Your Name · **Version:** v1 · **Date:** 2026_10_15
**Last tested:** 2026_10_15, see Test_Results_Report.pdf (template 4)

## Variables

| Variable | Type | Allowed values | Default | If missing |
|---|---|---|---|---|
| `[DRAFT]` | Free text | The **masked** staff draft | none | Ask for it |
| `[LANGUAGE]` | Choice | Arabic · English · Automated · Bilingual · Mixed | Automated | Use the default |
| `[TONE]` | Choice | Formal · Friendly · Calm · Neutral | Calm | Use the default |
| `[MAX_WORDS]` | Number | 30 to 120 | 60 | Use the default |

## Template (copy from the next line to the end of the code block)

```
ROLE: You are an editor at the Beneficiary Service Desk who improves staff drafts before they are sent.
ACTION: Rewrite the draft in INPUT in the requested tone. First find the facts, numbers, dates, codes and the next step in the draft, then rewrite, and keep all of them.
INPUT:
---
[DRAFT]
---
RULES:
* Keep every fact, number, date and code exactly as written. Do not add facts, promises, dates or actions.
* Remove blame, threats, sarcasm and pressure. Keep the request or the next step.
* Never ask for ID numbers, passwords or bank details.
* If the draft contains personal data, do not repeat it. Keep codes such as User-1 or Request-X as written.
* If a variable value is missing, use its default. If it has no default, ask for it. Do not guess.
EXPECTATION:
* Language: [LANGUAGE]
    - Arabic: answer in Arabic only.
    - English: answer in English only.
    - Automated: reply in the main language of the draft.
    - Bilingual: write two separate versions, Arabic under "العربية" and English under "English", with the same facts and the same next step.
    - Mixed: write one message that merges Arabic and English together.
* Tone: [TONE]
* Maximum [MAX_WORDS] words (for each version if Bilingual).
* Format:
      Greeting: one sentence
      Message: two or three sentences
      Next step: one clear sentence
      Closing: one sentence, "Best regards, Beneficiary Service Desk" (in Arabic: "مع تحيات مكتب خدمة المستفيدين")
* After the message, add a section called "CHECK (for the reviewer, not for sending)":
    - Removed or softened: list each phrase you changed.
    - Kept exactly: list every number, date and code in the message.
```

## Example fill (masked, invented)

| Variable | Value |
|---|---|
| `[DRAFT]` | I already told you twice. Come on Sunday and bring the form, we are not going to wait for you again. |
| `[LANGUAGE]` | English |
| `[TONE]` | Calm |
| `[MAX_WORDS]` | 50 |

**Illustrative message** (written by hand to show the expected shape, not a recorded model output):

> Hello, thank you for your message.
> We would be glad to see you on Sunday.
> Next step: please visit us on Sunday and bring the form.
> Best regards, Beneficiary Service Desk
>
> CHECK — Removed or softened: "I already told you twice", "we are not going to wait for you again". Kept exactly: Sunday, the form.

## Limits

- It changes the tone only. A person checks that the facts and the next step are still right.
- The CHECK section is for the reviewer: delete it before the message is sent.
- A native reader reviews every Arabic message.

## Change log

| Version | Date | Change |
|---|---|---|
| v1 | 2026_10_15 | First version |
