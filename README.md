# Fluorite

When finished, this program will be a highly versatile and powerful dice roller, inspired by the iOS app Dice Calculator. At the moment, its core functionality is in place, although it remains dramatically unpolished.

The central intended selling points for the program's release are:
- Versatile user interface, available both in GUI and CLI formats
- Fully offline; no need to rely on a Discord dice bot, or [that ancient Wizards dice roller](https://www.wizards.com/dnd/dice/dice.htm), or any similar bit of potentially-rottable online infrastructure
- Calculator functionality, supporting a variety of operations freely mixable with die rolls
- Multi-platform support

At the moment, there's a functional build for 64-bit Windows; other targets are a work-in-progress.

## Known Build Dependencies

Command-line tools:
- `cargo`
- `make`
- `zip`
- `jq`

Rust targets:
- `x86_64-pc-windows-msvc`

## TODOs

### Functionality (general)

- Figure out an elegant way to handle verbose display of nested dice rolls. (See, for example, `2d3d4`. Rendering as [2, 1]d4 loses something; so does rendering as [4, 2, 4].)
- Recognize preemptively and error when an input has a chance to try to roll a non-integer number of dice or a d[non-integer], rather than only when it actually does so

### Functionality (GUI)

- Allow pressing enter to work in place of button-pressing for shortcut-creation
- Allow reordering shortcuts after their creation
- Figure out text-wrapping for large inputs/outputs (in place of the current sideways scrollbar / nothing)
- Provide feedback on shortcut-creation failure (and also for roll errors in a non-history-clogging way, while I'm at it)
- Make the dice buttons a bit less dumb (see their current behavior when pressed repeatedly)
- Prettify the interface

### Build

- Set up a full cross-platform release pipeline, adding support for `i686-pc-windows-msvc`, `x86_64-unknown-linux-gnu`, and `x86_64-apple-darwin`
