# Editor Flow

This document describes the current runtime path in `xdv-edx`.

## Entry

- `edx_bridge.ds`:
  - `init()`: emits bridge-online signal.
  - `launch(path)`: forwards to `main(path)`.
- `edx_main.ds`:
  - `main(path) -> boot(path)`.
  - `boot(path)`: `init()` then `launch(path)`.
  - `init()`: calls `editor_init()`.
  - `launch(path)`: calls `editor_open(path)` then `run()`.
  - `run()`: executes `editor_run_loop(DEFAULT_TICKS)`.

## Editor Loop

- `edx_editor.ds`:
  - `editor_init()` initializes screen, buffer, cursor, and ready status.
  - `editor_open(path)` opens file if path is provided.
  - `editor_run_loop(remaining_ticks)`:
    - renders frame,
    - reads one key,
    - dispatches key behavior,
    - recurses until tick window expires or quit path is requested.

## Input Dispatch

- Control keys:
  - `Ctrl+Q`: request exit
  - `Ctrl+S`: save
  - `Ctrl+F`: search
  - `Ctrl+G`: goto line
  - `Ctrl+H`: help
- Editing keys:
  - `Enter`: newline
  - `Backspace`: delete-left behavior
  - Arrow keys: cursor movement
  - Printable ASCII: insert char

## Current Limits

- File read/write paths are interface-level and currently write/read fixed-size
  buffers in the model implementation.
- Search path currently requires non-zero query pointer and does not yet expose
  full interactive query collection in this module.
