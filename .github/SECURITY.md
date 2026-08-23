# Security Policy

## Supported versions

| Version | Supported |
|---------|-----------|
| 5.x     | Yes       |
| < 5.0   | No        |

## Reporting a vulnerability

BenchBloom reads text files and compares their shingle sets. It does not
execute the corpora it audits, opens no sockets, and should never receive
secrets. If you find a security issue - for example a path traversal in the
corpus loader, a crash on hostile input, or a report that leaks file contents
beyond the record it flags - please report it privately with GitHub's
"Report a vulnerability" button on the Security tab.

We aim to acknowledge reports within 72 hours and to ship a fix or mitigation
in the next patch release. Please do not open a public issue before a fix is
available.
