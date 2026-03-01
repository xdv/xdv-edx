# Editor Flow

This document describes the runtime path in `xdv-edx`.

## Entry

- `edx_bridge.ds`
  - `init()`: bridge online signal.
  - `launch(path)`: forwards to `main(path)`.
- `edx_main.ds`
  - `main(path) -> boot(path)`.
  - `boot(path)`: `init()` then `launch(path)`.
  - `init()`: `editor_init()`.
  - `launch(path)`: `editor_open(path)` then `run()`.
  - `run()`: executes `editor_run_loop(DEFAULT_TICKS)`.

## Deterministic Loop Model

`edx_editor.ds` uses packed loop state:

- `loop_state` (`running` or `exit requested`)
- `buffer_model` (`clean` or `dirty`)

Flow per tick:

1. render frame,
2. read key,
3. classify key (`control`/`motion`/`edit`/`printable`),
4. route command path,
5. apply buffer-model transition,
6. recurse with next packed state.

## Input and Command Path

- `Ctrl+Q` -> quit request
- `Ctrl+S` -> save via command plane
- `Ctrl+F` -> search command
- `Ctrl+G` -> goto command
- `Ctrl+H` -> help overlay

Editing/motion keys are handled in deterministic key-class branches.

## Render Model

`edx_screen` renders with buffer-aware row selection:

- computes visible text rows,
- draws content rows for current buffer line-count window,
- fills remaining rows with `~`,
- draws status bar/message and positions cursor.

## File IO and xdvfs Contract

`edx_file` enforces xdvfs path contract checks before open/save:

- path normalization (`file_resolve_path`),
- contract kind detection (`file_path_contract_kind`),
- validation gate (`file_validate_xdvfs_path`),
- then read/write + buffer binding.

## Regression Coverage

Regression coverage is implemented in:

- `edx_buffer_tests.ds`
- `edx_input_tests.ds`
- `edx_file_tests.ds`
- `edx_commands_tests.ds`
- `edx_editor_tests.ds`
- `edx_main_tests.ds` (aggregate)
