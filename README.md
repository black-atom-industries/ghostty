# Black Atom for Ghostty

<div align="center">
  <img src="https://github.com/black-atom-industries/.github/blob/main/profile/assets/black-atom-banner.jpg" alt="Black Atom Banner" style="width:100%"/>
</div>

> A collection of elegant, cohesive themes for the Ghostty terminal by Black Atom Industries

## What is a Black Atom Adapter?

This repository is a **Ghostty adapter** for the Black Atom theme ecosystem. In the Black Atom architecture:

- The [core repository](https://github.com/black-atom-industries/core) is the single source of truth for all theme definitions
- Each adapter implements these themes for a specific platform (Neovim, VS Code, Alacritty, etc.)
- The adapter uses templates to transform core theme definitions into platform-specific files

This modular approach ensures consistent colors and styling across all supported platforms while allowing for platform-specific optimizations.

## Available Themes

Black Atom includes multiple theme collections, each with its own distinct style:

| Collection   | Themes                                                     | Description                   |
| ------------ | ---------------------------------------------------------- | ----------------------------- |
| **JPN**      | koyo-hiru, koyo-yoru, tsuki-yoru                           | Japanese-inspired themes      |
| **Stations** | engineering, operations, medical, research                 | Space station-inspired themes |
| **Terra**    | seasons (spring, summer, fall, winter) × time (day, night) | Earth season-inspired themes  |
| **CRBN**     | null, supr                                                 | Minimalist carbon themes      |

All themes are available in both dark and light variants.

## Installation

### Prerequisites

- [Ghostty](https://github.com/mitchellh/ghostty) terminal emulator
- [Black Atom Core](https://github.com/black-atom-industries/core) (for generating themes)

### Setup

1. Clone this repository:

```bash
git clone https://github.com/black-atom-industries/ghostty.git
cd ghostty
```

2. Generate the theme files using Black Atom Core:

```bash
# From the core repository
black-atom-core generate
```

3. Copy the generated `.conf` files to your Ghostty themes directory:

```bash
mkdir -p ~/.config/ghostty/themes
cp themes/*/*.conf ~/.config/ghostty/themes/
```

## Usage

### Setting a Theme

In your `~/.config/ghostty/config` file, include one of the themes:

```
# Include a Black Atom theme
include ~/.config/ghostty/themes/black-atom-jpn-koyo-yoru.conf
```

### Switching Themes

To switch between themes, simply change the included theme file in your config and restart Ghostty:

```
# Change to a different theme
include ~/.config/ghostty/themes/black-atom-terra-fall-night.conf
```

## Development

### Template Structure

The theme templates use the Eta template syntax to inject theme values:

```
background = <%= theme.ui.bg.default %>
foreground = <%= theme.ui.fg.default %>
cursor-color = <%= theme.ui.fg.accent %>
# ...and so on
```

### Creating New Templates

1. Create a `.template.conf` file in the appropriate collection directory
2. Add the template to `black-atom-adapter.json`
3. Generate the theme using the core CLI

### Generating Themes

To generate all themes from the templates:

```bash
cd /path/to/black-atom-core
black-atom-core generate
```

## Contributing

Contributions are welcome! If you'd like to improve existing themes or add new features:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Create a pull request

## License

MIT - See [LICENSE](./LICENSE) for details

## Related Projects

- [Black Atom Core](https://github.com/black-atom-industries/core) - Core theme definitions
- [Black Atom for Neovim](https://github.com/black-atom-industries/nvim) - Neovim adapter
- [Black Atom for Zed](https://github.com/black-atom-industries/zed) - Zed editor adapter
- [Black Atom for Obsidian](https://github.com/black-atom-industries/obsidian) - Obsidian adapter
