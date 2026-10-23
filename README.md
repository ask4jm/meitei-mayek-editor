# Mayek Studio

A small Meetei Mayek typing studio built with Vue 3, Vite, and Electron. Use the on-screen character board or type with the phonetic key mappings in the editor.

## Features

- Meetei Mayek consonants, vowel signs, punctuation marks, and numerals on an on-screen keyboard
- Phonetic typing shortcuts, including `ng`, `ou`, and `ei`
- Automatic draft saving in the browser or desktop app
- Copy text, download as a UTF-8 text file, and open a plain text file
- Dark workspace, light paper editor, and a theme toggle
- Windows x64 portable executable

## Requirements

- Node.js
- pnpm

## Run in a browser

Install dependencies and start Vite:

```sh
pnpm install
pnpm dev
```

Open the local URL printed by Vite.

## Typing

Click in the editor, then either type a mapped key or choose a key from the character board. The on-screen roman labels show the typing shortcuts. For example, type `ng` to enter `ꯉ`, `ou` for `ꯧ`, and `ei` for `ꯩ`.

Vowel signs are dependent marks. Enter a consonant first, then enter its vowel sign. Typing `a` enters the sign `ꯥ`. On-screen buttons can also be used to enter characters. Use Copy text, Download, or Open file to move text in and out of the app.

## Build the portable Windows app

```sh
pnpm install
pnpm desktop
```

The Windows x64 portable executable is created in `release/`. It can be opened without installing the app. The current output is:

```text
release/Mayek Studio 1.0.0.exe
```

To open the built desktop app during development, first build the web app and then run:

```sh
pnpm build
pnpm desktop:open
```

## Project scripts

| Command | Purpose |
| --- | --- |
| `pnpm dev` | Start the Vite development server |
| `pnpm build` | Build the web app into `dist/` |
| `pnpm preview` | Preview the production web build |
| `pnpm desktop` | Build the web app and package a Windows x64 portable executable |
| `pnpm desktop:open` | Open the Electron app using the existing `dist/` build |

## Notes

- Drafts are stored locally in the browser or app profile using `localStorage`.
- The editor stores Unicode text. Meetei Mayek character appearance depends on font support on the device.
- The portable build uses Electron Builder's Windows `portable` target.
