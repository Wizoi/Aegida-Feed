# Aegida-Feed

A daily-updated, signed list of known scam websites, used by the Aegida phone app to recognise links in
messages. This repository holds only the published files; they are built elsewhere.

## What is published

The `gh-pages` branch is replaced once a day with:

| File | What it is |
|---|---|
| `feed.bin` | The list, about 9 MB. Each entry is an 8-byte SHA-256 prefix of a lower-case host name or a `host/path`, so the file contains no readable web addresses. |
| `feed.sig` | An ECDSA P-256 / SHA-256 signature of `feed.bin`. The app only uses a feed whose signature matches the key built into it. |
| `NOTICE.txt` | The licence notice for the data the list is derived from. |

Served at <https://wizoi.github.io/Aegida-Feed/>.

## Where the data comes from

Derived from [Phishing.Database](https://github.com/Phishing-Database/Phishing.Database) (MIT licence;
see `site/NOTICE.txt`): its active phishing domain list and active phishing link list. Domains that many
unrelated people publish on (for example a site-builder or a link shortener) are left out of the host list so
one bad page does not flag the whole service.

## What this repository does not contain

No personal information, no user data and no app code. The app sends nothing to this site except an
ordinary download request for the two files.

## Using the feed

It is not documented for outside use and the format may change without notice. For general-purpose scam and
phishing data, use the Phishing.Database lists directly.
