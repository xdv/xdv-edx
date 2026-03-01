# xdv-edx

Version: 0.2.x  
Status: Active  
Language: Dust Programming Language (DPL)

`xdv-edx` is the terminal editor subsystem for XDV OS.

## Current Scope

Current source provides:

- deterministic input classification (`control`, `motion`, `edit`, `printable`)
- deterministic command/keypath dispatch (`run_key_command`, `run_command`)
- deterministic buffer model (`clean/dirty`) with explicit transition helpers
- render path aligned to buffer line model and cursor positioning
- xdvfs path-contract validation for file open/save
- editor lifecycle (`main -> boot -> init -> launch -> run`)

## xdvfs Path Contract

`edx_file` enforces xdvfs-oriented path normalization and contract checks before
open/save. Default path resolution uses the editor default path profile in the
`/console` contract space.

## Regression Tests

The following test modules are included in `src/`:

- `edx_buffer_tests.ds`
- `edx_input_tests.ds`
- `edx_file_tests.ds`
- `edx_commands_tests.ds`
- `edx_editor_tests.ds`
- `edx_main_tests.ds` (aggregate runner)

## Source Layout

- `src/edx_main.ds`
- `src/edx_bridge.ds`
- `src/edx_editor.ds`
- `src/edx_screen.ds`
- `src/edx_buffer.ds`
- `src/edx_cursor.ds`
- `src/edx_input.ds`
- `src/edx_file.ds`
- `src/edx_commands.ds`
- `src/edx_search.ds`
- `src/edx_status.ds`
- `src/edx_help.ds`

## Build

```bash
dust check xdv-edx/src
```

## Documentation

- `docs/README.md`
- `docs/editor_flow.md`
- `docs/module_reference.md`
- `docs/keybindings.md`
- `changelog.md`
