# Peta Fasilitas Publik Kota Medan

Peta web interaktif berbasis Leaflet yang menampilkan sebaran fasilitas publik di Kota Medan, mencakup fasilitas kesehatan, pendidikan, transportasi, dan ruang publik. Proyek ini dibuat sebagai Proyek Tahap 1 mata kuliah Pengembangan SIG Web dan mendukung SDG 11 (Kota dan Permukiman Berkelanjutan) serta SDG 9 (Industri, Inovasi, dan Infrastruktur).

## Latar Belakang

Warga sering kesulitan mengetahui lokasi fasilitas publik secara ringkas. Peta ini mengumpulkan fasilitas tersebut dalam satu tampilan sehingga lebih mudah ditemukan dan dibandingkan jaraknya.

## Fitur

- Tujuh pilihan peta dasar: OpenStreetMap, Esri Jalan, Esri Satelit, Esri Topografi, Esri Abu-abu Terang, Esri National Geographic, dan OpenTopoMap
- Lima layer tematik (kesehatan, pendidikan, transportasi, ruang publik, wisata dan budaya) yang dapat dinyalakan atau dimatikan melalui layer control dan filter kategori
- Data fasilitas berasal dari OpenStreetMap (Overpass Turbo) dan dimuat dari berkas data.geojson, sehingga mencapai ratusan titik
- Impor berkas GeoJSON melalui tombol Impor GeoJSON
- Pencarian nama fasilitas dan daftar fasilitas yang terhubung ke peta
- Penanda berwarna per kategori dengan popup berisi nama, jenis, alamat, jam layanan, dan koordinat
- Legenda dan atribusi data
- Tombol Lokasi Saya yang menampilkan fasilitas terdekat dari posisi pengguna
- Alat ukur jarak dengan beberapa titik
- Tampilan responsif untuk layar ponsel

## Teknologi

- Leaflet 1.9.4
- HTML, CSS, dan JavaScript
- Overpass Turbo untuk pengunduhan data OpenStreetMap
- Tile peta dari OpenStreetMap, Esri, dan OpenTopoMap

## Sumber dan Struktur Data

Data fasilitas berasal dari OpenStreetMap dan diunduh melalui Overpass Turbo untuk wilayah Kota Medan, lalu disimpan sebagai berkas `data.geojson` pada folder yang sama dengan `index.html`. Objek yang diambil memiliki atribut nama dan termasuk dalam tag OpenStreetMap berikut.

| Kategori | Tag OpenStreetMap |
|---|---|
| Kesehatan | amenity = hospital, clinic |
| Pendidikan | amenity = university, college, school |
| Transportasi | railway = station, amenity = bus_station |
| Ruang publik | leisure = park, place = square |
| Wisata dan budaya | tourism = attraction, museum, zoo |

Query yang digunakan tersimpan pada berkas `query_overpass.txt`. Peta membaca `data.geojson` saat dibuka. Jika berkas tersebut tidak ada, peta mencoba mengambil data langsung dari Overpass API, dan jika gagal akan menampilkan 11 data contoh. Berkas GeoJSON lain juga dapat dimuat melalui tombol Impor GeoJSON.

## Cara Menjalankan

1. Unduh atau kloning repositori ini.
2. Jalankan server lokal dari folder proyek:

   ```
   python -m http.server 8000
   ```

3. Buka `http://localhost:8000` di browser.

Pastikan berkas `data.geojson` berada satu folder dengan `index.html`.

Peta dasar OpenStreetMap membutuhkan akses melalui http atau https. Jika berkas dibuka langsung dari folder, peta otomatis memakai peta dasar Esri.

## Sumber Data dan Atribusi

- Data dan peta dasar: © OpenStreetMap contributors (lisensi ODbL)
- Peta dasar tambahan: Tiles © Esri dan © OpenTopoMap (CC-BY-SA)
- Pustaka peta: Leaflet

## Penulis

Nadya Lahfah  
NIM 241712051  
Kom B'24
