# Raspberry Pi → Home Assistant Kiosk (Wayland, Portrait)

A minimal, robust **touchscreen kiosk** for **Raspberry Pi OS (Trixie)** using **Wayland (Wayfire)** and **Chromium (Flatpak)**.  
Features:
- Portrait **90° rotation** on `HDMI-A-1`
- **No sleep / no DPMS blanking**
- **No cursor** (optional)
- **Auto-launch** Chromium in kiosk to **Home Assistant**
- **Systemd user service** (single launcher, with logs)
- Persistent login (no more re-auth every boot)

> Tested URL (customize in files): `http://192.168.0.2:8123/`

---

## Requirements

- Raspberry Pi OS **Trixie (64-bit)** with **Wayland** session (Wayfire).
- Flatpak available (Chromium from Flathub).
- Display connected as `HDMI-A-1` (check with `wlr-randr`).

---

## Quick start

```bash
# 1) On the Pi, as user 'pi'
sudo apt update
sudo apt install -y git
git clone https://github.com/<yourname>/raspi-ha-kiosk.git
cd raspi-ha-kiosk

# 2) Install (customize URL if you want)
bash scripts/setup_kiosk.sh http://192.168.0.2:8123/

# 3) Reboot and enjoy
sudo reboot
