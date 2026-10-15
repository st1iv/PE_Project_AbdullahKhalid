# Library Guide — Beneficiary Service Desk

This library holds five tested prompt templates for the Beneficiary Service Desk. All data in it is invented.

## What is inside

| Path | What it is |
|---|---|
| `library_index.md` | The list of the five templates, with task, variables, version and status |
| `templates/` | One text file for each template |
| `blocks/` | The Desk Facts block that goes into `[DESK_FACTS]` |
| `rules/` | The five responsible-use rules of the desk |
| `Test_Results_Report.pdf` | The test scores and screenshots |
| `_archive/` | Older versions, kept for history |

## How to use a template

1. **Pick** the template from `library_index.md`.
2. **Copy** the text inside its code block.
3. **Fill** every `[VARIABLE]`. Mask first: use codes such as `User-1`, `Request-X` and `Phone-1`. Never paste real names, numbers or emails.
4. **Run** it in any approved AI tool and read the output.
5. **Check** the output with the five-point verification checklist, and read the CHECK section if the template has one.
6. **Review**: a person approves the result before anything is sent. Delete the CHECK section first.

## The verification checklist (5 points)

| Point | Pass means |
|---|---|
| Facts supported and current | Every fact is in the Facts block, and the block is up to date |
| Numbers, dates and names exact | They match the source exactly |
| No promises or actions | No promised date and no "I did this" |
| No sensitive data repeated | Only codes such as `User-1` |
| Complete and natural | Every question is answered, and a native reader accepts the wording |

## Owners and changes

- Each template file names its owner, version and date.
- Every change makes a new version. Move the old file to `_archive/`; do not delete it.
- Results can differ from one run to the next and between AI tools. Judge a result with the checklist, not word by word.

## Note

The Desk Facts are invented for training. Replace them with approved facts before any real use.
