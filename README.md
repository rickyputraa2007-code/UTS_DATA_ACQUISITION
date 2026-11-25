
# UTS Akuisisi dan Manajemen Data

## Tema
Akuisisi dan Pengolahan Data Pariwisata

## Tujuan
Mengumpulkan, membersihkan, memeriksa, dan menggabungkan
data terkait pariwisata menggunakan Python.

## Sumber Data

1. Kementerian Pariwisata
   - Tenaga kerja pariwisata menurut provinsi 2018-2024.
   - Tenaga kerja pariwisata menurut subsektor 2018-2024.

2. BPS SIRUSA
   - Referensi kode dan nama 38 provinsi.

3. Open-Meteo
   - Data cuaca harian Denpasar tahun 2025.

4. Denpasar Open Data
   - Data kategori daya tarik wisata.

## Proses Pengolahan

1. Akuisisi dataset XLSX dan CSV.
2. Akuisisi data melalui API.
3. Scraping tabel dari halaman data publik.
4. Pemeriksaan robots.txt.
5. Pembersihan data.
6. Pencatatan provenance dan MD5.
7. Pemeriksaan kualitas data.
8. Penggabungan data menggunakan pandas merge.
9. Pemeriksaan hasil penggabungan.

## Hasil Penggabungan

File:
data/final/tenaga_kerja_pariwisata_gabungan_bps.csv

Jumlah baris: 242
Jumlah kolom: 4

Kunci penggabungan: kode_provinsi
Metode: left merge
Validasi: many_to_one

Seluruh 242 baris berhasil dicocokkan dengan referensi BPS.
Tidak ditemukan duplikat pada data final.

## Dokumentasi

- docs/provenance.csv
- docs/data_ethics_checklist.csv
- docs/robots_denpasarkota.txt

## Struktur Folder

UTS_DATA_ACQUISITION/
    data/
        raw/
        processed/
        final/
    docs/
    notebooks/
    README.md

## Catatan

Lisensi dan ketentuan penggunaan beberapa sumber masih
perlu diverifikasi pada portal resminya.


## Penggabungan Data Berbagai Metode Akuisisi

Proyek ini menggunakan beberapa metode akuisisi data:
1. Unduhan berkas Excel dari sumber pemerintah.
2. Pengambilan data melalui Open-Meteo Historical Weather API.
3. Web scraping data daya tarik wisata dari portal data Denpasar.

### Penggabungan Wisatawan dan Cuaca

Data wisatawan Nusantara Denpasar tahun 2023
digabungkan dengan data cuaca Open-Meteo tahun 2023.

Metode penggabungan:
- Jenis: Inner Join
- Kunci: tahun dan bulan
- Validasi: one_to_one
- Jumlah hasil: 12 baris
- Data tidak cocok: 0
- Nilai kosong: 0
- Duplikasi: 0

### File Hasil Penggabungan

- data/raw/cuaca_denpasar_2023_api.csv
- data/processed/cuaca_denpasar_2023_bulanan.csv
- data/final/wisatawan_cuaca_denpasar_2023.csv

Metadata penggabungan disimpan pada:
docs/metadata_merge_wisatawan_cuaca.csv

Dokumentasi sumber dan hash MD5 disimpan pada:
docs/provenance.csv

Lisensi dan atribusi mengikuti ketentuan masing-masing sumber.
