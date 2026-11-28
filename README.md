# Rencana Kerja Game Jam: "Back to Basics" (Hari 3–10)

- **Tema Game Jam:** Back to Basics
- **Batas Waktu:** 10 Hari (Rencana Eksekusi Hari ke-3 s.d. Hari ke-10)
- **Anggota Tim:** Rifat, Kafka, Raveka, Hizkia

---

## 1. Ringkasan Konsep Game

- **Premis:** Sebuah portal misterius muncul di dunia _Cubism_ yang mendatangkan kubu _Realism_ bersama sebuah menara tinggi. Semakin tinggi lantai menara, gaya visual dan arsitekturnya semakin modern dan realistis. Kubu _Cubism_ diculik ke dalam menara dan diubah/terinfeksi menjadi kubu _Realism_.
- **Mekanik Naik Menara:** Karakter utama (MC) memasuki menara untuk menyelamatkan kubu _Cubism_. MC mengalahkan kubu _Realism_ dengan cara menyerapnya (_absorb_). Setelah menaklukkan Stage 1, MC memperoleh kekuatan **Purify** untuk mengembalikan kubu _Cubism_ yang terinfeksi ke wujud asalnya (_Back to Basics_). Setiap stage yang dikalahkan akan memberikan _upgrade_ agar MC bisa melewati rintangan (_obstacle_) yang lebih menantang sampai paling atas.
- **Klimaks & Mekanik Turun Menara:** Setelah mengalahkan Bos _Realism_ di puncak, menara mulai runtuh dan MC harus melarikan diri turun ke lantai dasar. Di setiap tahap penurunan, pemain wajib **membuang kekuatan yang dimilikinya satu per satu** sambil terus melawan atau menghindari musuh hingga seluruh kekuatan habis dan MC kembali menjadi sosok _Cubism_ biasa (_Back to Basics_).

---

## 2. Pembagian Peran Tim

> **Catatan:** Beban aset art untuk Rifat diminimalkan agar fokus penuh di logika dan pemrograman.

- **Rifat — Lead Gameplay Programmer**
  - Mekanik inti karakter (gerak & kontrol), sistem _combat_ dan _absorb_, kemampuan _Purify_ (mengembalikan _Realism_ ke _Cubism_), sistem 3 _power_ (aktif saat naik, dinonaktifkan/dibuang saat turun), serta AI musuh dan Bos.
- **Kafka — System Programmer & Level Designer**
  - Arsitektur stage menara (Lantai 1–3 + Ruang Bos), _Game Manager_ (transisi lantai, pemicu menara runtuh, _checkpoint_, _Game Over_, _Restart_), penyusunan tata letak level, serta integrasi UI ke kode.
- **Raveka — Lead Character & Environment Artist**
  - Aset visual MC, warga/musuh _Cubism_ vs _Realism_ (termasuk versi transisi/terinfeksi), Bos akhir, serta _tileset_/aset menara yang berevolusi dari geometris sederhana ke modern/realistis.
- **Hizkia — UI/UX, VFX & Audio Designer**
  - Desain antarmuka (layar pilih _power_, layar buang _power_, HUD, _Main Menu_, _Pause_, _Ending_), efek partikel (_absorb_, _purify_, reruntuhan), BGM & SFX, serta dukungan aset dekorasi ringan dan QA/_playtesting_.

---

## 3. Batasan Scope Realistis (Kunci di Awal Hari ke-3)

1. **Struktur Menara (3 Lantai + 1 Arena Bos):** Lantai 1 (nuansa _Cubism_ mulai terkontaminasi), Lantai 2 (transisi modern/detail), Lantai 3 (sangat realistis/kompleks), dan Puncak (Arena Bos).
2. **Jumlah Kekuatan (3 Power Utama):** Pas dengan jumlah lantai. Saat naik, MC membuka 1 _power_ tiap kuota _absorb_ terpenuhi (contoh: _Dash_, _Range/Area Attack_, dan _Shield_). Saat turun, MC wajib membuang 1 _power_ di setiap transisi lantai hingga kembali polos di lantai dasar.
3. **Daur Ulang Peta saat Fase Turun:** Gunakan tata letak Lantai 3 $\rightarrow$ 2 $\rightarrow$ 1 yang sama secara terbalik ketika menara runtuh, namun ubah atmosfernya (pencahayaan merah darurat, puing jatuh, jalur sebagian terblokir, tempo musik dipercepat) untuk menghemat waktu pengerjaan level dan art.

