# XDV EDX Changelog

## 2026-02-28

### Changed

- Stabilized editor input/render/buffer model:
  - added deterministic key classification and keypath helpers in `src/edx_input.ds`,
  - added explicit buffer model transitions (`clean`/`dirty`) in `src/edx_buffer.ds`,
  - refactored editor loop and key dispatch to packed deterministic state flow in `src/edx_editor.ds`,
  - aligned render path to buffer-aware row model in `src/edx_screen.ds`.

- Integrated file IO with xdvfs path contracts in `src/edx_file.ds`:
  - path normalization,
  - path-kind detection,
  - xdvfs contract validation gate before open/save,
  - default editor path resolution for console profile.

- Refactored command plane in `src/edx_commands.ds`:
  - key-to-command mapping,
  - key command dispatch entrypoint,
  - deterministic command status behavior.

### Added

- Added command/keypath regression tests:
  - `src/edx_buffer_tests.ds`
  - `src/edx_input_tests.ds`
  - `src/edx_file_tests.ds`
  - `src/edx_commands_tests.ds`
  - `src/edx_editor_tests.ds`
  - `src/edx_main_tests.ds` aggregate test runner.

- Updated docs:
  - `docs/editor_flow.md`
  - `docs/keybindings.md`
  - `docs/module_reference.md`
  - `docs/README.md`

## 2026-02-21

### Added

- Added `docs/` documentation set:
  - `docs/README.md`
  - `docs/editor_flow.md`
  - `docs/module_reference.md`
  - `docs/keybindings.md`
- Added `changelog.md`.

### Changed

- Reworked `README.md` to match current implementation scope:
  - clarified lifecycle/loop model behavior,
  - documented current interface-level limits for file/search paths,
  - added documentation index and build command.
