# Target-scoped AGENTS.md discovery

* After identifying the files that may need to change and before modifying them, check for instruction files from the project root through each target file's parent directory.
* In each directory, use `AGENTS.override.md` when it exists; otherwise, use `AGENTS.md` when it exists.
* Apply the selected instructions from the project root toward the target file. When instructions conflict, the instruction closest to the target file takes precedence.
* Repeat this check when the set of target files changes.
* Do not load instructions from subdirectories unrelated to the target files.
