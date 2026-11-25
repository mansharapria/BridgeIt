# BridgeIt

**From "I need help" to "I've reached out," one best-fit option at a time.**

BridgeIt is a mobile-friendly web guide for UCLA students who need mental health support beyond CAPS's short-term care. It asks a few questions, recommends one best-fit resource at a time with the reasons it fits, and drafts an editable email or call script so reaching out feels easier.

**Live prototype:** [bridgeit-ucla.vercel.app](https://bridgeit-ucla.vercel.app)

**Product requirements doc:** [docs/product-management/bridgeit-prd.md](docs/product-management/bridgeit-prd.md) ([PDF](docs/product-management/BridgeIt_PRD.pdf))

> Prototype for demonstration only. Not medical advice, and not for real use. In crisis? Call or text 988, or call UCLA CAPS 24/7 at 310-825-0768.

## The problem

CAPS offers 4 individual sessions a year, or 8 with UC SHIP. Students who need ongoing care are referred off campus, and from there they search, call and follow up on their own. In one published study, 42% of students referred off campus by a university counseling center never connected with a provider, and cost was the main barrier.

## What the prototype does

- **Guided intake:** student status, type of help, CAPS history, insurance, budget, format, location, availability and priorities. It never asks about symptoms or diagnoses.
- **Rule-based matching:** hard filters first (eligibility, insurance, budget, type of help, verification date), then ranking by the student's priorities.
- **One recommendation at a time:** each card shows why it fits, the cost, where, when, how to start and the source, with "Show me another" and a one-tap reason.
- **Outreach help:** an editable email or call script, pre-filled with the student's details, never including symptoms.
- **UC SHIP referral reminder,** an end-of-session "Did you reach out?" question, and an opt-in 14-day check-in.
- **Crisis resources on every screen.** No accounts and nothing stored.

## Product decisions

| Decision | Why |
|---|---|
| One option, not a list | Students already have lists. Fewer choices may reduce overwhelm. The tradeoff, less sense of choice, gets tested in beta. |
| Hard filters before ranking | Insurance, budget, eligibility and help type are never traded off. Therapy and peer groups aren't interchangeable. |
| Honest about unknowns | Unknown cost is never shown as free, and openings always say "confirm a spot." |
| Success means contact | The north star is students who report reaching out within 14 days (provisional target: 30%), not clicks. |

## Directory and verification

[`data/bridgeit_directory.csv`](data/bridgeit_directory.csv) lists every resource in the prototype: CAPS options, the UC SHIP referral path, low-cost and sliding-scale clinics, county services and peer support groups. Each live listing was checked on the organizer's own website, and the check date is recorded. Listings that couldn't be confirmed, or that are meant for family members, are held back with the reason noted.

## Repository

```
app/                      The prototype: a single self-contained web page
  index.html
  logo.png
  favicon.png
data/
  bridgeit_directory.csv  Resources used by the prototype, with sources and check dates
docs/
  product-management/     PRD (Markdown and PDF)
```

To run the prototype locally, open `app/index.html` in a browser.

## Status

Working prototype with PRD v0.2, November 2026. Next steps: discovery interviews with UCLA students, a clinical review of the crisis flow, and a small invited beta.
