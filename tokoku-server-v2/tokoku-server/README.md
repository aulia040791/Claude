# TokoKu POS v2.0

Aplikasi Point of Sale berbasis Flask + SQLite dengan modul lengkap.

## Fitur

### Modul Lama (Dipertahankan)
- ✅ Kasir / POS (scan barcode, keranjang, struk)
- ✅ Manajemen Produk & Stok
- ✅ Manajemen Pelanggan & Hutang Pelanggan
- ✅ Riwayat Transaksi (void, detail)
- ✅ Laporan Penjualan
- ✅ Pengaturan Toko & User

### Modul Baru v2.0
- ✅ **Distributor** — CRUD, kartu hutang buku besar
- ✅ **Pembelian Barang** — Faktur pembelian (Cash / Hutang Penuh / Hutang Sebagian)
- ✅ **Hutang Distributor** — Status, bayar hutang, riwayat cicilan
- ✅ **Kas** — Kas masuk/keluar otomatis + manual, saldo realtime
- ✅ **Laporan Keuangan** — Arus kas, laporan pembelian, laporan hutang
- ✅ **Dashboard** — Notifikasi overdue, top debtors, widget keuangan
- ✅ **Export Excel** — Pembelian, hutang, arus kas

## Cara Menjalankan

### Windows
```
SETUP.bat       # Install dependencies (sekali saja)
START_SERVER.bat # Jalankan server
```

### Manual
```bash
pip install flask flask-cors openpyxl
python app.py 8080
```

Buka browser: http://localhost:8080

## Login
| Username | Password   | Role    |
|----------|------------|---------|
| owner    | owner123   | Pemilik |
| admin    | admin123   | Admin   |
| kasir    | kasir123   | Kasir   |

## Integrasi Otomatis
- Faktur pembelian **Cash** → Kas Keluar otomatis
- Faktur pembelian **Hutang Sebagian (DP)** → Kas Keluar DP otomatis
- **Bayar Hutang** distributor → Kas Keluar otomatis
- **Transaksi Kasir** tunai → Kas Masuk otomatis
- **Stok bertambah** otomatis saat faktur pembelian disimpan

## Database
- File: `tokoku.db` (SQLite)
- Migration otomatis saat startup
- Kompatibel dengan data lama
