**# dokumentasi-jelajah-progo**<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dokumentasi Script | Jelajah-In Progo</title>

    <style>
        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            font-family: Arial, sans-serif;
            line-height: 1.7;
            color: #35443a;
            background: #f7f8f4;
        }

        header {
            background: #355e48;
            color: white;
            padding: 24px 8%;
        }

        header a {
            color: white;
            text-decoration: none;
        }

        main {
            max-width: 1000px;
            margin: 35px auto;
            padding: 0 22px;
        }

        section {
            background: white;
            padding: 24px;
            margin-bottom: 22px;
            border-radius: 12px;
            border: 1px solid #e3e8df;
        }

        h1, h2, h3 {
            color: #355e48;
        }

        code {
            background: #edf2eb;
            padding: 3px 6px;
            border-radius: 4px;
        }

        .file {
            font-weight: bold;
            color: #355e48;
        }

        .back {
            display: inline-block;
            margin-top: 10px;
            color: #355e48;
        }

        footer {
            text-align: center;
            padding: 22px;
            color: #68766c;
        }
    </style>
</head>

<body>
    <header>
        <h1 style="color:white;">Dokumentasi Script</h1>
        <p>Jelajah-In Progo — WebGIS Pariwisata Kabupaten Kulon Progo</p>
        <a href="index.html">← Kembali ke halaman utama</a>
    </header>

    <main>
        <section>
            <h2>1. Gambaran Umum</h2>
            <p>
                File script.js merupakan kode JavaScript yang mengatur
                interaksi dan fungsi utama WebGIS Jelajah-In Progo.
                Kode ini digunakan untuk memuat data wisata, menampilkan
                peta, mengelola pencarian, menyaring kategori, serta
                menampilkan informasi destinasi wisata.
            </p>
        </section>

        <section>
            <h2>2. Inisialisasi Program</h2>
            <p class="file">Fungsi: initMap() dan DOMContentLoaded</p>
            <p>
                Program dijalankan setelah struktur halaman HTML selesai
                dimuat. Proses awal meliputi inisialisasi peta, pemuatan
                data wisata, dan pengaturan event pada elemen halaman.
            </p>
            <p>
                Fungsi <code>initMap()</code> membuat peta menggunakan
                Leaflet, menentukan titik pusat awal di sekitar Kulon
                Progo, dan menambahkan peta dasar OpenStreetMap.
            </p>
        </section>

        <section>
            <h2>3. Pemuatan dan Pengolahan Data</h2>
            <p class="file">Fungsi: loadData() dan parseCSV()</p>
            <p>
                Fungsi <code>loadData()</code> mengambil file CSV dari
                repository GitHub. Setelah data berhasil dibaca,
                program memanggil fungsi-fungsi untuk memperbarui
                statistik, kategori, filter, tabel, dan marker peta.
            </p>
            <p>
                Fungsi <code>parseCSV()</code> memisahkan isi CSV menjadi
                baris dan kolom, menangani tanda kutip serta koma di
                dalam teks, kemudian menyusun data menjadi objek
                JavaScript berdasarkan nama kolom.
            </p>
            <p>
                Jika data gagal dimuat, program menampilkan pesan
                kesalahan pada tabel lokasi.
            </p>
        </section>

        <section>
            <h2>4. Pencarian dan Filter Kategori</h2>
            <p class="file">
                Fungsi: setupEvents(), renderFilters(), applyFilters()
            </p>
            <p>
                Fitur pencarian digunakan untuk menemukan destinasi
                berdasarkan nama wisata, kategori, kecamatan, desa,
                alamat, dan deskripsi. Filter kategori digunakan untuk
                menampilkan wisata berdasarkan kategori yang dipilih.
            </p>
            <p>
                Hasil pencarian dan filter diperbarui pada marker peta
                serta tabel daftar wisata. Tombol reset digunakan untuk
                mengembalikan filter ke kondisi awal.
            </p>
        </section>

        <section>
            <h2>5. Visualisasi Peta dan Marker</h2>
            <p class="file">
                Fungsi: renderMarkers(), createPopup(), markerColor()
            </p>
            <p>
                Fungsi <code>renderMarkers()</code> menampilkan lokasi
                wisata berdasarkan koordinat lintang dan bujur.
                Marker dibedakan berdasarkan kategori wisata dan
                dilengkapi pop-up informasi.
            </p>
            <p>
                Fungsi <code>createPopup()</code> menampilkan nama
                destinasi, kategori, lokasi, jam operasional, dan
                tiket masuk. Sementara itu, <code>markerColor()</code>
                menentukan warna marker berdasarkan kategori.
            </p>
        </section>

        <section>
            <h2>6. Tabel dan Informasi Destinasi</h2>
            <p class="file">
                Fungsi: renderTable(), selectDestination()
            </p>
            <p>
                Fungsi <code>renderTable()</code> menampilkan maksimal
                12 baris data pada tabel, termasuk nama wisata,
                kategori, kecamatan, jam operasional, dan tombol untuk
                melihat lokasi di peta.
            </p>
            <p>
                Fungsi <code>selectDestination()</code> memperbarui
                panel informasi destinasi, meliputi deskripsi, lokasi,
                kategori, koordinat, fasilitas, serta tautan rute
                menuju Google Maps.
            </p>
        </section>

        <section>
            <h2>7. Statistik dan Lokasi Pengguna</h2>
            <p class="file">
                Fungsi: updateStatistics(), getCategories()
            </p>
            <p>
                Fungsi <code>updateStatistics()</code> menghitung
                jumlah data wisata, kecamatan unik, dan kategori unik.
                Fungsi <code>getCategories()</code> menyusun daftar
                kategori yang tersedia dari data CSV.
            </p>
            <p>
                Tombol lokasi pengguna memanfaatkan Geolocation API
                pada browser untuk memusatkan peta ke posisi pengguna
                apabila izin lokasi diberikan.
            </p>
        </section>

        <section>
            <h2>8. Fungsi Pendukung</h2>
            <p class="file">
                Fungsi: renderCategoryOverview(),
                renderSearchResults(), normalizeCategory(),
                escapeHtml()
            </p>
            <p>
                Fungsi-fungsi tersebut digunakan untuk menampilkan
                ringkasan kategori, hasil pencarian, menyeragamkan
                teks kategori untuk tampilan, dan mengamankan teks
                yang dimasukkan ke dalam HTML agar karakter khusus
                tidak ditafsirkan sebagai elemen HTML.
            </p>
        </section>

        <section>
            <h2>9. Teknologi yang Digunakan</h2>
            <ul>
                <li>JavaScript untuk logika dan interaksi WebGIS.</li>
                <li>Leaflet untuk menampilkan peta interaktif.</li>
                <li>OpenStreetMap sebagai peta dasar.</li>
                <li>CSV yang diambil dari GitHub sebagai sumber data.</li>
                <li>Geolocation API untuk mengakses lokasi pengguna.</li>
                <li>Google Maps untuk menyediakan tautan rute.</li>
            </ul>
        </section>

        <a class="back" href="index.html">
            ← Kembali ke dokumentasi utama
        </a>
    </main>

    <footer>
        <p>Dokumentasi WebGIS Jelajah-In Progo</p>
    </footer>
</body>
</html>
