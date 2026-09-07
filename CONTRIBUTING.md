# Contributing to OpenPhase Labs projects

This is the default guide for every OpenPhase Labs repository. **A repository
with its own `CONTRIBUTING.md` overrides this one** — read that instead, since
it will carry the rules specific to what that project is.

Most of our repositories are **contracts rather than applications**: schemas and
specifications that other people build against. That shapes what a good
contribution looks like. A change to a contract is a change to everyone's
interface, so the bar is "can an implementer read this and get it right without
asking," not "does it work on my machine."

---

## Code of conduct

Be respectful, be specific, and assume good intent. Disagree with the work, not
with the person. Hostile, harassing, or discriminatory behavior toward any
contributor will result in removal from the project. See
[CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md).

---

## Before you open a pull request

**Open an issue first for anything structural.** New files, new messages, a
change to an existing interface, or anything you would describe as "while I was
in there" — discuss it before writing it. Small fixes, typos, and documentation
corrections need no preamble; send them.

**Cite your source.** Where a project mirrors a published standard, every change
that touches the mirrored surface must cite the spec section it comes from.
Inventing a field because it seems useful is grounds for rejection — a contract
that drifts from the standard it claims to implement is worse than one that
lacks a field.

**One logical change per pull request.** Sprawling changes get sent back, not
because of size but because they cannot be reviewed or reverted independently.

---

## Compatibility

Our schemas evolve **additively**. Across every repository that publishes a
wire format:

- **Additions are non-breaking** and welcome: new messages, new fields with new
  numbers, new enum values.
- **Field numbers are permanent.** Once published, a number is never reused or
  renumbered. Removing a field is acceptable; reusing its number is not — old
  peers will silently misread the new meaning.
- **Renaming an identifier is breaking**, even though the wire is unaffected.
  Generated code imports by name.
- Anything breaking requires a new version, and the previous version stays
  available.

If you are proposing a breaking change, propose the migration story with it.

---

## Branch and commit workflow

- **Branch from the repository's default branch.** Name it for the work:
  `feat/vendor-extensions`, `fix/preempt-units`, `docs/ingestion-guide`.
- **Atomic commits.** Each commit should leave the repository in a working
  state — schemas that compile, docs that match the schemas.
- **Commit message format:**

  ```
  <area>: short imperative summary (<= 70 chars)

  Optional body explaining WHY, wrapped at ~72 chars. Reference issues
  as #123. For schema changes, cite the spec section being implemented
  or clarified.
  ```

  The subject says what changed; the body says why it changed. The diff already
  shows the what.

---

## Pull request checklist

- [ ] Schemas compile cleanly with the repository's own tooling
- [ ] Documentation updated in the same change — a doc that describes the
      previous shape is worse than no doc, because it is believed
- [ ] Every new field cites its spec source, with units and valid range where
      the source constrains them
- [ ] Breaking changes are called out explicitly, with a migration story
- [ ] The description explains the *why*, not just the *what*

---

## Reporting issues

- **Bugs and spec ambiguities:** open an issue naming the file and line, and
  what you expected versus what you found.
- **Interop bugs against a consumer:** open the issue in that consumer's
  repository, unless the contract itself is wrong.
- **Security vulnerabilities:** do **not** open a public issue. See
  [SECURITY.md](SECURITY.md).

---

## License and contribution terms

OpenPhase Labs projects are published under the **Mozilla Public License 2.0**
unless a repository states otherwise; see that repository's `LICENSE`.

By submitting a contribution you agree that:

1. Your contribution is licensed under the same license as the project.
2. You have the right to make it — you are the author, or your employer's IP
   policy permits it.

There is no Contributor License Agreement. If one is ever introduced, existing
contributors will be told before it applies.
