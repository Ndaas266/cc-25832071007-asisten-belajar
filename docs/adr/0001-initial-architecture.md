# ADR-0001: Initial VPS Deployment Architecture

## Status
Accepted

## Context
VPS Ubuntu Server 24.04 di IDCloudHost dengan 2 vCPU, 2 GB RAM, dan 20 GB disk (modul mengasumsikan 1 vCPU dan 1 GB RAM). Aplikasi awal adalah baseline Flask untuk proyek Asisten Belajar.

## Decision
- Flask
- Gunicorn 1 worker, 2 thread
- systemd
- Caddy
- UFW
- GitHub

## Alternatives
1. Node.js + PM2
2. NGINX + Gunicorn
3. Docker
4. PHP-FPM

## Rationale
- Python dipilih karena proyek berikutnya (asisten belajar berbasis LLM) dan pustaka pendukungnya lebih mudah dikembangkan dengan Python.
- Gunicorn memakai 1 worker dan 2 thread agar penggunaan memori rendah dan tersisa ruang untuk sistem.
- systemd menjalankan aplikasi di latar belakang, menyala otomatis setelah restart, dan dihidupkan ulang saat gagal.
- Caddy sebagai pintu masuk publik karena konfigurasinya singkat dan mendukung HTTPS otomatis pada M04.
- UFW membatasi port masuk hanya SSH dan HTTP.
- Docker ditunda ke M06 untuk menjaga baseline tetap sederhana dan hemat sumber daya.

## Consequences
### Positive
- Penggunaan sumber daya rendah (service sekitar 30-40 MB memori).
- Konfigurasi sederhana dan mudah dijelaskan.
- Aplikasi tetap hidup setelah logout dan restart VPS.
### Negative
- Deployment masih manual.
- Hanya satu VPS, tanpa redundansi.
- Hanya HTTP, belum terenkripsi.
- Belum ada database.

## Review Trigger
Review pada M06/M07.
