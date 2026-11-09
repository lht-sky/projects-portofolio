# Haleon PUL — Opsi B R4 · Simulasi 3D

Simulasi 3D konsep **PT Global Inti Sinergi** untuk RFQ *PUL Palletizing* Haleon. Revisi R4 menggunakan **1 robot ABB** (kelas IRB 460) yang mengerjakan dua tugas:

1. **Case packing per layer.** Robot mengambil 1 layer berisi 20 karton (5 × 4, ukuran karton 115 × 104 × 60) dari layer former, lalu memasukkannya ke shipper (591 × 432 × 387). Satu shipper berisi 6 layer, total 120 karton.
2. **Palletizing.** Robot mengambil shipper yang sudah disegel dan diberi label di pick station, lalu menyusunnya ke pallet P1 atau P2 dengan pola 2 × 2 × 2 (8 shipper per pallet).

Kedua tugas memakai **satu gripper foam universal** (pad ±565 × 405 dengan extension ≥ 400 mm). Shipper dibentuk oleh **case erector otomatis**, lalu ditutup **top case sealer** dan diberi **label batch print & apply**.

## Alur pallet

- Pallet kosong masuk lewat **pintu MAL IN**, lurus ke P2.
- Pallet penuh keluar lewat **pintu MAL OUT**, lurus dari P1.
- Pergerakan silang (MAL IN ke P1, P2 ke MAL OUT) dilakukan handlift di zona bebas 1510.
- Pallet dialokasikan per batch. Sisa di akhir batch ditutup sebagai pallet parsial.

## Paket penawaran

| Paket | Lingkup |
| --- | --- |
| A — Robot cell | Robot, gripper universal, pick station + barcode, pallet station P1/P2, light curtain, safety fence, panel A |
| B — Case packing | Conveyor infeed karton, layer former 5 × 4, case erector, packing station, top case sealer, label print & apply, panel B |

Paket A bisa dipasang lebih dulu dengan packing dan sealing manual. Paket B menyusul tanpa perlu robot tambahan.

## Membuka

Buka `index.html` di browser, atau aktifkan **GitHub Pages** (Settings → Pages → branch `main`, folder `/root`). Three.js 0.160.0 dimuat dari jsDelivr.

## Kontrol

| Kontrol | Fungsi |
| --- | --- |
| Jeda / Lanjut | Menghentikan atau melanjutkan waktu simulasi |
| 1× … 60× | Kecepatan simulasi. Dalam waktu nyata, 1 layer terbentuk tiap 40 s, 1 shipper tiap 240 s, 1 pallet ±32 menit |
| Kamera | Overview, Layer & shipper, Robot & pallet, Atas, Ikuti handlift. Bisa diputar dan di-zoom dengan mouse |
| Label / Zona / Pagar / Dinding | Menampilkan atau menyembunyikan elemen tampilan |

Panel status menampilkan:
- timeline siklus robot (24 × 10 s)
- status batch
- isi pallet station
- sinyal interface Paket B ↔ A (LAYER READY, BOX READY, BOX FULL, AT PICK)
- log kejadian

## Basis data proses

| Parameter | Nilai |
| --- | --- |
| Cartoner | 30 cpm, 1 layer (20 karton) tiap 40 s |
| Siklus robot per shipper | 6 × pick layer ±12 s + 1 × palletizing ±15 s = ±87 s dari 240 s |
| Utilisasi robot | ±30–36 % |
| Pallet | 1200 × 1000 × 160, 8 shipper, tinggi ±934 mm |

## Revisi

- **R4 (`index.html`):** 1 robot, layer pick 20 karton, gripper foam universal, case erector, top sealer, label otomatis, 2 pallet station di depan MAL OUT/IN.
- **R2 (`r2-gantry.html`):** konsep sebelumnya, yaitu cobot case packing 5-pack ditambah gantry palletizing 4 station. Disimpan sebagai arsip.

Status: konsep untuk penawaran dan pembahasan. Ini bukan gambar manufaktur. Dimensi final ditentukan setelah survey lokasi, dan tipe robot final ditentukan ABB.
