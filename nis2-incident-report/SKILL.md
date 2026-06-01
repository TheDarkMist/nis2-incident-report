---
name: nis2-incident-report
description: >-
  Drafts NIS2 incident reports for a small WordPress agency or freelancer, especially
  one acting as supply chain to a regulated client rather than as a regulated entity
  itself. Use this skill whenever someone needs to draft or produce a NIS2 incident
  notification: a 24-hour early warning, a 72-hour notification, a 30-day final or
  progress report, or a user-protection notice, after a security incident such as a
  breach, intrusion, malware, defacement, prolonged downtime, or data exposure on a
  WordPress site or on a client they support. Trigger it whenever the conversation
  mentions NIS2 reporting duties, CSIRT or authority notification, the 24h/72h/30-day
  deadlines, supply-chain reporting obligations, or "what and when do I have to report
  after we got hacked". It produces first drafts only: a human reviews, edits, and sends.
---

# NIS2 Incident Report

## What this does

This skill helps draft the incident reports required by NIS2 (Directive (EU) 2022/2555)
from the realistic position of a **small WordPress agency or freelancer**. Most of the
time that agency is not itself a regulated entity: it is pulled in as **supply chain** to
a client who is regulated. The reporting duty sits on the regulated entity, so when the
agency is supply chain the client is the legal sender and the agency feeds them the
content.

The output is always a **first draft**. A human reads it, fills the gaps, and decides
whether and when to send. This skill never sends anything and never decides on the
client's behalf. That separation is the whole point: an incident report drafted in a hurry
is exactly the kind of document that does damage if it goes out wrong, so the human stays
in the loop by design.

## Step 1: Identify which report is due

NIS2 does not ask for one report; it asks for a sequence with hard deadlines that all
count **from the moment the entity becomes aware** of the incident. Work out which one the
user needs before drafting anything. If it is unclear, ask.

| Report | Deadline | Legal basis | In one line |
| --- | --- | --- | --- |
| **Early warning** | within 24h | Art. 23(4)(a) | An alert, not a confession. Four fields, kept short. |
| **Notification** | within 72h | Art. 23(4)(b) | Severity, indicators of compromise, mitigations so far. |
| **Final / progress report** | by day 30 | Art. 23(4)(c) | Final report if closed; monthly progress report if still open. |
| **User-protection notice** | without undue delay | Art. 23(2) | Tell affected users the one concrete action to take. |

The authority may also request an intermediate report at any point before day 30.

## Step 2: Gather the incident notes

Ask for the facts of the incident, or work from notes the user already has. Expect some or
all of the fields below. Treat anything absent as **unknown**, never as zero or "fine":
the difference matters in a regulatory document.

- `incident`: short title or id
- `became_aware`: date, time, time zone (this starts every clock)
- `our_role`: `regulated entity` or `supply chain`
- `regulated_client`: name, jurisdiction, in scope (yes / no)
- `triage`: malicious cause suspected? service down over 30 min? personal data exposed?
  client is a regulated entity? (yes / no each)
- `timeline`: list of `{ time, event }`
- `impacted_services`: what was affected
- `data_involved`: data types touched; mark clearly if personal data
- `iocs`: IPs, file hashes, suspicious URLs
- `actions_taken`: containment and mitigation so far
- `root_cause`: if known
- `status`: `ongoing` or `closed` (with `closed_at` if closed)
- `contacts`: CSIRT, client, hoster, upstream vendor
- `user_action`: the concrete step users should take, if any

## Step 3: Draft the report

1. Read `references/report-templates.md` for the exact structure of the report you
   identified in Step 1. Each template keeps strictly to the fields the law asks for, with
   no padding: a regulator wants signal, not prose.
2. Read `references/csirt-by-country.md` to address the report to the right recipient. The
   national CSIRT of the client's jurisdiction is the recipient of the regulatory reports.
   If the jurisdiction is not in the list, say so and ask rather than guessing.
3. Start every draft with a short **"Gaps to fill before sending"** list that names the
   required fields still unknown. This turns the draft into a checklist for the human
   instead of hiding the holes.
4. Write in plain language, ready for a human to finish.
5. End every draft with this exact line, on its own:

   > DRAFT, requires human review and sign-off.

## Guardrails

These are not bureaucracy; each one prevents a specific way an incident report can backfire.

- **Facts only.** Never invent a detail. If a required field is missing, write
  "unknown / under investigation" and list it under *Gaps to fill before sending*. A
  confident-sounding guess in a regulatory document is worse than an honest gap.
- **Redact before it reaches the draft.** Do not ask for, or copy in, raw personal data or
  secrets (passwords, API keys, tokens). If the notes contain personal data, flag it and
  tell the human to redact before sending. A breach report must not become the next breach.
- **You draft, you do not send.** No message is final until a human signs off. This is why
  every draft ends with the sign-off line.
- **Name the sender.** When the agency is supply chain, state explicitly that the regulated
  client is the legal sender and the agency provides the content. Getting this wrong sends
  a notification from a party with no standing to send it.
- **Separate fact from assessment.** Do not overstate severity. Mark judgements as
  judgements, so the regulator can tell what is observed from what is inferred.
- **Right recipient.** Use the CSIRT for the client's jurisdiction. If it is unknown, ask;
  do not default to a familiar one.
