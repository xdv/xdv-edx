# Module Reference

## Lifecycle and bridge

- `src/edx_bridge.ds`
  - xdv-os integration bridge entrypoints (`init`, `launch`).
- `src/edx_main.ds`
  - editor process lifecycle orchestration.

## Editor core

- `src/edx_editor.ds`
  - deterministic loop state packing/unpacking,
  - key-class dispatch,
  - command keypath routing,
  - buffer-model transition flow.
- `src/edx_commands.ds`
  - command wrappers (`save`, `quit`, `search`, `goto`),
  - key-to-command mapping (`command_from_key`),
  - key command dispatcher (`run_key_command`).

## UI and interaction

- `src/edx_screen.ds`
  - buffer-aware frame rendering, status rendering, cursor placement.
- `src/edx_status.ds`
  - status-line and message color/error output path.
- `src/edx_help.ds`
  - help overlay output behavior.
- `src/edx_input.ds`
  - key read/decode, key classification, keypath pack/unpack.

## Data and navigation

- `src/edx_buffer.ds`
  - deterministic clean/dirty model,
  - keypath model transitions,
  - write-size and line-count model helpers.
- `src/edx_cursor.ds`
  - cursor row/column movement with screen bounds.
- `src/edx_search.ds`
  - search-next/prev/find-all hooks.
- `src/edx_file.ds`
  - file open/save workflows with xdvfs path contract validation.

## Regression Tests

- `src/edx_buffer_tests.ds`
- `src/edx_input_tests.ds`
- `src/edx_file_tests.ds`
- `src/edx_commands_tests.ds`
- `src/edx_editor_tests.ds`
- `src/edx_main_tests.ds`
