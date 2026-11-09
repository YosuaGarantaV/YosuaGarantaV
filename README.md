# Yosua Aldrin Garanta

Mahasiswa S1 Informatika, Universitas Amikom Yogyakarta. Saya membangun sistem berbasis large language model dan model machine learning, lalu mengujinya dengan data nyata. Angka di bawah selalu saya tulis bersama ukuran sampel atau pembandingnya, termasuk hasil yang belum sesuai harapan.

Minat: sistem multi-agen LLM, machine learning, dan rekayasa perangkat lunak.

## Ringkasan proyek

| Proyek | Jenis | Tahun | Alat utama |
|---|---|---|---|
| [Sistem multi-agen LLM untuk saham IDX](#skripsi-sistem-multi-agen-llm-untuk-simulasi-perdagangan-saham-di-bei) | Skripsi | 2026 | Python, LLM API, SQLite, pytest |
| [Tiny GPT berbahasa Indonesia](#tiny-gpt-model-bahasa-kecil-berbahasa-indonesia) | Tugas kuliah | 2026 | PyTorch, SentencePiece |
| [Prediksi laga sepak bola](#prediksi-hasil-laga-sepak-bola-dengan-random-forest) | Tugas kuliah | 2026 | pandas, scikit-learn |
| [Foto wajah ke gaya kartun](#foto-wajah-ke-gaya-kartun) | Percobaan pribadi | 2025 | PyTorch |
| [Jepret: toko kamera daring](#jepret-toko-daring-perlengkapan-kamera) | Proyek kelompok | 2025 | PHP, MySQL, Tailwind CSS |
| [Latihan pemrograman web](#latihan-pemrograman-web) | Tugas kuliah | 2025 | HTML, CSS, JavaScript |

## Skripsi: sistem multi-agen LLM untuk simulasi perdagangan saham di BEI

Repositori: [Multi_Agent](https://github.com/YosuaGarantaV/Multi_Agent) dan [prediction-backend](https://github.com/YosuaGarantaV/prediction-backend)

Satu koordinator mengatur enam peran agen LLM: analis, trader, anggota dewan teknikal, anggota dewan kontrarian, sentimen, dan evaluator. Tujuh belas gerbang deterministik di Python menjaga keputusan risiko yang tidak boleh diserahkan ke model, dan setiap keputusan tercatat di jejak audit. Bila semua model gagal, mesin heuristik tanpa LLM mengambil keputusan. Akurasi sistem dibandingkan dengan mesin heuristik itu pada tanggal yang sama, memakai uji berpasangan per tanggal dengan block bootstrap.

| Ukuran | Nilai |
|---|---|
| Periode berjalan langsung di pasar | 15 Juli sampai 6 September 2026 (8 pekan) |
| Prediksi tercatat | 3.721 |
| Panggilan model | 56.928, sebanyak 58,7% berstatus peringatan dan keputusan tetap keluar |
| Baris jejak audit | 148.668 |
| Selisih akurasi multi-agen dikurangi heuristik | −12,6 poin persentase, selang [−30,9; +3,8] |
| Portofolio simulasi | −4,45% saat IHSG naik 9,84% |

Kesimpulan: sistem tetap berjalan saat penyedia model gagal, tetapi keunggulan akurasinya belum terbukti. Rancangan delapan pekan ini hanya mampu mendeteksi selisih sekitar 29,7 poin persentase.

Kode di kedua repositori adalah versi Juli dan September 2026. Versi terbaru yang dipakai untuk naskah skripsi, dengan 282 tes otomatis, belum diunggah.

## Tiny GPT: model bahasa kecil berbahasa Indonesia

Repositori: [Mini-Gpt](https://github.com/YosuaGarantaV/Mini-Gpt)

Transformer decoder-only yang saya tulis dari nol di PyTorch: 6 layer, 8 head, embedding 256, konteks 128 token, sekitar 5 sampai 6 juta parameter. Model dilatih pada korpus berbahasa Indonesia bertema game FPS sekitar 18.500 kata, dengan empat mode tokenisasi: karakter, kata, BPE buatan sendiri, dan SentencePiece.

| Model | Val loss | Selisih val dan train | Perplexity | Bits per karakter |
|---|---:|---:|---:|---:|
| Dilatih dari nol | 2,79 | 1,42 | 16,3 | 1,75 |
| Pretraining lalu fine-tuning | 2,21 | 0,36 | 9,1 | 1,38 |

## Prediksi hasil laga sepak bola dengan Random Forest

Repositori: [football-random_forest](https://github.com/YosuaGarantaV/football-random_forest)

Klasifikasi tiga kelas (menang kandang, seri, menang tandang) dari 15.362 laga internasional sejak 2010 dengan Random Forest 100 pohon. Akurasi uji 45,88% (n = 3.073 laga), masih di bawah tebakan selalu menang kandang yang mencapai 48,9%. README repositori mencatat penyebabnya dan rencana fitur berikutnya.

## Foto wajah ke gaya kartun

Repositori: [imageGenerative](https://github.com/YosuaGarantaV/imageGenerative)

Generator bergaya ResNet di PyTorch untuk image-to-image. README repositori mencatat temuan utamanya: data tidak berpasangan dilatih dengan loss berpasangan, sehingga langkah berikutnya adalah pendekatan CycleGAN.

## Jepret: toko daring perlengkapan kamera

Repositori: [jepretln](https://github.com/YosuaGarantaV/jepretln)

Proyek kelompok empat orang: aplikasi web PHP berpola MVC tanpa framework, Tailwind CSS, dan panel admin dengan 11 modul. Bagian saya: halaman informasi pengguna (FAQ, syarat dan ketentuan, kebijakan privasi, kebijakan pengembalian, tentang kami), footer, navbar dan sidebar admin, serta perbaikan login admin.

## Latihan pemrograman web

Repositori: [5574_Yosua](https://github.com/YosuaGarantaV/5574_Yosua)

Tugas awal HTML, CSS, dan JavaScript: halaman artikel, CV, formulir dengan validasi, dan galeri dengan CSS Grid.

## Keterampilan

| Bidang | Alat dan teknik |
|---|---|
| LLM dan agen | API LLM multi-penyedia, tool calling, rantai model cadangan, gerbang deterministik |
| Machine learning | PyTorch, Transformer, tokenisasi BPE dan SentencePiece, transfer learning, scikit-learn |
| Statistik eksperimen | Uji berpasangan, block bootstrap, daya uji, baseline kelas mayoritas |
| Rekayasa perangkat lunak | Python, pytest, SQLite, Git |
| Web | PHP MVC, MySQL, Tailwind CSS, HTML, CSS, JavaScript |
