# Takwim-Waktu-Solat
File ini mengandungi kod untuk menghasilkan takwim solat menggunakan perisian Python dan Skyfield API.

#### Takwim Hijrah
1. File ini mengandungi kod bagi penghasilan takwim hijrah, sama seperti projek Takwim Hijrah pada repository saya
2. Takwim yang dihasilkan melalui perisian ini hanya untuk kegunaan peribadi. Sila rujuk takwim waktu solat yang dikeluarkan oleh JAKIM atau Jabatan Mufti Negeri masing-masing untuk pengesahan. Semoga bermanfaat!

## Cara menghasilkan takwim Waktu Solat Tahunan
1. Masukkan lokasi latitud dan longitud di kawasan yang anda mahukan
2. Masukkan tahun masihi yang berkaitan
3. Lancarkan kesemua kod mengikut turutan

## Kaedah penentuan waktu solat 
Berikut adalah kaedah yang digunakan bagi penentuan waktu solat

### Waktu subuh
1. Kedudukan pusat matahari pada -18 darjah di bawah ufuk
2. Kedudukan ini diambil menggunakan API dark_twilight_day

### Waktu syuruk dan maghrib
1. Kedudukan pusat matahari pada -50 arka minit (-0.8333 darjah) di bawah ufuk
2. Tambahan -50 arka minit adalah daripada anggaran separuh diameter sudut matahari (16 arka minit) dan anggaran pembiasan (34 arka minit)
3. Syuruk adalah ketika hujung piring matahari mencecah ufuk tampak, manakala maghrib adalah ketika keseluruhan piring matahari berada dibawah ufuk tampak
4. Kedudukan ini diambil menggunakan API dark_twilight_day

### Waktu zohor
1. Masa transit matahari + 1 minit 4 saat (anggaran separuh diameter sudut Matahari = 16 arka minit)
2. Masa transit diambil menggunakan API meridian_transit

### Waktu asar
1. Terdapat 2 sudut yang perlu diambil kira iaitu sudut zenith matahari ketika transit, dan sudut ketika matahari menghasilkan bayang-bayang sesuatu objek yang sama panjang dengan panjang objek tersebut ditambah dengan bayang-bayang ketika transit. 
2. Sila rujuk pada gambar 'Terbitan waktu solat Asar'. 
3. Penghasilan waktu asar menggunakan API find_discrete.
4. Ketepatan waktu asar mempunyai ketepatan sekitar 2.4 saat
5. Kod 'function' waktu asar dibuat di luar 'function' waktu solat lain kerana kaedah yang lebih kompleks
6. Penghasilan waktu asar ini mengambil masa yang agak lama berbanding dengan waktu solat lain. Jika komputer anda tidak mempunyai CPU yang bagus, anda boleh skip pada pelancaran kod waktu asar bagi mengelakkan komputer anda menjadi perlahan

### Waktu isyak
1. Kedudukan pusat matahari pada -18 darjah di bawah ufuk
2. Kedudukan ini diambil menggunakan API dark_twilight_day
