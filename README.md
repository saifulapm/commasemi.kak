# commasemi.kak

A Kakoune plugin for smart toggling of comma and semicolon at the end of lines. Handles comments across multiple languages intelligently.

## ✨ Features

- Toggle between comma and semicolon at line endings
- Preserves and skip inline comments
- Smart toggle behavior:
  - If no punctuation exists → adds the character
  - If same character exists → removes it
  - If different character exists → replaces it
- Works with multiple comment styles across languages via kakoune `%opt{comment_line}` option.
- Supports JavaScript, TypeScript, PHP, Python, Ruby, Rust, Go, C/C++, Lua, HTML, CSS, and more

## Install

Add `commasemi.kak` to your autoload dir: `~/.config/kak/autoload/`.

Or via [kak-bundle](https://codeberg.org/jdugan6240/kak-bundle):

```
bundle commasemi https://github.com/saifulapm/commasemi.kak %{
  # Suggested mappings
  map global normal <c-,> ':toggle-comasemi ,<ret>' -docstring 'toggle comma'
  map global normal <c-\;> ':toggle-comasemi \;<ret>' -docstring 'toggle semicolon'
  map global insert <c-,> '<a-;>:toggle-comasemi ,<ret>' -docstring 'toggle comma'
  map global insert <c-\;> '<a-;>:toggle-comasemi \;<ret>' -docstring 'toggle semicolon'
}
```

# Note:

This plugin relies on Kakoune’s built-in `comment_line` option to detect and skip
commented lines. As a result, it automatically adapts to the active filetype and
works correctly with languages that define their comment prefix (e.g. //, #, --, etc.).
if any lang `comment_line` opt not set, this may not work properly.

## Similar neovim plugin

- [commasemi.nvim](https://github.com/saifulapm/commasemi.nvim)
