# Spamhaus DROP Lists

A mirror of the Spamhaus **DROP** ("Don't Route Or Peer") lists. These are netblocks and ASNs
that are hijacked or leased by professional spam and cyber-crime operations: malware
distribution, botnet controllers and the like. They are meant for firewalls and routers to drop
all traffic to and from these networks.

## Files

| File | Contents | Raw URL |
|---|---|---|
| `drop.txt` | DROP, IPv4 netblocks (includes the former EDROP) | https://raw.githubusercontent.com/SecOps-Institute/SpamhausIPLists/master/drop.txt |
| `drop_ipv6.txt` | DROPv6, IPv6 netblocks | https://raw.githubusercontent.com/SecOps-Institute/SpamhausIPLists/master/drop_ipv6.txt |
| `asn_drop.json` | ASN-DROP, malicious or hijacked ASNs | https://raw.githubusercontent.com/SecOps-Institute/SpamhausIPLists/master/asn_drop.json |
| `edrop.txt` | Empty (see below), kept so existing links don't break | https://raw.githubusercontent.com/SecOps-Institute/SpamhausIPLists/master/edrop.txt |
| `Last-Checked-At` | Time of the last successful check (IST) | |

**Format of the `.txt` files:** one CIDR per line. Entries are normalized, deduplicated and
sorted numerically, with Spamhaus's `; SBL…` reference comments removed.

**Format of `asn_drop.json`:** Spamhaus's NDJSON, mirrored as-is. Each line is one object such as
`{"asn":…, "rir":…, "domain":…, "cc":…, "asname":…}`, and the last line is a
`{"type":"metadata",…}` record.

> **EDROP has been merged into DROP by Spamhaus.** `edrop.txt` is now empty, so use `drop.txt`.
> The old `asn_drop.txt` has been removed; the ASN list is `asn_drop.json`.

## How it is built

- Source: https://www.spamhaus.org/drop/. The files are `drop.txt`, `dropv6.txt`, `edrop.txt`
  and `asndrop.json`.
- `asn_drop.json` is checked before publishing: every line must be valid JSON, and the number of
  ASNs must match Spamhaus's own metadata count.

## Update schedule

**mirabot**, an automated bot, checks Spamhaus **every hour**:
- `Last-Checked-At` is updated on every successful check.
- The lists change only when Spamhaus changes them, so this repo's commit history doubles as a
  change log.

Before publishing, the bot checks each update for problems: minimum size, malformed data, and
any sudden drop of more than half the entries. If a check fails, the previous list stays in
place. If `Last-Checked-At` is more than a few hours old, an update is being held back or the
bot is down.

## Using DROP

Spamhaus recommends DROP for core routers and firewalls. It only lists address space that is
allocated directly by a Regional Internet Registry and controlled by criminals, never a
legitimate network's space. See the [DROP FAQ](https://www.spamhaus.org/faq/section/DROP%20FAQ).

## License

MIT for this repository's packaging. **The data belongs to The Spamhaus Project and is subject to
the [Spamhaus DROP terms of use](https://www.spamhaus.org/drop/terms/).**

---
Updated hourly by **mirabot**, sponsored by [endlesstokens.ai](https://endlesstokens.ai) — *Pay for Time not Tokens*.

Maintained by [SecOps Institute](https://github.com/SecOps-Institute) ·
[LinkedIn](https://www.linkedin.com/in/aarvee11) · [Blog](https://amisafe.secops.in)
