---
name: Bug report
about: Something in a schema, specification, or document is wrong
title: ''
labels: ''
assignees: ''

---

**Where**
File and line, message or field name. Be exact — `spat.proto` `TimingConfidence`
is findable; "the SPaT stuff" is not.

**What it says now**
Quote it.

**What is wrong with that**
The observed behavior versus what you expected, or the contradiction you found.
If it disagrees with a published standard, cite the section — NTCIP 1202 §X.Y,
J2735 §A.B, IHR (Purdue 2012) event N.

**How you hit it**
What you were building when this came up: generating stubs, implementing a
consumer, reading the spec to build against it. If there are steps to reproduce,
give them.

**Impact**
Who gets this wrong because of it, and what happens when they do. A field
documented under the wrong name costs an implementer an afternoon; a trust
boundary described incorrectly costs more.

**Anything else**
Version or commit you are reading, and any other context.
