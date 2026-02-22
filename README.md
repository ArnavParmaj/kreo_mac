# Kreo Software for Mac
An open source macOS configuration app for the Kreo Swarm keyboard.

> ⚠️ **Work in Progress** — This project is in early development. The Windows-only official software prompted this effort to bring full keyboard configuration support to macOS.

---

## Motivation

The Kreo Swarm is a great keyboard, but its official configuration software only runs on Windows. This project aims to fix that — giving Mac users the ability to configure their keyboard without needing a VM or a second machine.

## Planned Features

- 🌈 **Lighting control** — change RGB modes, colors, and effects
- ⌨️ **Key remapping** — reassign keys to custom inputs
- 🔁 **Macro creation** — record and assign macros to keys
- 💾 **Profile management** — save and switch between configurations
- 🔧 **Firmware updates** — (stretch goal, complex but worth attempting)

## How It Works

The app communicates with the keyboard over USB using the HID (Human Interface Device) protocol. The goal is to reverse engineer the communication protocol used by the official Windows app and reimplement it natively on macOS.

The rough approach:
1. Capture USB traffic between the official Windows app and the keyboard using Wireshark + USBPcap in a VM
2. Document the command structure (what bytes do what)
3. Build a native macOS app that speaks the same protocol

## Status

| Task | Status |
|---|---|
| Identify USB chipset / protocol | 🔄 In progress |
| Capture USB traffic | ⏳ Pending |
| Document command structure | ⏳ Pending |
| Basic lighting control | ⏳ Pending |
| Key remapping | ⏳ Pending |
| Macro support | ⏳ Pending |
| UI | ⏳ Pending |
| Firmware updates | 🔮 Stretch goal |

## Tech Stack

Planned stack (subject to change as the project evolves):

- **Language:** Python (prototyping) → Swift/SwiftUI (final app)
- **USB/HID communication:** [`hidapi`](https://github.com/libusb/hidapi) with Python `hid` bindings
- **UI:** SwiftUI for a native macOS experience

## Contributing

This is currently a solo student project but contributions, ideas, and especially help with protocol reverse engineering are very welcome. If you own a Kreo Swarm and are on Windows, helping capture USB traffic would be incredibly valuable.

Feel free to open an issue if you have information about the keyboard's chipset or USB protocol.

## Disclaimer

This is an independent, unofficial project with no affiliation with Kreo. It is built purely for educational purposes and personal use. Use at your own risk — while lighting and macro changes are safe, firmware-related features should be used with caution.

## License

MIT — free to use, modify, and distribute.

---

*Built with curiosity by a third-year Computer Engineering student who just wanted to use his keyboard on a Mac.*
