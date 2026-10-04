# UARTist releases

**UARTist** is a serial console for hardware bring-up, for macOS and
Windows. This repository holds its releases — the macOS app, the portable
Windows app, checksums and the installer — and is the place to report
problems. Website:
<https://uartist.app>.

## Install

**macOS (Apple silicon, macOS 11 or later)**

```sh
brew install --cask changyy/tap/uartist
```

or one line in Terminal (it checks the download's SHA-256 before installing):

```sh
curl -fsSL https://uartist.app/install.sh | sh
```

or `UARTist-arm64.dmg` from the
[latest release](https://github.com/changyy/UARTist-release/releases/latest):
open it and drag UARTist into Applications. UARTist is not notarized yet, so
the first time choose *System Settings → Privacy & Security → Open Anyway*.

**Windows 10 / 11** — the
[Microsoft Store](https://apps.microsoft.com/detail/9MTZSLT89V5X), or:

```powershell
winget install --id 9MTZSLT89V5X --source msstore
```

or, where the Store is not available, the portable app:
`UARTist-windows-x64.zip` from the latest release — unzip it anywhere and run
`UARTist\UARTist.exe`. It is not signed, so the first time choose *More info
→ Run anyway*. It does not update itself.

## Each release has

| File | |
|---|---|
| `UARTist-<version>-arm64.dmg` | the macOS app |
| `UARTist-arm64.dmg`, `UARTist-arm64.dmg.sha256` | the same dmg under a name that does not change, and its SHA-256 |
| `UARTist-<version>-windows-x64.zip` | the portable Windows app |
| `UARTist-windows-x64.zip`, `UARTist-windows-x64.zip.sha256` | the same zip under a name that does not change, and its SHA-256 |
| `install-mac.sh` | the one-line installer |
| `THIRD_PARTY_NOTICES.md` | the open-source components inside the app, and their licenses |

## Problems, questions, ideas

[Open an issue](https://github.com/changyy/UARTist-release/issues). Say
which version of UARTist, which system, and the adapter if it is
about a device.

Privacy: <https://uartist.app/privacy/>.
