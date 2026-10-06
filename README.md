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

**Linux (Ubuntu 22.04 or later, Debian, Fedora — x86_64 and arm64)** — one
line, for your account only, no `sudo`: it checks the download's SHA-256, puts
UARTist in `~/.local` and the app menu, and prints (without running them) the
steps that need an administrator:

```sh
curl -fsSL https://uartist.app/install.sh | sh
```

or the system's package manager, which also brings in WebKit2GTK:

```sh
sudo apt install ./UARTist-linux-amd64.deb     # Ubuntu, Debian (arm64: UARTist-linux-arm64.deb)
sudo dnf install ./UARTist-linux-x86_64.rpm    # Fedora (arm64: UARTist-linux-aarch64.rpm)
```

or the portable `UARTist-linux-x86_64.tar.gz` (`aarch64`): unpack it anywhere
and run `UARTist/UARTist`. To open serial ports, your account needs the
`dialout` group, once: `sudo usermod -aG dialout $USER`, then log out and in.

**Windows 10 / 11** — the
[Microsoft Store](https://apps.microsoft.com/detail/9MTZSLT89V5X), or:

```powershell
winget install --id 9MTZSLT89V5X --source msstore
```

or, where the Store is not available, the portable app:
`UARTist-windows-x64.zip` from the latest release — unzip it anywhere and run
`UARTist\UARTist.exe`. It is not signed, so the first time choose *More info
→ Run anyway*. It does not update itself.

## Teach Claude Code to use UARTist

```sh
npx --allow-remote=all https://uartist.app/claude-skill/ install --global   # or --local, for one project
uartist skill install                                                       # or, with UARTist installed: no Node needed
```

installs a Claude Code skill — how to install UARTist, its command line and
its MCP server, and what to ask you first — at the same version as the app.
`--allow-remote=all` lets npm 12 and later fetch a package from a URL (they
refuse by default; earlier npm ignores the flag). On Windows, if PowerShell says
*running scripts is disabled*, type `npx.cmd` instead of `npx`, or use
PowerShell 7 or the Command Prompt.

## Each release has

| File | |
|---|---|
| `UARTist-<version>-arm64.dmg` | the macOS app |
| `UARTist-arm64.dmg`, `UARTist-arm64.dmg.sha256` | the same dmg under a name that does not change, and its SHA-256 |
| `UARTist-<version>-windows-x64.zip` | the portable Windows app |
| `UARTist-windows-x64.zip`, `UARTist-windows-x64.zip.sha256` | the same zip under a name that does not change, and its SHA-256 |
| `UARTist-<version>-linux-<arch>.tar.gz`, `.deb`, `.rpm` | the Linux app: portable, and as packages (x86_64 / amd64, aarch64 / arm64) |
| `UARTist-linux-…`, each with a `.sha256` | the same under names that do not change, and their SHA-256 |
| `install.sh`, `install-mac.sh`, `install-linux.sh` | the one-line installer, and the one it runs for macOS or Linux |
| `THIRD_PARTY_NOTICES.md` | the open-source components inside the app, and their licenses |
| `uartist-skill.tgz`, `uartist-claude-skill.zip` | the Claude Code skill for this version (npx package, or the folder to unzip) |

## License

UARTist is free to use under the MIT license, which comes with every build.
Its source code is not published. The open-source components it carries, and
their licenses, are in `THIRD_PARTY_NOTICES.md`.

## Problems, questions, ideas

[Open an issue](https://github.com/changyy/UARTist-release/issues). Say
which version of UARTist, which system, and the adapter if it is
about a device.

Privacy: <https://uartist.app/privacy/>.
