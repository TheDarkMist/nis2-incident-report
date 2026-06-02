# NIS2 Incident Report (Claude skill)

A Claude agent skill that drafts NIS2 incident reports from the realistic position of a
small WordPress agency or freelancer, the kind that is usually pulled in as **supply chain**
to a regulated client rather than being a regulated entity itself.

Built as the giveaway for the WordCamp Europe 2026 lightning talk
**"NIS2 Incident Report in 10 Minutes"** by Francesco Canovi.

## What it does

NIS2 (Directive (EU) 2022/2555) does not ask for one report. It asks for a sequence of
reports with hard deadlines. This skill drafts each one:

- **Early warning**, within 24 hours of becoming aware (Art. 23(4)(a))
- **Notification**, within 72 hours of becoming aware (Art. 23(4)(b))
- **Final or progress report**, within one month of the 72-hour notification (Art. 23(4)(d))
- **User-protection notice**, without undue delay (Art. 23(1)-(2))

It always produces a **first draft**. A human reads it, fills the gaps, and decides whether
and when to send. The skill never sends anything and never decides on the client's behalf.
Every draft opens with a "Gaps to fill before sending" checklist and ends with a sign-off line.

## Install

### Claude Code

Copy the `nis2-incident-report/` folder into your skills directory:

- per project: `<project>/.claude/skills/nis2-incident-report/`
- global: `~/.claude/skills/nis2-incident-report/`

Restart Claude Code. The skill triggers on its own when you describe a NIS2 incident.

### claude.ai

Download the `nis2-incident-report/` folder and zip it so the archive contains
`nis2-incident-report/SKILL.md` at its top level, rename the archive to
`nis2-incident-report.skill`, then upload it under Settings > Capabilities > Skills.

## Use it

Describe your incident in plain language. For example:

> One of our clients (an Italian company that falls under NIS2) had their WordPress site
> breached through an outdated plugin. We are their agency and host. Draft what has to go
> out first.

The skill works out which report is due, asks for the facts it needs, and drafts it.

## What is inside

- `nis2-incident-report/SKILL.md` - the workflow
- `nis2-incident-report/references/report-templates.md` - the four report templates with their legal basis
- `nis2-incident-report/references/csirt-by-country.md` - which national CSIRT receives the report
- `nis2-incident-playbook.pdf` - the one-page printable playbook, the paper twin of this skill

## Important

This skill drafts documents. It is not legal advice. Two things to check every time:

- The designated national CSIRT and the exact submission channel change with each country's
  NIS2 transposition. Verify the recipient against the regulated client's national law
  before anything is sent.
- When you act as supply chain, the regulated client is the legal sender. You provide the
  content, they file it under their own name.

## License

Free to use and adapt.
