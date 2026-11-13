# OFAES · Open Formative Assessment Evidence Schema

**Status: draft v0.1.** Feedback welcome through issues.

OFAES is a free, open format for everyday classroom evidence: exit tickets, quick checks, quiz items, journals and observations. One record covers:

1. **What was observed.** Exactly what the student wrote, said or did, and the conditions they had.
2. **How it might be interpreted.** One or more possible meanings, each pointing to the part of the work it rests on.
3. **How confident anyone is.** A confidence level, why the interpretation could be wrong, other explanations, and the one question that would settle it.
4. **What to do next.** Suggested next steps, scoped to one student, a small group or the whole class.
5. **What the teacher decided.** Accepted, adapted, rejected or waiting for more evidence.

Any tool can read and write it. [Boom AI](https://boomai.app/evidence-review-k12.html) is one implementation.

## Principles

- **Teachers decide.** An interpretation from an AI, a teacher or a specialist is recorded as a proposal (`proposed_by`). Nothing is final until `teacher_decision` says so.
- **Honest about uncertainty.** Every interpretation carries a confidence level and room for why it could be wrong.
- **Careful with children's information.** Students are identified only by an anonymous, school-assigned ID. Supports are described by what they do (for example `read aloud`), never by disability or diagnosis. No names, emails or state student numbers.
- **Portable.** Evidence should move between tools, so schools are never locked in.

## Files

| Path | What it is |
|---|---|
| `schema/ofaes-v0.1.schema.json` | The schema ([JSON Schema 2020-12](https://json-schema.org/draft/2020-12/schema)) |
| `examples/exit-ticket-fractions.json` | A valid example: one 5th-grade exit-ticket response on adding fractions (fictional student) |

## Validate a record

With Python:

```bash
pip install jsonschema
python -c "import json, jsonschema; jsonschema.validate(json.load(open('examples/exit-ticket-fractions.json')), json.load(open('schema/ofaes-v0.1.schema.json'))); print('valid')"
```

## License

Apache License 2.0. See [LICENSE](LICENSE).
