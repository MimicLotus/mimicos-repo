# 👑 MimicOS Binary Package Repository (`[mimicos]`)

The official Tier 1 rolling binary package repository for **MimicOS**.

This repository distributes precompiled, hardware-optimized Arch Linux packages (`.pkg.tar.zst`) and the repository database (`mimicos.db.tar.zst`) directly via GitHub Releases.

The flagship desktop experience in MimicOS is powered by **Umbriel WM** (the modern scrolling Wayland compositor) paired with **Noctalia Shell** (layer-shell panel, launcher, and notifications), unified by the **Mimic** package engine.

---

## 📦 Key Packages

| Package | Role | Description |
| :--- | :--- | :--- |
| **`mimic`** | Core Package Engine | High-performance drop-in package manager with hermetic `bwrap` sandbox builds and `MemoryGuard` safeguards. |
| **`mimic-brain`** | Zero-RAM AI SysAdmin | Socket-activated compiler diagnostic mentor and package triage daemon. |
| **`umbriel`** | Flagship Window Manager | Blazing-fast scrolling Wayland compositor serving as the core WM for MimicOS. |
| **`noctalia-shell`** | Desktop Shell | Modern Wayland layer-shell panel, application launcher, dock, and OSD stack tailored for Umbriel. |
| **`mimicos-desktop-settings`** | Desktop Integration | Modular Umbriel configs, Wallust dynamic palettes, session definitions, and theme scripts. |
| **`mimicos-desktop`** | Flagship Meta-Package | Meta-package bundling the complete flagship desktop: Umbriel WM + Noctalia Shell + Mimic engine. |
| **`sddm-theme-mimicos`** | Display Manager Theme | Sleek Wayland SDDM login theme matching the MimicOS aesthetic. |

---

## 🖥️ The Flagship Stack: Umbriel WM + Noctalia Shell

The MimicOS flagship desktop is not an arbitrary desktop environment created from scratch—it is a meticulously tuned, keyboard-driven Wayland environment:

- **Compositor**: [Umbriel](https://github.com/noctalia-dev/umbriel) — A lightweight scrolling Wayland compositor featuring smooth animations and ergonomic workspace navigation.
- **Desktop Shell**: [Noctalia Shell](https://github.com/noctalia-dev/noctalia-shell) — Fast, elegant layer-shell bar, application launcher, quick settings, and notifications.
- **Theme & Dynamic Color**: [Wallust](https://codeberg.org/explosion-mental/wallust) — Dynamic palette generation applied seamlessly across Alacritty, GTK, and shell components.
- **Package Management**: [Mimic](https://github.com/MimicLotus/mimic-core) — Sandboxed `bwrap` builds, zero-RAM triage daemon (`mimic-brain`), and memory-safe parallel compilation.

---

## 🚀 Adding the Repository to Arch Linux

To enable the `[mimicos]` binary repository on any Arch Linux or derivative system:

### 1. Configure `/etc/pacman.conf`

Open `/etc/pacman.conf` with root privileges and append the following stanza:

```ini
[mimicos]
SigLevel = Optional TrustAll
Server = https://github.com/MimicLotus/mimicos-repo/releases/download/latest
```

### 2. Synchronize Databases & Install

Synchronize your package databases:

```bash
sudo pacman -Syu
```

Install the Mimic package engine and AI mentor:

```bash
sudo pacman -S mimic mimic-brain
```

Or install the complete flagship desktop (Umbriel WM + Noctalia Shell):

```bash
sudo pacman -S mimicos-desktop
```

---

## 🛠️ Architecture & Distribution

- **Rolling Release**: Hosted on GitHub Releases under the `latest` tag.
- **Hermetic Toolchains**: Built using `bwrap` sandboxing with `-march=x86-64-v3` / native flags, `sccache`, and the `mold` linker.
- **Drop-in Compatibility**: Fully compatible with standard `pacman`, `makepkg`, and the `mimic` package engine.

---

## 👤 Maintainer

Crafted by **Mimic Lotus** for **MimicOS**.
