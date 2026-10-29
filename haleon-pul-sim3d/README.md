# Haleon PUL — Opsi B · Simulasi 3D

Simulasi 3D konsep **PT Global Inti Sinergi** untuk RFQ *PUL Palletizing* Haleon. Isinya Opsi B dengan dua modul yang bisa dipesan terpisah:

- **Modul 1 — Robotic case packing.** Satu cobot ±10 kg dengan gripper vakum 5 zona memindahkan karton (115×104×60) ke shipper (591×432×387, 120 karton, pola 5×4×6). Shipper dibentuk, ditutup, di-taping, dan diberi label secara manual oleh 1 operator dengan 2 posisi kerja.
- **Modul 2 — Gantry palletizing.** Gantry kartesian XYZ overhead melayani 4 pallet station (PS1–PS4) di posisi RFQ. Pola susunnya 2×2×2 (8 shipper per pallet). Pallet dialokasikan per batch, dan pallet diganti dengan handlift lewat pintu MAL OUT.

Kedua modul hanya bertemu di **titik serah** (conveyor shipper), dengan sinyal I/O READY, SHIPPER OUT, FULL/STOP, dan FAULT.

## Membuka

Buka `index.html` di browser, atau aktifkan **GitHub Pages** (Settings → Pages → branch `main`, folder `/root`). Semua file sudah dalam satu halaman. Three.js 0.160.0 dimuat dari jsDelivr.

## Kontrol

| Kontrol | Fungsi |
| --- | --- |
| Jeda / Lanjut | Menghentikan atau melanjutkan waktu simulasi |
| 1× … 60× | Kecepatan simulasi (waktu nyata: 1 shipper per 4 menit, 1 pallet ±32 menit) |
| Kamera | Overview, Modul 1, Modul 2, Atas, Ikuti handlift (bisa diputar/zoom dengan mouse) |
| Label / Zona / Dinding penuh | Menampilkan label, zona lingkup & lorong, tinggi dinding |

## Basis data proses

| Parameter | Nilai |
| --- | --- |
| Cartoner | 30 cpm |
| Isi shipper | 120 karton, ±21 kg |
| Laju shipper | 1 per 4 menit |
| Pallet | 1200×1000×160, 8 shipper, tinggi ±934 mm (maks. 1350) |
| Batch contoh | B-001 PLCF 20 shipper, B-002 PLFB 12, B-003 PLCF 16, … (line clearance ±5 menit) |

## Revisi

- **R2 (geometri simulasi ini):** rel selatan gantry dipindah ke Y 5360, karena di Y 5775 rel menabrak kolom H bangunan. PS1/PS2 digeser ±370 mm ke utara supaya sejajar dengan PS3/PS4.
- R1: layout di atas denah RFQ, palletizing memakai gantry.

Status: konsep untuk penawaran dan pembahasan. Ini bukan gambar manufaktur, dan dimensi final ditentukan setelah survey lokasi.
