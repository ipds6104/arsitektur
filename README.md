# Arsitektur Infrastruktur Hardware & Software — BPS Kabupaten Mempawah (6104)

Slide presentasi interaktif bergaya **Swiss Internationalism (IKB)** yang memetakan infrastruktur IT BPS Mempawah untuk briefing tim IT:

- **Hardware & Compute**: PC Server ThinkStation (Ubuntu Desktop + Docker + Coolify) dan perangkat kerja pegawai.
- **Jaringan Dual-ISP & 3 Access Point**: Jalur **Dukodu** (1 AP khusus server ThinkStation) dan **IndiHome** (2 AP untuk PC/laptop pegawai).
- **CI/CD Otomatis**: Push ke branch `main` di GitHub memicu **GitHub Apps Webhook** ke Coolify untuk auto-redeploy container Docker.
- **Tata Kelola Domain**: Transisi dari wildcard `*.dvlpid.my.id` menuju domain resmi BPS Mempawah.

## Akses Halaman Web
- **GitHub Pages**: https://ipds6104.github.io/arsitektur/
- **Kontrol Presentasi**: Panah `←` / `→` atau scroll untuk navigasi, `P` untuk Presenter Mode, `ESC` untuk grid overview, `B` untuk mode statis/low-power.
