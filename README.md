# 📁 Fonts from Windows 11

![Font Types](https://img.shields.io/badge/TTF%20%7C%20TTC%20%7C%20FON-included-F9F6EE)
[![Windows](https://custom-icon-badges.demolab.com/badge/Windows-0078D6?logo=windows11&logoColor=white)](#)

This repository contains a comprehensive archive of font files extracted from Windows 11 version 22H2. It includes both legacy bitmap `.fon` fonts and modern TrueType/OpenType `.ttf` and `.ttc` fonts, organized for archival, reference, or integration into custom environments.

## 📦 Structure

```bash
fonts-windows/
├── README.md
└── Windows-11/
    ├── *.fon          # Bitmap fonts (legacy DOS, VGA, OEM, CGA, EGA)
    ├── *.ttf          # TrueType fonts (UI, serif, sans-serif, emoji, etc.)
    ├── *.ttc          # Font collections (Cambria, SimSun, Yu Gothic, etc.)
```

## 🔤 Font Categories

The collection spans multiple font families and formats:

- **System UI Fonts**: Segoe UI, Calibri, Candara, Consolas, Corbel, etc.
- **Legacy Fonts**: VGA, EGA, CGA, OEM, DOS, Small Fonts (`*.fon`)
- **International Fonts**: Malgun Gothic (Korean), MS Gothic (Japanese), SimSun (Chinese), Yu Gothic
- **Decorative & Symbol Fonts**: Webdings, Wingdings, Gabriola, Impact, Marlett
- **Serif & Sans-Serif**: Georgia, Times New Roman, Arial, Verdana, Trebuchet MS
- **Mono Fonts**: Courier New, Lucida Console
- **Emoji & Icons**: Segoe UI Emoji, Segoe MDL2 Assets, Segoe UI Symbol

## ⚠️ Licensing Note

These fonts are proprietary to Microsoft and are distributed with Windows 11. Redistribution or use outside of licensed Windows environments may violate Microsoft's terms of use. This repository is intended for educational and archival purposes only.

## 🛠️ Quick Install (Linux)

To clone and install the fonts directly into your local font directory:

```bash
git clone --depth=1 --filter=blob:none --sparse https://github.com/ashik-maybe/fonts-windows.git /tmp/winfonts \
&& cd /tmp/winfonts \
&& git sparse-checkout set Windows-11 \
&& mkdir -p ~/.local/share/fonts \
&& cp -r Windows-11/* ~/.local/share/fonts/ \
&& fc-cache -fv
```

This command:

- Clones only the `Windows-11` folder (sparse checkout)
- Copies all fonts to `~/.local/share/fonts`
- Refreshes the font cache for immediate use

Bitmap `.fon` files may require legacy environments or emulators to function properly.

<details>

<summary>🧵 Selective Install: Serif & Sans-Serif Fonts Only</summary>

If you only want to install classic serif and sans-serif fonts (e.g., Georgia, Times New Roman, Arial, Verdana, Trebuchet MS), use this filtered install:

```bash
git clone --depth=1 --filter=blob:none --sparse https://github.com/ashik-maybe/fonts-windows.git /tmp/winfonts \
&& cd /tmp/winfonts \
&& git sparse-checkout set Windows-11 \
&& mkdir -p ~/.local/share/fonts \
&& find Windows-11 -type f \( \
  -iname "georgia*.ttf" -o \
  -iname "times*.ttf"   -o \
  -iname "arial*.ttf"   -o \
  -iname "verdana*.ttf" -o \
  -iname "trebuc*.ttf"  \) \
  -exec cp {} ~/.local/share/fonts/ \; \
&& fc-cache -fv
```

This command:

- Installs only serif and sans-serif `.ttf` fonts
- Skips bitmap `.fon` files and other font types
- Keeps your font directory minimal and focused

> You can customize the `find` pattern to include or exclude additional families as needed.

</details>
