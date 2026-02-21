# Keybindings

`xdv-edx` key handling is defined in `src/edx_editor.ds` and `src/edx_input.ds`.

## Control commands

- `Ctrl+Q`: quit request
- `Ctrl+S`: save
- `Ctrl+F`: search
- `Ctrl+G`: goto line
- `Ctrl+H`: help overlay

## Navigation

- `Left Arrow`: move cursor left
- `Right Arrow`: move cursor right
- `Up Arrow`: move cursor up
- `Down Arrow`: move cursor down

Arrow keys are decoded from escape sequences in `edx_input.ds`.

## Editing keys

- `Enter`: insert newline
- `Backspace`: delete one character backward
- printable ASCII (`32..126`): insert character

## Notes

- Unknown/non-printable keys outside mapped controls are ignored by the editor
  loop in the current implementation.
