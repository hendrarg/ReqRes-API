# ReqRes-API

Repo ini adalah starter untuk dokumentasi dan eksperimen dengan ReqRes, hosted REST API untuk QA automation dan backend testing.

## Ringkasan

ReqRes cocok dipakai untuk:

- testing frontend dan backend
- smoke test dan end-to-end test
- latihan request/response REST
- validasi integrasi API

## Prasyarat

- Akun ReqRes dan API key
- `curl` atau Postman
- Opsional: Node.js jika ingin menulis script integrasi sendiri

## Quick Start

ReqRes saat ini memakai header `x-api-key` untuk setiap request.

### 1) Ambil data dari collection

```bash
curl "https://reqres.in/api/collections/products/records" \
  -H "x-api-key: YOUR_API_KEY" \
  -H "X-Reqres-Env: prod"
```

### 2) Buat record baru

```bash
curl -X POST "https://reqres.in/api/collections/products/records" \
  -H "x-api-key: YOUR_API_KEY" \
  -H "X-Reqres-Env: prod" \
  -H "Content-Type: application/json" \
  -d '{"data":{"name":"New Product","price":9.99}}'
```

### 3) Pakai session per-user

```bash
curl "https://reqres.in/app/collections/products/records" \
  -H "Authorization: Bearer YOUR_SESSION_TOKEN"
```

## Contoh Alur Pakai

1. Buat API key di ReqRes.
2. Kirim request pertama ke endpoint collection.
3. Gunakan data respons untuk testing UI, API client, atau automation suite.
4. Jika perlu isolasi data per user, gunakan session token.

## Referensi Endpoint

- `GET /api/collections/products/records` untuk membaca data collection.
- `POST /api/collections/products/records` untuk menambah data.
- `Authorization: Bearer ...` untuk session user terisolasi.

## Struktur Repo

Saat ini repo masih minimal dan berfokus pada README ini sebagai titik awal.

## Referensi Resmi

- Docs: https://reqres.in/docs
- Postman Workspace: https://www.postman.com/reqresapi/reqres/overview

## Catatan

Kalau kamu mau, repo ini bisa dilanjutkan dengan:

- contoh client Node.js
- koleksi Postman
- test otomatis dengan Playwright atau Jest
- dokumentasi endpoint yang lebih detail
