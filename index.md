---
title: Marionette MCP
---

# Marionette MCP

**Let your AI client see and operate Windows desktop apps.** · by Sewoong Oh (Codetelier)

[한국어](ko/) · [Terms of Service](terms) · [Refund Policy](refund) · [Privacy Policy](privacy) · Support: codetelier.support@gmail.com

Marionette MCP is a local MCP server for Windows. An AI client such as Claude Code calls its tools to capture the screen, read text, find buttons and icons, and click or type in desktop apps — including apps that have no API.

## Features

- **Sees the screen**: text recognition (OCR, Korean and English) and icon detection run on your PC; elements come back as a numbered list.
- **Operates apps**: clicks, typing (Korean too), keys, scrolling, drag, window focus and placement, UI Automation when an app offers it.
- **Shows what it does**: a pointer and target highlight on screen, and an emergency stop (Ctrl+Alt+Backspace or a quick shake of the mouse) that halts all input at once.
- **Learns apps**: short app notes (tips and pitfalls) it shares with the AI client the next time.
- **Works without administrator rights**: runs as a normal user; restart it as administrator from the tray menu when an app running as administrator must be driven.
- **Remote use (optional)**: let Claude Code on another PC you specify drive this one (a test VM, for example), with an access token and a firewall rule for that address only.

## Get it

Install with [winget](https://learn.microsoft.com/windows/package-manager/winget/) (built into Windows 10 and 11) from PowerShell or the command prompt. No administrator rights and no setup screens:

```
winget install Codetelier.Marionette
```

Marionette checks for new versions once a day and installs them when you choose (or, if you turn on automatic install, while Claude is idle).

## System requirements

| | Minimum | Recommended |
|---|---|---|
| Windows | Windows 10 version 1809 (build 17763) or later, 64-bit (x64; ARM64 isn't supported) | Windows 10 22H2 or Windows 11 |
| Processor | 4 cores | More cores analyze the screen faster |
| Memory | 8 GB | 16 GB |
| Storage | 1 GB free (about 530 MB installed, models included) | |
| Graphics | Not needed | A DirectX 12 discrete GPU with 4 GB or more speeds up icon detection (optional) |

Measured on a 4-core Intel Core i3-10100 with 16 GB: Marionette holds about 0.2 GB idle and 0.5–0.8 GB between screen analyses, and up to about 4 GB while analyzing on the CPU. Analyzing a 560×640 window takes about 9–13 s on the CPU, a whole 1920×1080 screen about 21 s; with a GeForce GTX 1650 doing icon detection, about 3–8 s and 16 s. Analyzing just a window or a region, and reading text only, is faster.

## Connect Claude Code

After Marionette starts (tray icon), register it once in Claude Code:

```
claude mcp add --transport http marionette http://127.0.0.1:5300 -s user
```

Then restart Claude Code.

## Free and Pro

- **Free**: 100 tool calls in any one-hour window.
- **Pro**: no limit. $29, paid once, for one PC. Press **Buy Pro** on the Marionette window's **About** tab. Your license key comes in the receipt email: paste it on the **About** tab and press **Register** ([how](activate)). To move Pro to another PC, press **Remove key** on the old one first. Full refund within 14 days ([Refund Policy](refund)).

## Support

codetelier.support@gmail.com
