# 2-opencode-loom

This folder contains the final deployable Loom-prep package.

## Primary File

- `opencode-loom-script-final.html`

This is the master file to publish.

## Included Assets

- `claude-loom-script-final.html`
  Embedded as a comparison tab inside the master file.
- `daud-loom-bullet-rehearsal.md`
  Short rehearsal outline.
- `daud-loom-final-4m30-spoken.md`
  Natural spoken script.
- `daud-loom-final-4m30-spoken.mp3`
  Generated practice audio.
- `daud-loom-final-4m30-spoken.mp4`
  Generated practice video.

## Runtime Dependencies

The master HTML also references:

- `../loom-sample/compressed-2.mp4`

So if you deploy this folder, make sure the `loom-sample/` folder is deployed alongside it at the repository root.

## Intended Use

- review sample-video strategy
- rehearse final talking points
- compare OpenCode and Claude versions
- play the local practice media directly in browser
