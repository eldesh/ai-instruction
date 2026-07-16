# AGENTS.md

## General principles

* Understand the relevant code, documentation, conventions, and constraints before making changes.
* Optimize for the intended final design, not merely for the smallest possible diff.
* Make only changes that are necessary for the requested outcome.
* Preserve existing behavior unless the task intentionally changes it.
* Prefer simple, explicit solutions over unnecessary abstraction or speculative flexibility.
* Do not hide uncertainty. State assumptions and unresolved issues when they affect the result.

## Project conventions

* Follow repository-local instructions and established conventions.
* Use the project's existing tools and workflows when they are available.
* Do not introduce a new dependency, tool, framework, or convention without a clear need.
* Keep configuration, documentation, implementation, and tests consistent with one another.
* Do not modify unrelated user changes.
* Match the style and idioms of the surrounding code unless the task explicitly requires changing them.

## Code organization

* Keep files, directories, functions, types, and modules focused on clear responsibilities.
* Split code when a unit contains multiple separable responsibilities.
* Prefer coherent restructuring over local patching when the current structure no longer matches the code's responsibilities.
* Add, move, or remove files when doing so makes ownership and boundaries clearer.
* Keep names precise and domain-oriented.
* Prefer small functions with clear inputs, outputs, and side effects.
* Avoid duplication when a shared concept can be expressed clearly in one place.

## Comments and documentation

* Document public behavior, important invariants, non-obvious constraints, and design decisions.
* Explain meaning, responsibility, or intent rather than restating the implementation.
* Update documentation when behavior, interfaces, workflows, or user-facing examples change.
* Keep examples accurate and executable where practical.

## Testing and verification

* Add or update tests for behavior changes and bug fixes.
* Prefer focused tests that verify observable behavior.
* Cover relevant boundary conditions, failure paths, and regressions.
* Run the repository's applicable formatting, linting, type-checking, testing, and build checks.
* Use the narrowest useful checks during development, then run the broader relevant checks before completion.
* Report checks that were not run and the reason they were omitted.
* Do not rely only on manual verification when the behavior can be tested automatically.

## Generated files and dependencies

* Do not edit generated artifacts as source; update their source and regenerate them with the project's tooling.
* Commit generated artifacts only when the repository expects them to be committed.
* Keep dependency declarations and lockfiles synchronized.
* Avoid unrelated dependency updates.

## Version control

* Keep commits focused and internally consistent.
* Do not include unrelated changes in a commit.
* Do not leave mechanical, temporary, or fixup-style commits in the final history when history editing is appropriate and safe.
* Do not rewrite shared history or discard existing work without explicit authorization.
