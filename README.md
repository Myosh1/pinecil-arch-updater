# pineup — Pinecil Arch Updater

A shell script that automates flashing [IronOS](https://github.com/Ralim/IronOS) firmware onto Pinecil V1 and V2 soldering irons.

## Requirements

**Arch Linux based distributions only.** Other distributions are not supported.

## What it does

- Installs all required dependencies (`blisp`, `dfu-util`, `curl`, `jq`) via pacman/AUR
- Configures udev rules for device access
- Fetches the latest IronOS release directly from the official GitHub repository
- Prompts for device version and firmware language
- Flashes the firmware with no additional steps required

## Installation

```bash
chmod +x pineup
cp pineup ~/.local/bin/pineup
```

## Usage

```bash
# Interactive mode
pineup

# Non-interactive
pineup --v2 --lang EN
pineup --device v2 --lang EN

# Fully automated (device must already be in DFU mode)
pineup --v2 --lang EN --auto

# Help
pineup --help
```

## Entering DFU mode (Pinecil V2)

1. Unplug Pinecil from USB
2. Hold the **[−]** (minus) button
3. While holding — plug in USB
4. The screen should remain blank

## Authors

- **Myoshi** — concept, testing, debugging
- **Claude (Anthropic)** — script development
- **ChatGPT (OpenAI)** — assistance at various stages

## License

This script is released under the **MIT License**.

IronOS firmware is licensed under **GNU GPLv3** by [Ralim (Ben V. Brown)](https://github.com/Ralim/IronOS).
This script downloads firmware directly from the official repository and does not re-host any files,
in compliance with the IronOS license terms.

## Status

This project was written for personal use and will likely not receive updates or active maintenance.
