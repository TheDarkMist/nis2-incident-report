# NIS2 Incident Report

Made for the WordCamp Europe 2026 lightning talk
**"NIS2 Incident Report in 10 Minutes"** by Francesco Canovi.

Two ways to draft a NIS2 incident report from the point of view of a small WordPress agency
or freelancer, usually pulled in as supply chain to a regulated client rather than being a
regulated entity:

- `nis2-incident-playbook.pdf` - a one-page printable checklist and form, to fill by hand
- `nis2-incident-report/` - a Claude skill that drafts the same reports for you

Same fields either way. Both produce a first draft only: a human reads it, fills the gaps,
and decides whether and when to send. This is not legal advice.

## The four reports

NIS2 (Directive (EU) 2022/2555) asks for a sequence of reports, not one:

- early warning, within 24 hours (Art. 23(4)(a))
- notification, within 72 hours (Art. 23(4)(b))
- final or progress report, within one month (Art. 23(4)(d))
- user-protection notice, without undue delay (Art. 23(1)-(2))

## Using the skill

**Claude Code** - copy `nis2-incident-report/` into `~/.claude/skills/` (or your project's
`.claude/skills/`) and restart. It triggers on its own when you describe a NIS2 incident.

**claude.ai** - zip the `nis2-incident-report/` folder (with `SKILL.md` at the top level),
rename it to `nis2-incident-report.skill`, and upload it under Settings > Capabilities > Skills.

Then just describe the incident in plain language and it works out which report is due.

## Two things to check every time

- The national CSIRT and the submission channel change with each country's NIS2
  transposition. Verify the recipient before anything is sent.
- As supply chain you provide the content, but the regulated client is the legal sender and
  files it under their own name.

## License

Free to use and adapt.
