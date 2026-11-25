# Arsitektur Infrastruktur Hardware & Software — BPS Kabupaten Mempawah (6104)

Slide presentasi interaktif bergaya **Swiss Internationalism (`ikb`)** berjumlah **13 slide** yang memetakan secara komprehensif infrastruktur IT BPS Mempawah untuk briefing tim IT (Lead + 2 Anggota), dilengkapi **3 diagram Mermaid interaktif** (dengan kontrol Zoom `+ / − / RESET` dan Drag-to-Pan):

1. **Mermaid #1 — Arsitektur End-to-End (Slide 3)**: Peta integrasi lintas Zona Operasional (IndiHome), Cloudflare Edge + Dual HA `cloudflared` QUIC, Zona Produksi (Dukodu + ThinkStation P320), dan CI/CD GitOps + Tailscale Mesh.
2. **Mermaid #2 — Arsitektur Hardware & Jaringan Fisik Lengkap (Slide 6)**: Detail 2 ISP (IndiHome 2 AP, Dukodu 1 AP 5GHz `OPTI-004F88-5G`), PC/Laptop Pegawai, interface NIC ThinkStation (`Realtek Wi-Fi 6 USB 192.168.1.54` aktif, `Intel I219-LM eno1` kandidat kabel LAN, `tailscale0 100.101.49.42`, `docker0` + 36 bridges), CPU `Intel Xeon E3-1220 v6` (4C), GPU `NVIDIA Quadro P600`, RAM `15 GiB + 11 GiB Swap`, dan storage `1 TB WD HDD` (`442.5 GB ext4`, `486 GB NTFS` legacy headroom, `1 GB EFI`).
3. **Mermaid #3 — Arsitektur Software, Ingress, 78 Container & CI/CD Lengkap (Slide 9)**: Detail 3x GitHub Apps Webhook & GHCR, Dual-Path Ingress (8 layanan Direct Host-Port + Wildcard `*.dvlpid.my.id` via `Traefik v3.6`), Host Daemons (`Ubuntu 24.04.4 LTS`, `Docker v29.5.0`, `cloudflared` HA, `tailscaled`, `agy-mesh`, `microsocks`, `warp-svc`), `Coolify v4.7.6`, `rIDM SSO`, `Infisical Vault`, `OpenObserve`, `Portainer`, `RustDesk`, seluruh **78 container aktif** (23 Apps, 5 Compose Services, 7 Standalone DBs), hingga layer data (`PostgreSQL 15/16/18`, `MariaDB 11`, `MySQL`, `Redis`, `Valkey`, `Meilisearch v1.13`, `MinIO S3`).

## Akses Halaman Web
- **GitHub Pages**: https://ipds6104.github.io/arsitektur/
- **Kontrol Presentasi**: Panah `←` / `→` atau scroll untuk navigasi, `P` untuk Presenter Mode (Bahasa Indonesia), `ESC` untuk grid overview, `B` untuk mode statis/low-power, serta tombol `+ / − / RESET` + drag pada diagram Mermaid.
