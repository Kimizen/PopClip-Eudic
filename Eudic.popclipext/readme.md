# Eudic for PopClip

Look up the selected text in [Eudic](https://www.eudic.net/) (欧路词典), the Chinese-English dictionary.

Select any word or sentence, click the Eudic icon in the PopClip bar, and Eudic
opens straight to the relevant entry.

## Usage

1. Select some text in any app.
2. Click the **Eudic** icon in the PopClip bar.
3. Eudic launches (or comes to the front) and shows the entry for the selected text.

Works with both **Eudic 欧路词典 Lite** (`com.eusoft.freeeudic`) and
**Eudic 欧路词典 增强版** (`com.eusoft.eudic`). If Eudic is not installed, PopClip
offers to take you to the download page.

## Options

**Lookup Mode** (查询方式)

| Mode | URL used | Result |
| --- | --- | --- |
| 词典 (Dictionary) | `eudic://dict/<text>` | Word/sentence definition |
| 百科 (Wiki) | `eudic://wiki/<text>` | Encyclopedia entry |

Change it in PopClip → Settings → Extensions → Eudic.

## How it works

This extension uses Eudic's official `eudic://` URL Scheme rather than sending
AppleScript commands. That means it keeps working across Eudic's current
versions and does not need to know whether you have the Lite or enhanced
edition. PopClip URL-encodes the selected text automatically, so Chinese text,
spaces and punctuation are handled correctly.

## Changelog

- 2026-10-04: Initial release. Replaces the outdated built-in Eudic extension:
  switched from AppleScript to the official `eudic://` URL Scheme, added the
  词典/百科 lookup mode option, removed the need to pick an edition manually,
  and enabled the "Eudic not installed" install prompt.

## Credits

- [Eudic](https://www.eudic.net/) — 欧路词典, by 上海倩言网络科技有限公司.
- Built for [PopClip](https://popclip.app/) by Nick Moore.
