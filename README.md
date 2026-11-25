# UserAgentCorpus

A simple, deduplicated collection of **53,809** real-world HTTP `User-Agent`
strings observed by services operated by AKADATA LIMITED.

This is a data collection, not a classification project. One string per
record, nothing else.

## Contents

- `user-agents.csv` — single column (`user_agent`), 53,809 records + header.
  Alphabetically sorted A–Z (case-insensitive, deterministic tie-break),
  exact-string deduplicated, original capitalisation/punctuation/spacing
  preserved, UTF-8, LF line endings, RFC 4180 quoting.
- `SHA256SUMS` — SHA-256 checksum of the CSV.
- `README.md`, `LICENSE` — this documentation and the licence terms.

## Origins

The primary source is [https://www.az2.co.uk/](https://www.az2.co.uk/), an
online shopping and product discovery platform operated by AKADATA LIMITED.

The observed traffic included consumers, web browsers, legitimate search
engine crawlers, AI crawlers, automated bots, scrapers, security scanners
and other automated clients, including traffic that we might ordinarily
prefer to block. Such traffic was not universally excluded during the
observation period, allowing the collection to capture a broader
representation of real-world HTTP clients.

The collection was subsequently supplemented with additional User-Agent
strings observed by our CVE intelligence service:

[https://cve.akadata.co.uk/](https://cve.akadata.co.uk/)

The combined research draws upon more than twelve million HTTP traffic
observations.

## A note on what these strings are

These are strings genuinely observed in HTTP requests, not necessarily
genuine representations of the software making those requests.
User-Agent headers can be spoofed, fabricated or misleading: a string
claiming to be an ordinary browser may be sent by a bot, a scanner, or
anything else. Treat every record as *claimed* identity, never proof.

The dataset does not claim to identify every User-Agent in existence.

## Privacy

Each string was audited before publication. Records containing internal
operational strings, template placeholders, control characters, personal
email addresses, credentials or tokens, MAC addresses, long digit runs,
IP addresses, private hostnames, spreadsheet formula triggers or
overlong values were excluded entirely — never modified. No traffic
counts, timestamps, IP addresses, geographical information, source
attribution or other metadata is published. A small number of bot
operator contact addresses remain exactly as their operators publish
them inside their own User-Agent strings; no personal data was found
in the collection.

## Intended uses

Software development, HTTP parser testing, security research, traffic
analysis and machine learning.

## Acknowledgements

The collection originated during the development of UAThink, a native
User-Agent identity classifier by AKADATA LIMITED:

[https://github.com/akadatalimited/UAThink](https://github.com/akadatalimited/UAThink)

## Licence

- `user-agents.csv` and `SHA256SUMS` — CC0-1.0 (public domain dedication;
  no rights claimed over third-party strings, product names or trademarks).
- `README.md` — MIT, Copyright (c) 2026 AKADATA LIMITED.

See LICENSE for the full terms and scope.

## Verification

```sh
sha256sum -c SHA256SUMS
```

Expected: `user-agents.csv: OK`
(`7df8a217116ceb76a0574cdec723a8974e94d9205b01e507ba966b9bd56abb46`).

---

AKADATA LIMITED — Proudly Made in England.
