# test-java-monorepo

A personal playground for exploring how to structure a **Java monorepo** with
multiple apps and libraries — different builds, different release cadences, and
a mix of modules that are published as artifacts vs. modules that are not.

This repository is a sandbox. It is intentionally not a product, framework, or
template. It exists so I can experiment, break things, and learn.

## What I'm exploring

- Multi-module layout in Maven for a repo that contains both **applications**
  and **shared libraries**.
- **Per-module release pipelines** — modules versioned and released
  independently rather than as one big lockstep release.
- **Selective publishing** — some library modules are published as artifacts
  for external consumption, while apps and internal-only libraries are
  deliberately *not* published.
- General monorepo concerns in a JVM context: dependency hygiene between
  modules, build-time scoping, CI strategies, and keeping the root build
  understandable as the repo grows.

## Tooling

- **Build tool:** [Apache Maven](https://maven.apache.org/) with a parent POM
  and `<modules>` aggregation. Per-module publish/no-publish is handled via the
  Maven Deploy Plugin (`<skip>true</skip>` on modules that should not be
  released).
- **JDK:** 25
- **Publishing target:** TBD — undecided between Maven Central, GitHub
  Packages, or another registry. Configuration will land once I pick one.

## Layout (planned)

```
apps/    # runnable applications — not published
libs/    # shared libraries — some published, some internal-only
```

Specifics will appear and change as I experiment.

## Status

Early and shifting. Module names, structure, build conventions, and even the
overall layout may change without notice. Anything here is fair game to
rewrite or delete.

## Using this code

The repository as a whole is unlikely to be useful to anyone but me — it's a
collection of experiments rather than a coherent project.

That said, **individual pieces of code are absolutely free to borrow**, copy,
adapt, or learn from. If something here helps you, take it.

## License

Licensed under the **GNU General Public License v3.0**. See [LICENSE](LICENSE)
for the full text. Borrowing code is welcome under the terms of GPLv3.
