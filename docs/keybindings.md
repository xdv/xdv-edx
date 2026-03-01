# Keybindings

`xdv-edx` key handling is defined in `src/edx_editor.ds` and `src/edx_input.ds`.

## Key Classes

- `control`
- `motion`
- `edit`
- `printable`
- `unknown`

Classification entrypoint: `input_classify_key(key)`.

## Control Commands

- `Ctrl+Q`: quit request
- `Ctrl+S`: save
- `Ctrl+F`: search
- `Ctrl+G`: goto line
- `Ctrl+H`: help overlay

Control keys route through command/keypath dispatch (`run_key_command`).

## Navigation

- `Left Arrow`: move cursor left
- `Right Arrow`: move cursor right
- `Up Arrow`: move cursor up
- `Down Arrow`: move cursor down

Arrow keys are decoded from escape sequences in `edx_input.ds`.

## Editing Keys

- `Enter`: insert newline and move to start of next row
- `Backspace`: delete-left behavior with cursor-left update
- printable ASCII (`32..126`): insert character and move cursor right

## Keypath Helpers

`edx_input` provides packed keypath helpers for deterministic command routing:

- `input_pack_keypath(class, key)`
- `input_unpack_keyclass(packed)`
- `input_unpack_keyvalue(packed, class)`
- `input_keypath_for(key)`
