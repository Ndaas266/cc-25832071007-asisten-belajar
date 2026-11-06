# Asisten Belajar

Cloud Computing — PTI 2802  
Pertemuan 3 — Project Inception

## Author
Amanda Fatihatul Ilmi / 25832071007 / 2A

## Problem
Mahasiswa yang belajar mandiri di luar jam kuliah sering tidak memperoleh penjelasan yang cepat dan sesuai materi dalam Bahasa Indonesia. (Hipotesis, belum diverifikasi dengan survei.)

## Target Users
Mahasiswa S1 yang belajar mandiri, memakai ponsel atau laptop.

## Features M03
- baseline application
- health endpoint
- VPS deployment

## Architecture

```mermaid
flowchart LR
    U[User] --> C[Caddy]
    C --> G[Gunicorn]
    G --> F[Flask]
```

## Infrastructure
- Ubuntu Server 24.04
- 2 vCPU
- 2 GB RAM
- 20 GB disk
- Caddy
- Gunicorn

## Public Endpoint
`http://<PUBLIC_IP>/`

## Health Check
`GET /health`

## Deployment
See `docs/deployment.md`.

## Security
- key-only SSH
- root SSH disabled
- UFW enabled
- backend loopback-only

## Current Limitations
- HTTP only
- no persistent database
- no container
- manual deployment

## Roadmap
M04 DNS/HTTPS, M05 Data, M06 Container, M07 IaC, M09 CI/CD
