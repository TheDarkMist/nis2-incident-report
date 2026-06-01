# NIS2 report templates

The four reports NIS2 asks for, with the legal basis and the exact fields to draft. Keep to
the fields the law asks for, no padding. Each clock counts from the moment the entity
becomes aware of the incident.

## Contents

- [Early warning (24h)](#early-warning-24h)
- [Notification (72h)](#notification-72h)
- [Final / progress report (30d)](#final--progress-report-30d)
- [User-protection notice](#user-protection-notice)

---

## Early warning (24h)

**Legal basis:** Art. 23(4)(a). Due within 24 hours of becoming aware.

This is an alert, not a confession. "Still investigating" is a valid answer. Keep it short.
Only four things are required:

- **Malicious cause:** yes / no / unknown
- **Cross-border impact:** yes / no / unknown
- **Known impact:** one line on what is affected so far
- **Contact:** a contact person plus an alternate

**Template**

```
To: [national CSIRT of the client's jurisdiction, via the regulated client if supply chain]
Subject: Early warning - [incident]

Gaps to fill before sending:
- [required fields still unknown]

- Malicious cause suspected: [yes / no / unknown]
- Cross-border impact: [yes / no / unknown]
- Known impact: [one line]
- Contact: [name, role, email/phone] / Alternate: [name, role, email/phone]

DRAFT, requires human review and sign-off.
```

---

## Notification (72h)

**Legal basis:** Art. 23(4)(b). Due within 72 hours of becoming aware. The authority may
request an intermediate report at any time before day 30.

Builds on the early warning with substance:

- **Severity assessment:** scale of impact, users/services affected, duration
- **Indicators of compromise (IOCs):** IPs, file hashes, suspicious URLs
- **Mitigations applied:** containment and remediation done so far
- **Current status:** ongoing or closed

**Template**

```
To: [national CSIRT of the client's jurisdiction, via the regulated client if supply chain]
Subject: Incident notification - [incident]

Gaps to fill before sending:
- [required fields still unknown]

- Severity assessment: [impact, scope, duration; mark judgements as judgements]
- Indicators of compromise: [IPs, hashes, URLs]
- Mitigations applied: [actions taken]
- Current status: [ongoing / closed, with closed-at time if closed]

DRAFT, requires human review and sign-off.
```

---

## Final / progress report (30d)

**Legal basis:** Art. 23(4)(c). Due by day 30.

Which template you use depends on whether the incident is closed.

**If closed - final report:**

- Root cause
- Full timeline
- Mitigation status
- Cross-border impact

**If still open - progress report:** a monthly update until it closes, stating what is
known, what is still open, and the expected next update. The final report is then due
within a month of closing.

**Template (closed)**

```
To: [national CSIRT of the client's jurisdiction, via the regulated client if supply chain]
Subject: Final report - [incident]

Gaps to fill before sending:
- [required fields still unknown]

- Root cause: [what allowed the incident]
- Timeline: [from became-aware to resolution]
- Mitigation status: [what is fixed, what remains]
- Cross-border impact: [yes / no / unknown, with detail]

DRAFT, requires human review and sign-off.
```

**Template (open - progress)**

```
To: [national CSIRT of the client's jurisdiction, via the regulated client if supply chain]
Subject: Progress report - [incident]

Gaps to fill before sending:
- [required fields still unknown]

- What is known: [confirmed facts]
- What is still open: [under investigation]
- Expected next update: [date]

DRAFT, requires human review and sign-off.
```

---

## User-protection notice

**Legal basis:** Art. 23(2). Send without undue delay when users can take a concrete
action to protect themselves: change a password, rotate an API key, watch for phishing.

In supply chain, the regulated client is the sender; the technical content comes from the
agency. No technical detail the user cannot act on.

**Template**

```
To: [affected users, sent by the regulated client]
Subject: [plain-language heading]

- What happened: [one line]
- What to do now: [the single concrete action]
- Where to get help: [contact or link]

DRAFT, requires human review and sign-off.
```
