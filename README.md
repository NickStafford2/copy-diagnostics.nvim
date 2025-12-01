# nvim-copy-diagnostics

A tiny Neovim plugin that copies diagnostics to your system clipboard.

## What it does

- Collects all unique diagnostics in the current buffer
- Joins their messages with newlines
- Copies the result to the `+` clipboard register so you can paste anywhere

> **Note:** The default mapping copies every diagnostic in the buffer, not just
> the message under your cursor.

## 🔑 Usage

1. Open a buffer that has diagnostics (via built-in LSP, linting, etc.).
2. Press `<Leader>cy` to copy all diagnostic messages in the buffer.
3. Paste from the system clipboard as usual (for example, `<C-v>` in your terminal).

## Installation (lazy.nvim)

```lua
{
  "NickStafford2/copy-diagnostics.nvim",
}
```

## Configuration

The plugin is configured through `vim.g.copy_diagnostics_configuration`. Below
is the default configuration; override any value you need.

```lua
{
  "NickStafford2/copy-diagnostics.nvim",
  config = function()
    vim.g.copy_diagnostics_configuration = {
      keymap = {
        all = "<Leader>cy",   -- copy all diagnostics in the buffer
        cursor = "<Leader>cY", -- reserved for future per-cursor copy
      },
    }
  end,
}
```

## Tracking updates

See [doc/news.txt](doc/news.txt) for updates. You can also follow the RSS feed:

```
https://github.com/NickStafford2/copy-diagnostics.nvim/commits/main/doc/news.txt.atom
```
