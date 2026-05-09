# Aimisi Codex Pet

Unofficial custom Codex pet package for 爱弥斯.

![Aimisi preview](previews/aimisi-showcase.gif)

## Install

Copy the pet folder into your Codex home:

```powershell
Copy-Item -Recurse -Force .\pets\aimisi "$env:USERPROFILE\.codex\pets\aimisi"
```

Then restart or reopen the Codex pet with `/pet`, and select `爱弥斯` if it is not already selected.

## Package

```text
pets/aimisi/
  pet.json
  spritesheet.webp
```

The spritesheet is a Codex-compatible 8x9 atlas:

- 8 columns x 9 rows
- 192x208 pixels per cell
- 1536x1872 pixels total
- WebP with alpha

## Behavior Notes

- Idle and waiting rows keep 爱弥斯 open-eyed.
- Drag and movement rows use open-eyed flying frames to avoid rapid eye flashing.
- Hover/action rows include extra cute variants: waving, cheek pose, head tilt, happy squeezed-eye jump, and small in-place flying motions.

## Preview

The full contact sheet is available at `previews/contact-sheet.png`.

## Rights

This is an unofficial fan-made Codex pet package created for personal customization. It is not affiliated with OpenAI, Codex, Kuro Games, or Wuthering Waves. Do not use these assets commercially unless you have the relevant rights.
