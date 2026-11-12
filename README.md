# 🖧💰🔐 NetPoly: Monopoli Keamanan Jaringan

Game papan bergaya monopoli untuk pembelajaran **Keamanan Jaringan** dan **shortcut komputer** (Kelas XI TKJ, tingkat menengah-sulit). Dimainkan langsung di browser, tanpa instalasi, tanpa server, dan tanpa internet.

## Fitur

- Papan 40 kotak, 2–4 pemain, dua dadu digital beranimasi
- 30 aset jaringan yang bisa dibeli, disewa, dan di-upgrade (level 1–3)
- Kotak Kesempatan (kartu acak), Audit Pajak, Denda Insiden, Wi-Fi Gratis, dan Karantina
- 51 soal level sedang dan sulit, diacak tanpa pengulangan, dengan pembahasan setiap jawaban
- Papan pemain langsung (koin dan jumlah aset), peringkat akhir, dan konfeti kemenangan
- Kontrol: petunjuk, suara on/off, mulai ulang, keluar
- Tampilan responsif dan nama pemain tersimpan di Local Storage

## Aturan permainan

1. Setiap pemain mulai dengan **1500 koin**. Melewati kotak MULAI mendapat **+200**.
2. **Aset belum dimiliki:** jawab soal dengan benar untuk membelinya (koin harus cukup).
3. **Aset milik lawan:** bayar sewa. Jika soal dijawab benar, sewa **diskon 50%**.
4. **Aset milik sendiri:** jawab benar untuk upgrade keamanan. Maksimal level 3, dan sewa naik tiap level.
5. **Karantina:** pada giliran berikutnya, jawab benar untuk bebas. Jika salah, giliran dilewati.
6. Pemain dengan koin di bawah 0 **bangkrut** dan keluar dari permainan.
7. Permainan selesai setelah **12 ronde** atau saat tinggal satu pemain. Pemenang adalah yang memiliki **koin + harga aset** terbesar.

## Materi soal

| Kelompok | Isi |
|---|---|
| Konsep keamanan | Defense in depth, least privilege, default deny, IDS vs IPS, hash dan integritas, enkripsi asimetris, VPN, DMZ, ACL, port security, patch management |
| Serangan | SQL Injection, XSS, MITM, ARP spoofing, DDoS, zero-day, ransomware, brute force, spear phishing, honeypot |
| Port dan protokol | SSH 22, Telnet 23, DNS 53, HTTPS 443, RDP 3389 |
| NIST CSF 2.0 | Penerapan fungsi Govern, Identify, Protect, Detect dalam skenario, serta prinsip CIA |
| Shortcut | Win+Shift+S, Win+V, Ctrl+Shift+T/N, Win+R/E/I, Shift+Delete, Win+Tab, Ctrl+Alt+Del, Alt+Enter, F12, Ctrl+Backspace, dan shortcut Terminal Linux (Ctrl+C, Ctrl+L, Ctrl+R, Tab) |

## Cara menjalankan

**Lokal:** unduh repositori ini lalu buka `index.html` di browser.

**Online lewat GitHub Pages:**

1. Unggah `index.html` dan `README.md` ke repositori GitHub.
2. Buka **Settings → Pages**.
3. Pada *Build and deployment*, pilih **Deploy from a branch**, branch `main`, folder `/ (root)`, lalu **Save**.
4. Tunggu 1–2 menit. Game bisa dibuka di `https://USERNAME.github.io/NAMA-REPO/`.

## Cara mengubah soal dan pengaturan

Semua pengaturan ada di bagian `CONFIG` di awal blok `<script>` pada `index.html`.

```js
// pilihan ganda: jawaban benar ditulis PERTAMA, pilihan diacak otomatis
pg(3, "Port bawaan SSH adalah ...", ["22", "23", "80", "443"], "SSH memakai port 22.")

// benar/salah
bs(2, "HTTPS memakai port 443.", true, "Benar.")
```

- Angka pertama adalah level: `1` mudah, `2` sedang, `3` sulit.
- `judul`, `mapel`, `materi`, `kelas`: teks pada halaman awal.
- `koinAwal`, `gajiMulai`, `maxRonde`: koin awal, gaji melewati MULAI, dan jumlah ronde.
- `aset`: daftar 30 nama aset di papan, berurutan dari kotak awal ke kotak akhir (harga naik otomatis).
- `soal`: bank soal.

Setelah mengedit soal, cek ulang kunci jawaban dan mainkan satu putaran untuk memastikan tidak ada error.

## Teknologi

HTML5, CSS3, dan JavaScript murni dalam satu file. Tanpa library eksternal dan tanpa koneksi internet.

## Lisensi

Bebas digunakan dan dimodifikasi untuk kegiatan pembelajaran. Tambahkan file `LICENSE` jika ingin menentukan lisensi tertentu.
