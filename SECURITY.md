# Security Policy

This policy applies to every OpenPhase Labs repository unless that repository
publishes its own.

## Reporting a vulnerability

**Do not open a public issue.**

Email **admin@openphase-labs.com** with:

- the repository and the file or message involved
- what an attacker can do with it
- the steps to reproduce, or the reasoning if it is a design flaw rather than a
  bug

You will get an acknowledgement within **72 hours**. We will tell you what we
intend to do and roughly when, and we will tell you when a fix ships.

We will not take legal action against anyone who reports a vulnerability in good
faith, who does not access or modify data belonging to anyone else, and who
gives us a reasonable opportunity to fix the problem before disclosing it
publicly.

## What counts as a vulnerability here

Most of what we publish is a **contract** — schemas and specifications that
implementers build against. Contracts have their own kind of security flaw, and
these are in scope:

- A schema or specification that leads a correct implementation into an unsafe
  one: a field that invites credentials or tokens onto the wire, an
  authentication or authorization boundary that is described ambiguously enough
  to be implemented wrongly, or a default that is unsafe when followed.
- A trust boundary the specification states but does not actually hold.
- A message shape that permits an untrusted party to assert something the
  specification claims only a trusted party can assert.

Also in scope, in the ordinary way: vulnerabilities in any code we publish.

**Out of scope:** vulnerabilities in someone else's implementation of one of our
contracts. Report those to whoever ships that software. If their bug was caused
by our specification being wrong or unclear, we want to hear about that part —
that is a contract flaw and it is in scope.

## Supported versions

Contract versions remain available indefinitely once published, but security
fixes land on the current version. Where a fix cannot be made without a breaking
change, we will say so plainly rather than quietly changing the meaning of an
existing field.
