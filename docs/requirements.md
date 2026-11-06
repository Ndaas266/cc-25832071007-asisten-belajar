# Requirements

## Problem Statement
Mahasiswa yang belajar mandiri di luar jam kuliah sering tidak memperoleh penjelasan yang cepat dan sesuai materi dalam Bahasa Indonesia. Alat AI umum tersedia, tetapi tidak selaras dengan materi PTI 2802 dan sering langsung memberi jawaban akhir tanpa pembimbingan. (Status: hipotesis, belum diverifikasi dengan survei.)

## Target Users
- Mahasiswa S1 yang belajar mandiri, memakai ponsel atau laptop.
- Pengelola: mahasiswa pengembang.

## Functional Requirements
- FR-01 Login pengguna (rencana M05).
- FR-02 Antarmuka chat tutor AI (rencana).
- FR-03 Riwayat percakapan persisten (rencana M05).
- FR-04 Endpoint GET /health (tersedia pada M03).
- FR-05 Kuota per pengguna (rencana).
- FR-06 Penanganan galat API LLM (rencana).

## Non-Functional Requirements
- NFR-01 backend loopback-only
- NFR-02 application managed by systemd
- NFR-03 public request through reverse proxy
- NFR-04 no secret in repository

## Constraints
- Acuan modul: 1 vCPU, 1 GB RAM, 20 GB disk
- VPS aktual: 2 vCPU, 2 GB RAM, 20 GB disk
- Ubuntu Server 24.04
- public IPv4

## Acceptance Criteria M03
- [x] first deployment accessible
- [x] health endpoint works
