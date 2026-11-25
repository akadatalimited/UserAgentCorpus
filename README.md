# UserAgentCorpus — Proposed Expansion (PRIVATE DRAFT, NOT PUBLISHED)

A deduplicated collection of **145,880** real-world HTTP `User-Agent`
strings observed by services operated by AKADATA LIMITED.

This is a data collection, not a classification project. One string per
record, nothing else. No IP addresses, timestamps, counts, attributions
or other observation metadata are included.

**Status: release-ready draft, private only. No publication yet.**

## Contents (this directory, private draft)

- `user-agents.csv` — single column (`user_agent`), 145,880 records + header.
  Alphabetically sorted A–Z (case-insensitive, deterministic tie-break),
  exact-string deduplicated, original capitalisation/punctuation/spacing
  preserved, UTF-8, LF line endings, RFC 4180 quoting.
- `SHA256SUMS` — SHA-256 checksum of the CSV.
- `README.md` (this file), `MANIFEST.json` — documentation and build manifest
  (public-safe: no private infrastructure details).

## Origins

- Original 53,809 records: [https://www.az2.co.uk/](https://www.az2.co.uk/), an
  online shopping and product discovery platform, supplemented by our CVE
  intelligence service ([https://cve.akadata.co.uk/](https://cve.akadata.co.uk/)).
  The combined research drew upon more than twelve million HTTP traffic
  observations (see published v1 README).
- Expansion +92,071 records: further historical acquisition across production
  services operated by AKADATA LIMITED, on the order of tens of millions of
  additional HTTP observations. No per-request metadata is published.

The observed traffic included consumers, web browsers, legitimate search
engine crawlers, AI crawlers, automated bots, scrapers, security scanners
and other automated clients, including traffic that we might ordinarily
prefer to block. Such traffic was not universally excluded, allowing the
collection to capture a broader representation of real-world HTTP clients.

## A note on what these strings are

These are strings genuinely observed in HTTP requests, not necessarily
genuine representations of the software making those requests.
User-Agent headers can be spoofed, fabricated or misleading: a string
claiming to be an ordinary browser may be sent by a bot, a scanner, or
anything else. Treat every record as *claimed* identity, never proof.

The dataset does not claim to identify every User-Agent in existence.

## Privacy

Each string was audited before proposal. Records containing internal
operational strings, template placeholders, control characters, personal
email addresses, credentials or tokens, MAC addresses, long digit runs,
IP addresses, private hostnames, spreadsheet formula triggers or
overlong values were excluded entirely — never modified. Full exclusion
accounting (1,476 candidates) is retained privately and was verified to
contribute zero records to this CSV. No traffic counts, timestamps, IP
addresses, geographical information, source attribution or other metadata
is published. A small number of bot operator contact addresses remain
exactly as their operators publish them inside their own User-Agent
strings (as in v1); no personal data was found in the collection.

## Intended uses

Software development, HTTP parser testing, security research, traffic
analysis and machine learning.

## Licence (proposed)

- `user-agents.csv` and `SHA256SUMS` — To the extent AKADATA LIMITED holds
  any copyright or database rights in the selection and arrangement of this
  collection, those rights are dedicated to the public domain under
  CC0-1.0. This dedication applies only to rights AKADATA LIMITED holds in
  the dataset and does not purport to transfer, license or claim ownership
  of any rights in the individual third-party user-agent strings themselves
  (including any product names or trademarks they may contain), which remain
  with their respective owners.
- `README.md` — MIT, Copyright (c) 2026 AKADATA LIMITED.

## Verification (private)

```sh
sha256sum -c SHA256SUMS
```

Expected: `user-agents.csv: OK`
(`df80489db9918662f7bdc2c914a4a34dd92719b745c82248553398fef59ede68`).

---

AKADATA LIMITED — Proudly Made in England. (Private draft.)
