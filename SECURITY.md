# Security Policy

This is the default policy for repositories in the FLIMKit organisation that do not carry their own. [FLIMKit itself has a fuller one](https://github.com/FLIMKit/FLIMKit/blob/main/SECURITY.md), and it takes precedence for that repository.

These are academic research tools maintained by Alex Hunt at the Centre for Inflammation Research, University of Edinburgh, not commercial products with a security team behind them. Reports are handled on a best-effort basis, but they are taken seriously and they will get a reply.

## Reporting a vulnerability

**Do not open a public issue for a security problem.**

Use one of these instead:

1. GitHub's private vulnerability reporting, from the Security tab of the repository in question.
2. Email alexander.hunt@ed.ac.uk with `FLIMKit security` in the subject line.

Please include what the problem is and what an attacker gets out of it, the version and platform you saw it on, and steps to reproduce. If a malformed input file triggers it, a minimal file or a generator script is far more useful than a description.

Expect acknowledgement within 7 days and an assessment within 30. This is a single-maintainer project, so if you have not heard back in that window, send a follow-up rather than assuming it was ignored. Credit goes in the advisory unless you would rather stay anonymous.

## Scope

These tools run locally on data you point them at. The realistic risk is a hostile or corrupt input file, not a remote attacker.

In scope: code execution, memory corruption or path traversal from parsing a data file; code execution or file overwrite from loading a session, project or config file; insecure handling of credentials or signing material in build scripts.

Out of scope: crashes or unhandled exceptions on malformed files with no path to code execution or data loss, which are ordinary bugs and still worth an issue; running out of memory on a large file; anything requiring an attacker who already has your user account on the machine.

A plugin loaded from `~/.flimkit/plugins` is ordinary Python running with your privileges. There is no sandbox, and a plugin misbehaving is not a vulnerability. A way to get one loaded without the setting being on is.
