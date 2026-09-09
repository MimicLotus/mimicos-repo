# 👑 MimicOS Binary Package Repository (`[mimicos]`)

The official Tier 1 rolling binary package repository for **MimicOS**.

This repository distributes precompiled, hardware-optimized Arch Linux packages (`.pkg.tar.zst`) and the repository database (`mimicos.db.tar.zst`) directly via GitHub Releases.

---

## 📦 Key Packages

| Package | Role | Description |
| :--- | :--- | :--- |
| **`mimic`** | Core Engine | Unified drop-in package manager with hermetic `bwrap` builder and memory safeguards. |
| **`mimic-brain`** | AI SysAdmin | Socket-activated triage mentor and diagnostic daemon. |
| **`umbriel`** | Compositor | Ultra-fast scrolling Wayland compositor tailored for MimicOS. |
| **`noctalia-shell`** | Desktop Shell | Modern Wayland layer-shell panel, launcher, and OSD. |
| **`mimicos-desktop`** | Meta Package | Flagship desktop profile bundling the complete MimicOS desktop experience. |

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

Install the flagship MimicOS tools:

```bash
sudo pacman -S mimic mimic-brain
```

Or install the complete desktop environment:

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
