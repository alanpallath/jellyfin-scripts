# Home Assistant OS (Pi 5) + External USB Drive + Jellyfin (Docker)  
This setup mounts an external drive into Home Assistant OS and runs Jellyfin so it can see your media folders reliably.

> **Key point:** On Home Assistant OS, `/etc/fstab` is read-only, so manual mounts do **not** persist automatically.  
> We solve this by:
> 1) mounting the drive at boot using a **local add-on**, and  
> 2) running Jellyfin with `--restart unless-stopped` so it starts after reboot.

---

## What you’ll end up with

- External drive mounted at:  
  `/mnt/data/supervisor/media/koalaDrive`

- Jellyfin container sees media at:  
  `/media` (inside the container)

- Recommended folders on the drive:
  - `/mnt/data/supervisor/media/koalaDrive/Movies`
  - `/mnt/data/supervisor/media/koalaDrive/TV_Shows`
  - `/mnt/data/supervisor/media/koalaDrive/Anime`
  - `/mnt/data/supervisor/media/koalaDrive/Music`

- Jellyfin web UI:
  - `http://homeassistant.local:8096`
  - or `http://<PI-IP>:8096`

---

## Prereqs

- Home Assistant OS (Pi 5)
- SSH access to HA host (e.g. via `ssh root@homeassistant.local -p 22222`)
- External USB drive detected as `/dev/sda2` (example)
- Drive formatted and mountable (ext4 recommended)

---

## 1) Mount the drive (manual test)

SSH into HA host and run:

```sh
lsblk
