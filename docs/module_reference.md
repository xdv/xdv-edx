# Module Reference

## Lifecycle and bridge

- `src/edx_bridge.ds`
  - xdv-os integration bridge entrypoints (`init`, `launch`).
- `src/edx_main.ds`
  - editor process lifecycle orchestration.

## Editor core

- `src/edx_editor.ds`
  - main loop, key dispatch, save/open handling, command routing.
- `src/edx_commands.ds`
  - command wrappers (`save`, `quit`, `search`, `goto`).

## UI and interaction

- `src/edx_screen.ds`
  - frame drawing and cursor positioning.
- `src/edx_status.ds`
  - status-line and message color/error output path.
- `src/edx_help.ds`
  - help overlay output behavior.
- `src/edx_input.ds`
  - key read, escape-sequence decode, printable checks.

## Data and navigation

- `src/edx_buffer.ds`
  - buffer change interfaces and dirty-state signaling.
- `src/edx_cursor.ds`
  - cursor row/column movement with screen bounds.
- `src/edx_search.ds`
  - search-next/prev/find-all interface hooks.
- `src/edx_file.ds`
  - file open/save interface hooks.
