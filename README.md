# xdv-edx

Version: 0.1.0  
Status: Active  
Language: Dust Programming Language (DPL)

## Purpose

`xdv-edx` is the XDV full-screen terminal text editor for direct system maintenance and source editing in the K-domain runtime path.

## Editor Model

The editor provides:

- interactive full-screen editing
- file open and save workflows
- insert/delete/newline operations
- cursor movement across rows and columns
- command handling for save, quit, search, and go-to-line
- status and help overlays

## Source Layout

`src/edx_bridge.ds`  
OS integration bridge entrypoints.

`src/edx_main.ds`  
Editor startup and runtime orchestration.

`src/edx_editor.ds`  
Main editing loop and key dispatch.

`src/edx_screen.ds`  
Screen drawing and frame rendering.

`src/edx_buffer.ds`  
Text buffer operations and dirty-state tracking.

`src/edx_cursor.ds`  
Cursor state and movement operations.

`src/edx_input.ds`  
Key input decoding and command-line input support.

`src/edx_file.ds`  
File load/save and path workflows.

`src/edx_commands.ds`  
Editor command handlers.

`src/edx_search.ds`  
Search and match navigation operations.

`src/edx_status.ds`  
Status bar and state messaging.

`src/edx_help.ds`  
Help overlay rendering.

## Build

```bash
dust check xdv-edx/src
```
