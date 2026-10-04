# Eudic for PopClip

Look up the selected text in [Eudic](https://www.eudic.net/) (欧路词典), the Chinese-English dictionary.

Select any word or sentence, click the Eudic icon in the PopClip bar, and Eudic
opens straight to the relevant entry.

This is a modernised replacement for the built-in Eudic extension, which has not
been updated since 2022 and whose AppleScript `show dic with word` approach no
longer behaves reliably with current versions of Eudic (tested against Eudic 26.9.1).

## Usage

1. Select some text in any app.
2. Click the **Eudic** icon in the PopClip bar.
3. Eudic launches (or comes to the front) and shows the entry for the selected text.

**Secondary-click** (right-click or Control-click) the icon to open a submenu with
the rest of the commands.

| Command | What it does |
| --- | --- |
| Search In Eudic (main button) | Looks the selection up, using the Lookup Mode option |
| 词典 Dictionary | `eudic://dict/<text>` — word or sentence definition |
| 百科 Wiki | `eudic://wiki/<text>` — encyclopedia entry |
| 朗读 Speak | Speaks the selection using Eudic's speech engine (via the macOS service "Eudic • 朗读选中内容") |
| 启动 Eudic | Just launches Eudic (`eudic://`) |

## Options

Set these in PopClip → Settings → Extensions → Eudic.

**Eudic Edition** (版本) — which Eudic app to open. Leave it on 自动 (Auto) if you
have one edition installed; if you have both, pick **Lite 版** or **增强版** to make
PopClip open that specific one. (With Auto, macOS routes the `eudic://` scheme to
whichever app registered it.)

**Lookup Mode** (查询方式) — what the main button looks up: 词典 (`eudic://dict/`)
or 百科 (`eudic://wiki/`).

## How it works

The extension uses Eudic's official `eudic://` URL Scheme instead of sending
AppleScript commands. That keeps it working across current Eudic versions and
means it does not need to know whether you have the Lite or enhanced edition —
unless you want to force one, which is what the Edition option is for. PopClip
URL-encodes the selected text automatically, so Chinese text, spaces and
punctuation are handled correctly.

### A note on what Eudic actually supports on macOS

Eudic's published URL Scheme documentation lists several actions, but not all of
them work on the Mac. These were tested on Eudic 26.9.1 and are **not** included
because they do nothing on macOS:

- `eudic://camera` (相机取词) — mobile only
- `eudic://recite` (单词复习) — mobile only
- `eudic://dailyword` (每日一句) — mobile only
- `eudic://peek/<word>` — Android only
- `eudic://transcribe` — iOS only

Eudic also exposes no way for another app to open its lightweight floating
translation window: the `eudic` scheme, the four AppleScript commands
(`show dic`, `show cg`, `show wiki`, `speak word`), and both macOS services all
open the main window. If you want a floating popup instead, enable Eudic's own
**鼠标自动取词** (mouse selection capture) in Eudic → Preferences → 取词, or use an
app such as [Easydict](https://github.com/tisfeng/Easydict) which does expose a
lightweight window via `easydict://query?text=`.

## Changelog

- 2026-10-05: Added the Eudic Edition option (Auto / Lite / 增强版), targeting a
  specific app via `popclip.openTemplateUrl`. Added the submenu with
  词典 / 百科 / 朗读 / 启动 Eudic.
- 2026-10-04: Initial release. Replaced the outdated built-in Eudic extension:
  switched from AppleScript to the official `eudic://` URL Scheme and enabled the
  "Eudic not installed" install prompt.

## Credits

- [Eudic](https://www.eudic.net/) — 欧路词典, by 上海倩言网络科技有限公司.
- Built for [PopClip](https://popclip.app/) by Nick Moore.
