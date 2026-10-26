# PAZ Viewer

**English** | [Russian](README.ru.md)

A Windows tool for viewing and editing **PAZ archives** of the **Musica** visual novel engine by
minori (*12の月のイヴ*, *eden\**, *ef*, *Natsuzora no Perseus*, *Trinoline*, *Supipara* and others).

Open an archive, browse it like a folder, preview pictures, scripts and sounds, extract files,
replace or add files and save the archive back — whole, or as a small patch the game loads over
the original.

## Features

- **Built-in keys for 29 Musica games** (from the GARbro database). The game is detected
  automatically when an archive is opened.
- **Explorer-like browsing**: a folder tree, the current folder's contents and a path bar; or all
  files in one flat list (Ctrl+L).
- **Three views**: Details (size, packed size, offset, packing, status), List and Thumbnails on a
  checkerboard background (Ctrl+1/2/3).
- **Preview pane** (F3): pictures (PNG, BMP, JPEG), script text (Shift-JIS), sound (OGG and WAV,
  also files without an extension) with Play / Stop.
- **Extract** selected files, folders or the whole archive into a folder named after the archive,
  keeping subfolders.
- **Replace and add files** by drag and drop, from the menu or from the context menu.
- **Save** the whole archive, or **save only the changes as a patch** (`scr1.paz` … `scr9.paz`):
  the game loads it over `scr.paz` and the original stays untouched — the best way for
  translations.
- **Multi-volume archives** (`bg.paz` + `bg.pazA` … `bg.pazN`) open as one archive and are saved
  in volumes again, split like the original packer does (300 MiB, a file never crosses volumes).
- **Byte-identical round trip**: an unchanged archive is saved back exactly as the original.
- **Safe saving**: the first overwrite keeps the original as `.paz.bak` (each volume too).
- **English or Russian interface** (Language menu; English by default), built-in help (F1).
- Remembers panel sizes, the view, the preview pane and the language.

## Usage

1. Run `pazview.exe` and open a `.paz` (Ctrl+O), drop it onto the window, or pass it on the
   command line: `pazview.exe path\to\scr.paz`.
2. Browse and preview; extract with Ctrl+E (selected) or Ctrl+Shift+E (all).
3. To change files, drop the new files onto the list: archive files with the same name or path
   are replaced, others can be added as new.
4. Save with Ctrl+S, or Ctrl+P to write only the changes as a patch.

### Keyboard

| Keys | Action |
|---|---|
| Ctrl+O | Open archive |
| Ctrl+S / Ctrl+Shift+S | Save / Save as |
| Ctrl+P | Save changes as patch |
| Ctrl+E / Ctrl+Shift+E | Extract selected / Extract all |
| Ctrl+R | Replace the selected file |
| Del | Undo replace / remove a new file |
| Ctrl+A | Select all |
| Ctrl+L | All files in one list |
| Ctrl+1 / 2 / 3 | Details / List / Thumbnails |
| Enter | Open folder / play sound |
| Backspace, Alt+↑ | Up one level |
| F3 | Preview pane |
| F1 | Help |

## Download

Get `pazview.exe` from [Releases](https://github.com/imKota/PazViewer/releases). It is a single
file: no installation and no extra runtime are needed — just run it.

**Requirements:** Windows 10 or 11 (64-bit).

## Limitations

- File names inside an archive are stored in Shift-JIS, so Cyrillic is not supported in names
  (file contents can be anything).
- No preview yet for `.sqz`, `.avi` and other engine formats (they can be extracted and replaced).
- An overlay (`scr1.paz`) opened without its main archive next to it, and without RC4-layered
  files, may show the wrong game name (the contents are not affected).

## Credits

- Game keys: the [GARbro](https://github.com/morkt/GARbro) database.
- [zlib](https://zlib.net/) 1.2.11 and [stb_vorbis](https://github.com/nothings/stb) 1.22 are built in.

Made by [ImKota](https://github.com/imKota/) · [github.com/imKota/PazViewer](https://github.com/imKota/PazViewer)
