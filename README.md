# xdv-edx

Version: 0.1.x  
Status: Active  
Language: Dust Programming Language (DPL)

`xdv-edx` is the terminal editor subsystem for XDV OS.

## Current Scope

Current source provides:

- editor boot/launch lifecycle (`main -> boot -> init -> run`)
- render loop and key-dispatch structure
- cursor motion handling (left/right/up/down)
- text-buffer operation interfaces (insert/backspace/newline/dirty flag)
- file open/save interface hooks
- command handlers (save, quit, search, goto-line)
- status and help overlay plumbing

This package is currently a runtime model implementation for bare-metal
integration and command-path validation. Some storage/search behaviors are
minimal and are documented in `docs/`.

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
