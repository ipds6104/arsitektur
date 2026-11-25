# Arsitektur Infrastruktur Hardware, Mesh & Software — BPS Kabupaten Mempawah (6104)

Slide presentasi interaktif bergaya **Swiss Internationalism (`ikb`)** berjumlah **15 slide** untuk briefing tim IT (Lead + 2 Anggota), dilengkapi **3 diagram Mermaid interaktif** (dengan tombol Zoom `+ / − / RESET` dan Drag-to-Pan):

1. **Mermaid #1 — Arsitektur End-to-End (Slide 3)**: Integrasi Public Data Plane (IndiHome → Cloudflare Edge → Dual HA `cloudflared` QUIC → Traefik/Direct Ports → Coolify), Private Mesh Plane (Tailscale 11 node + AGY Mesh `:8484`), Infisical Vault (`:8095`), dan GitOps CI/CD.
2. **Mermaid #2 — Arsitektur Hardware, Jaringan Fisik & 11 Node Tailscale (Slide 6)**: 2 ISP (IndiHome 2 AP, Dukodu 1 AP 5GHz `OPTI-004F88-5G`), 11 node Tailscale (`server-thinkstation-p320`, `bps` 20-Core GPU, `bps6104-2`, `bps6104-7`, `bps6104-8`, `desktop-ltkna8u`, `victus-1`, `victus`, `localhost-0`, `poco-f7`, `xiaomi-pad-6`), NIC ThinkStation (`Realtek Wi-Fi 6 USB` aktif & `Intel I219-LM eno1` kandidat kabel LAN), CPU Xeon E3-1220 v6, GPU NVIDIA Quadro P600, RAM 15 GiB + 11 GiB Swap, dan 1 TB WD HDD.
3. **Mermaid #3 — Arsitektur Software, Ingress, Infisical, AGY Mesh & 78 Container (Slide 10)**: 3x GitHub Apps Webhook & GHCR, Dual-Path Ingress (8 Direct Host-Port + Wildcard `Traefik v3.6`), Host Daemons (`Ubuntu 24.04.4 LTS`, `Docker v29.5.0`, `tailscaled`, `agy-mesh :8484`, `microsocks`, `warp-svc`), **Infisical Secret Vault (`secrets:8095`)**, `Coolify v4.7.6`, `rIDM SSO`, `OpenObserve`, `Portainer`, `RustDesk`, seluruh **78 container aktif** (23 Apps, 5 Services, 7 Standalone DBs), dan Data Layer.

### Fokus Tata Kelola & Keamanan (Slide 7, 11, 12, 13)
- **Tailscale + Universal AGY Mesh (`:8484`)**: Kolaborasi multi-PC (`agy-ops`, shared context blackboard, `ask_peer`, peer screen capture) dan aturan Zero 3rd-Party VPN.
- **Infisical Secret Vault (`secrets.dvlpid.my.id`)**: Zero hardcoded secrets, Universal Auth runtime injection (`infisical run` / `agy-infisical`), audit trail, dan rotasi instan.
- **Dua Migrasi Aset Wajib**:
  1. **Domain**: Dari `*.dvlpid.my.id` (domain pribadi Lead) → **Domain Resmi BPS Mempawah**.
  2. **Akun Tailscale**: Dari `ihza2karunia@gmail.com` (akun pribadi, belum ideal) → **`ipds6104@gmail.com`** (akun resmi satker).

## Akses Halaman Web
- **GitHub Pages**: https://ipds6104.github.io/arsitektur/
- **Kontrol Presentasi**: Panah `←` / `→` atau scroll untuk navigasi, `P` untuk Presenter Mode (Bahasa Indonesia), `ESC` untuk grid overview, `B` untuk mode statis, serta tombol `+ / − / RESET` + drag pada diagram Mermaid.
