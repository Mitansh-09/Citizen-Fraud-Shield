# Citizen Fraud Shield

AI-powered digital fraud detection platform built for **ET AI Hackathon 2026**, addressing Problem Statement 6: *AI for Digital Public Safety — Defeating Counterfeiting, Fraud & Digital Arrest Scams*.

## Problem

India lost over **Rs 1,776 crore** to "digital arrest" scams in just the first nine months of 2024 (Ministry of Home Affairs). These scams — fraudsters impersonating CBI, ED, or Customs officers over video call — are industrialised operations, yet citizens have no real-time tool to check a suspicious call or message before it's too late.

## What this does

- **Check a Message** — paste any call transcript or message. An 8-signal rule-based detection engine (authority impersonation, "digital arrest" threats, manufactured urgency, isolation tactics, ID/KYC bait, financial requests, parcel-scam narrative, money-laundering accusation) scores it 0–100 and returns a verdict: Scam Confirmed / Suspicious / Likely Safe, with plain-English reasoning and next-step guidance.
- **Evidence Board** — a fraud network graph visualising how individually-reported scam incidents cluster into organised campaigns by shared script patterns, timing, and phone-number formatting. The board is a static demo dataset for the prototype, not live report ingestion yet.
- **Optional settings** — the page works fully offline by default. If you add a Gemini API key in the settings panel, the app can generate richer explanation text for the current session.

## UI Notes

The page uses a more restrained civic-product layout instead of a theatrical evidence-board style, so the interface feels closer to a real public-facing tool and less like a generated demo.

## Why rule-based, not just LLM-only

The classifier works fully offline with zero API dependency — critical for a reliable live demo. An optional AI reasoning layer (Gemini API) can be enabled via the settings panel to generate richer natural-language explanations on top of the rule engine's findings, but the core verdict and confidence score never depend on network access or an API key.

## Tech Stack

- Vanilla HTML / CSS / JavaScript — zero build step, zero dependencies
- SVG-rendered evidence board (custom force-free clustered layout)
- Optional: Google Gemini API for AI-generated reasoning text

## Running locally

No installation needed. Open [index.html](index.html) directly in any browser.

## Deployment

Deployed as a static site — works on Vercel, Netlify, or GitHub Pages with zero configuration.

## Current scope / known limitations

- The evidence board uses a static demonstration dataset (11 synthetic linked reports across 3 campaign clusters) to illustrate the intended clustering logic — it does not yet ingest live report data.
- The rule-engine signal patterns are tuned against sample transcripts and known digital-arrest scam scripts; broader real-world coverage is a next step.
- No backend, persistence, or authentication layer — intentionally out of scope for prototype stage.

## Roadmap

- Live ingestion pipeline connecting to NCRP (cybercrime.gov.in) report data
- Graph-based similarity scoring (replacing static demo clusters) using shared entity extraction across reports
- Multi-language citizen advisory via WhatsApp/IVR
- Telecom-side integration for real-time call flagging

## Judging Criteria Mapping

| Criteria | How this addresses it |
|---|---|
| Innovation (25%) | Real-time signal-based detection at point of contact, not post-complaint investigation |
| Business Impact (25%) | Directly targets a Rs 1,776 crore/9-month fraud category with a near-zero-cost, offline-capable citizen tool |
| Technical Excellence (20%) | Reliable rule-engine core with optional AI augmentation; no single point of failure |
| Scalability (15%) | Static, dependency-free architecture deployable at zero marginal cost per user |
| User Experience (15%) | Single-action verdict, no account or setup required |

## Team

Built for ET AI Hackathon 2026.