---

## 4. Jadwal & Pembagian Tugas (Hari ke-3 sampai Hari ke-10)

| Hari & Target                                  | Rifat (Gameplay Code)                                                                                                                             | Kafka (System & Level)                                                                                                                                               | Raveka (Character & Env Art)                                                                                                             | Hizkia (UI, VFX & Audio)                                                                                                                              |
| :--------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------ | :------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Hari 3:**<br>Prototipe Kasar & Art Direction | Buat pergerakan MC, serangan dasar, sistem HP, dan mekanik _absorb_ musuh menggunakan bentuk kotak/kapsul sementara.                              | Susun struktur _project_ & _scene_ menara. Buat _whitebox_ (denah kasar) Lantai 1 dan sistem pindah lantai.                                                          | Tentukan palet warna & gaya visual 3 tingkat menara (_Cubism_ $\rightarrow$ _Realism_). Mulai buat aset MC & 1 musuh dasar.              | Buat _wireframe_ HUD (HP & bar _Absorb_), desain kasar layar pilih _power_, dan kumpulkan/buat SFX dasar (pukul, _absorb_).                           |
| **Hari 4:**<br>Mekanik Inti Naik Menara        | Implementasi _skill_ _Purify_ (ubah musuh terinfeksi balik jadi _Cubism_) setelah Lantai 1, plus kode untuk 3 _power_ utama.                      | Hubungkan kuota _absorb_ ke pemicu buka _power_. Buat denah kasar Lantai 2 & 3 serta sistem _spawner_ musuh.                                                         | Selesaikan aset Lantai 1 & 2, animasi dasar MC, dan 2 tipe musuh _Realism_ (+ versi _Cubism_ setelah di-_purify_).                       | Buat aset UI final untuk HUD dan _pop-up_ pemilihan _power_. Mulai buat efek partikel _absorb_ dan _purify_.                                          |
| **Hari 5:**<br>Bos & Mekanik Runtuh (Turun)    | Buat AI Bos _Realism_ (cukup 2–3 pola serangan jelas) dan sistem buang _power_ (menonaktifkan _skill_ pilihan pemain satu per satu).              | Buat _event_ menara runtuh setelah Bos kalah, _trigger_ kamera bergetar, rintangan puing jatuh, dan alur balik Lantai 3 $\rightarrow$ 1.                             | Buat desain & animasi Bos _Realism_ serta aset lingkungan Lantai 3 (paling detail/modern) dan versi retak/hancur untuk fase turun.       | Buat UI khusus pengorbanan/buang _power_ (nuansa tegang), VFX reruntuhan, dan susun BGM (simpel $\rightarrow$ modern $\rightarrow$ panik saat kabur). |
| **Hari 6:**<br>Integrasi Penuh (Target Alpha)  | Gabungkan semua skrip (MC, 3 _power_, musuh, Bos) dan perbaiki _bug_ logika antar-mekanik agar alur naik-turun bisa ditamatkan.                   | Masukkan semua aset dari Raveka & Hizkia ke Lantai 1–3 & Ruang Bos. Pasang alur _Main Menu_ $\rightarrow$ _Gameplay_ $\rightarrow$ _Ending_ $\rightarrow$ _Restart_. | Selesaikan sisa aset lingkungan, objek interaksi (portal awal/akhir), dan efek visual perubahan MC kembali jadi _Cubism_ polos.          | Pasang semua SFX & BGM ke _engine_, lengkapi layar _Main Menu_, _Pause_, _Game Over_, dan ilustrasi/teks _Ending_.                                    |
| **Hari 7:**<br>Feature Freeze & Polish Awal    | Stop fitur baru. Fokus perbaiki _bug gameplay_, atur responsivitas kontrol, dan pastikan tidak ada _softlock_ saat _power_ habis di lantai dasar. | _Balancing_ desain level: cek jarak lompatan/rintangan saat turun ketika pemain sudah membuang _power_ (pastikan tetap bisa dilewati tanpa _power_).                 | Rapikan detail visual, pencahayaan (_lighting_) tiap lantai agar transisi _Cubism_ ke _Realism_ kontras, dan perbaiki animasi yang kaku. | Poles transisi UI, tambahkan _tutorial prompt_ singkat di Lantai 1 (tombol gerak, serap, _purify_), dan seimbangkan volume audio.                     |
| **Hari 8:**<br>Playtest Internal & Balancing   | Pantau _playtest_ tim, catat dan perbaiki _bug_ prioritas tinggi (terutama di fase Bos dan saat membuang _power_).                                | Atur ulang jumlah HP musuh, kuota _absorb_, dan kecepatan reruntuhan berdasarkan hasil tes agar kurva kesulitan terasa pas.                                          | Buat aset pendukung halaman _submission_ (_cover art_, ikon game, _banner_) sambil memperbaiki _glitch_ visual yang ditemukan saat tes.  | Lakukan QA _testing_ ekstrem (coba mati di tiap lantai, tes semua urutan buang _power_) dan catat daftar _bug_ untuk Rifat & Kafka.                   |
| **Hari 9:**<br>Game Feel & Build Uji Coba      | Tambahkan _game feel_ (_hit-stop_, _knockback_, _invincibility frame_) dan bantu Kafka melakukan _Test Build_ pertama di luar _engine_.           | Lakukan _Test Build_ (WebGL/Windows sesuai aturan jam), uji di PC/browser lain untuk memastikan tidak ada _error_ saat di-_export_.                                  | Finalisasi aset halaman _submission_ (ambil _screenshot_ terbaik dari tiap lantai yang menunjukkan transisi visual).                     | Rekam cuplikan _gameplay_ pendek (GIF/video) untuk promosi, tulis deskripsi game & daftar kontrol, lalu cek ulang semua teks/kredit tim.              |
| **Hari 10:**<br>Final Build & Submission       | _Standby_ perbaiki _bug_ kritis saja (jangan ubah kode besar). Bantu cek hasil _build_ final.                                                     | _Export Final Build_, pastikan ukuran file sesuai batas platform gamejam, dan lakukan proses _upload_.                                                               | Cek tampilan visual halaman _submission_ dan bantu uji main _Final Build_ langsung dari tautan yang sudah diunggah.                      | Finalisasi halaman _submission_, verifikasi bahwa game bisa dijalankan oleh orang lain, dan _submit_ minimal 3–4 jam sebelum _deadline_.              |

---

## 5. Aturan Main Harian Tim

- **Check-in 10 Menit Setiap Malam:** Evaluasi progres harian masing-masing anggota dan pastikan _merge_ proyek (jika menggunakan Git) dilakukan rutin agar tidak terjadi konflik _scene_ menjelang tenggat waktu.
- **Desain Level Turun Harus "Power-Agnostic":** Saat pemain turun di lantai terakhir tanpa satu pun _power_ tersisa, seluruh rintangan wajib tetap bisa dilewati hanya dengan gerakan dasar (_Back to Basics_). Kekuatan yang tersisa seharusnya hanya mempermudah, bukan menjadi syarat mutlak melewati jalur.
- **Cutoff Fitur di Malam Hari ke-7:** Fitur apa pun yang belum selesai pada malam Hari ke-7 sebaiknya dipotong. Game yang singkat namun utuh dari awal, pertarungan Bos, hingga _ending_ yang mulus jauh lebih baik dibandingkan game ambisius yang penuh _bug_.
