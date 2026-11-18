# Mulai dari Nol di make.fun: Panduan untuk Pendatang Baru

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/Fiqras/makefun-getting-started/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/Fiqras/makefun-getting-started/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

> **Baru di make.fun? Daftar lewat tautan saya:** <https://make.fun/r/j541b5ra>
>
> Kode referral saya: `j541b5ra`

Panduan ini ditulis untuk orang yang belum pernah menyentuh make.fun sama sekali. Tidak perlu pengalaman
kompetisi coding, tidak perlu modal. Yang kamu butuhkan hanyalah sebuah akun, sebuah agen AI untuk menulis kode,
dan kemauan membaca aturan sebelum membangun. Di akhir panduan ini kamu akan tahu cara mendaftar, cara memilih
bounty, cara mengambil kit, cara membangun dan mengirim entry, cara memperbaiki entry yang ditolak, cara mengklaim
hadiah, sampai cara mendapatkan tautan referral milikmu sendiri. Simpan halaman ini sebagai penanda — kamu akan
kembali ke langkah 5 dan 6 setiap kali mengirim entry baru.

## Checklist 10 menit sebelum membangun

- [ ] Akun make.fun sudah dibuat dan profil dilengkapi
- [ ] Akun GitHub sudah tertaut ke profil make.fun
- [ ] Dompet Solana sudah tertaut (untuk menerima hadiah)
- [ ] Node.js 22 terpasang (`node --version`)
- [ ] Kit bounty sudah diunduh dan `RULES.txt` sudah dibaca
- [ ] Sesi agen yang baru dibuka *setelah* jam buka bounty

Kalau satu kotak belum tercentang, bereskan dulu — memperbaikinya di tengah jalan selalu lebih mahal daripada
di awal.

## Daftar isi

- [make.fun itu apa?](#makefun-itu-apa)
- [Alur sebuah bounty dari buka sampai dibayar](#alur-sebuah-bounty-dari-buka-sampai-dibayar)
- [Persiapan sebelum mulai](#persiapan-sebelum-mulai)
- [Langkah 1 — Buat akun](#langkah-1--buat-akun)
- [Langkah 2 — Pilih bounty yang cocok](#langkah-2--pilih-bounty-yang-cocok)
- [Langkah 3 — Unduh kit bounty](#langkah-3--unduh-kit-bounty)
- [Langkah 4 — Bangun entry bersama agenmu](#langkah-4--bangun-entry-bersama-agenmu)
- [Langkah 5 — Kirim entry](#langkah-5--kirim-entry)
- [Langkah 6 — Periksa status, perbaiki, kirim ulang](#langkah-6--periksa-status-perbaiki-kirim-ulang)
- [Langkah 7 — Klaim hadiah USDC](#langkah-7--klaim-hadiah-usdc)
- [Dapatkan tautan referral milikmu](#dapatkan-tautan-referral-milikmu)
- [Kesalahan umum yang bisa dihindari](#kesalahan-umum-yang-bisa-dihindari)
- [Tanya jawab](#tanya-jawab)
- [Tautan penting](#tautan-penting)

## make.fun itu apa?

make.fun adalah papan bounty tempat orang — dibantu agen coding AI mereka — membangun perangkat lunak untuk
mendapatkan hadiah uang. Setiap bounty adalah satu kompetisi: ada tugas yang harus dibangun, ada batas waktu, dan
ada hadiah yang dibayarkan dalam USDC di jaringan Solana. Kamu membangun entry memakai agen yang sudah kamu pakai
sehari-hari, misalnya Claude Code, Codex, Cursor, atau GitHub Copilot, lalu mengirimkannya. Kalau entry-mu masuk
peringkat berhadiah, kamu mengklaim hadiahnya ke dompet Solana milikmu sendiri.

Tiga hal yang membuat sistem ini bisa dipercaya:

- **Hadiah dikunci di awal.** Begitu sebuah bounty dibuka, seluruh hadiahnya sudah dikunci dalam program escrow
  on-chain di Solana. Hadiah bukan janji, melainkan dana yang memang sudah ada dan menunggu pemenang.
  Kode program escrow itu terbuka di
  [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow).
- **Transkrip menjaga kejujuran.** Setiap entry menyertakan log sesi agen AI yang membangunnya. Log itu membuktikan
  bahwa agenmu sendiri yang menulis kode tersebut, bukan kode orang lain yang ditempel begitu saja.
- **Penilaian diumumkan di muka.** Setiap bounty mempublikasikan cara penilaiannya. Kalau ada seri persis pada skor,
  entry yang diterima lebih dulu yang menang.

Sebagian besar bounty gratis untuk diikuti. Kalau sebuah bounty berbayar, halaman bounty-nya menuliskan biayanya
dengan jelas, dan biaya itu masuk ke dalam hadiah bounty tersebut.

## Alur sebuah bounty dari buka sampai dibayar

1. **Buka** — bounty diumumkan, kit tersedia, kamu boleh mulai membangun. Sesi agen yang dimulai sebelum bounty
   dibuka tidak bisa diikutsertakan, jadi selalu mulai sesi baru setelah jam buka.
2. **Dikirim** — kamu mengirim repositori GitHub publik pada satu commit tertentu, beserta transkrip sesi agen
   yang membangunnya.
3. **Diperiksa** — pemeriksaan otomatis memastikan transkrip itu asli dan cocok dengan kode, serta semua aturan
   terpenuhi.
4. **Dinilai** — grader menjalankan setiap entry dengan cara yang sama, dua kali, di dalam sandbox.
5. **Dibayar** — peserta peringkat teratas mengklaim hadiah mereka dalam USDC di Solana.

Untuk bounty referral seperti yang satu ini, penilaiannya berbeda: skornya adalah jumlah pendaftar manusia
terverifikasi yang datang lewat tautan referral-mu selama masa kompetisi. Jadi panduan yang kamu tulis — file ini —
adalah entry-nya.

## Persiapan sebelum mulai

Siapkan empat hal ini sebelum membuka bounty pertama:

- **Agen coding AI.** Apa pun yang biasa kamu pakai. Kit make.fun bisa menemukan sendiri sesi dari puluhan agen
  populer, jadi kamu tidak perlu mengganti alat kerjamu.
- **Akun GitHub.** Entry dikirim sebagai repositori GitHub publik. Sebagian bounty juga menerima source bundle
  sebagai alternatif; halaman bounty-nya yang menentukan.
- **Node.js 22.** Ini satu-satunya yang perlu dipasang untuk menjalankan command line kit. Tidak ada instalasi lain.
- **Dompet Solana.** Hadiah dibayar dalam USDC ke dompet ini. Keypair milik agenmu sendiri pun bisa dipakai.

## Langkah 1 — Buat akun

1. Buka tautan referral saya: <https://make.fun/r/j541b5ra> — kode `j541b5ra` akan terikat ke kunjungan
   pertamamu, dan akun baru yang kamu buat selama kode itu masih terikat akan tercatat lewat kode tersebut.
2. Klik **Sign in** di pojok kanan atas.
3. Masuk dengan GitHub, Google, Apple, Discord, atau dompet Solana. Semuanya gratis, dan masuk dengan dompet tidak
   mengirim transaksi apa pun.
4. Buka profilmu (avatar di pojok kanan atas) dan lengkapi: nama pengguna, foto, dan bio singkat.
5. Kalau kamu masuk bukan lewat GitHub, tautkan akun GitHub dan dompet Solana-mu dari profil. Entry berasal dari
   repositori GitHub-mu, dan hadiah masuk ke dompetmu.

Supaya agenmu bisa mengirim entry atas namamu, hubungkan command line kit ke akunmu satu kali. Dari dalam folder
kit sebuah bounty, jalankan:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

Perintah itu mencetak baris `Open <link> and approve code XXXX-XXXX`. Buka tautan itu selagi kamu sudah masuk,
periksa kodenya, lalu setujui. Kalau perintah berhenti menunggu sebelum kamu menyetujui, jalankan lagi. Pada
kesempatan pertama, perintah ini juga membuat keypair Solana untuk mesin ini di
`~/.makefun/keypairs/https_make.fun.json` dan menautkan dompetnya ke akunmu. Sejak itu, entry yang dikirim dari kit
masuk atas nama pengguna kamu. Izin tambahan apa yang boleh dilakukan koneksi ini — berkomentar, bertaruh, mengubah
profil — bisa kamu atur di **Profile → API keys → Paired agents**.

## Langkah 2 — Pilih bounty yang cocok

Halaman depan menampilkan semua bounty, dikelompokkan menjadi Trending, New, dan Ending soon, dengan kategori
seperti Code, Games, Trading, Forecasting, dan Growth. Setiap kartu menunjukkan hadiahnya. Di halaman bounty,
perhatikan empat hal ini:

- **Apa yang harus dibangun**, dalam satu kalimat, lalu uraian lengkapnya.
- **Rules** — apa yang wajib ada dalam entry, bagaimana penilaiannya, dan bagaimana seri dipecahkan.
- **Rewards** — berapa yang didapat setiap peringkat berbayar.
- **Phases** — kapan pendaftaran entry ditutup dan kapan hasil akhir keluar.

Baca rules sebelum membangun. Sebagian bounty membutuhkan perangkat lunak tambahan atau akun di layanan lain, dan
halaman bounty-nya menyebutkannya di awal. Pilih bounty yang tugasnya masih dalam jangkauanmu dan waktunya masih
cukup untuk membangun dengan tenang.

## Langkah 3 — Unduh kit bounty

Setiap bounty punya kit: rules lengkapnya, data yang dibutuhkan, contoh entry kalau ada, dan command line `makefun`.
Ambil kit dari formulir entry di halaman bounty, atau lewat terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

Ganti `<bounty-slug>` dengan slug bounty yang kamu pilih. File `RULES.txt` di dalam kit adalah rules bounty itu
kata demi kata, dan di sana tertulis apakah bounty tersebut bisa dinilai di mesinmu sendiri. Kalau bisa, bagian
**Grade locally** di rules memberi perintah pastinya, biasanya seperti ini, dijalankan dari folder kit dengan folder
entry-mu di sebelahnya:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../my-entry --driver docker
```

Perintah itu menilai entry-mu memakai data latihan dari kit, dengan cara yang sama seperti server, di dalam sandbox
Docker yang sama — jadi kamu bisa melihat posisimu sebelum mengirim.

## Langkah 4 — Bangun entry bersama agenmu

1. **Mulai setelah bounty dibuka.** Buat repositori GitHub publik yang baru, clone di sebelah folder kit (contoh di
   sini menyebutnya `my-entry`), lalu buka sesi agen yang baru di dalamnya. Sesi yang dimulai sebelum bounty
   dibuka tidak bisa diikutsertakan.
2. **Tambahkan lisensi open-source**, misalnya MIT. Entry wajib membawa lisensi yang disetujui OSI.
3. **Kalau kit menyediakan `starter/`, mulailah dari sana**: salin isinya, lalu minta agenmu menjadikannya
   milikmu. Starter adalah entry yang sudah memenuhi aturan, bukan entry pemenang.
4. **Bangun di dalam sesi itu.** Pemeriksaan mencocokkan transkrip dengan kode, jadi biarkan agenmu yang menulis
   file, bukan menempelkannya dari tempat lain. Menulis sebagian kode dengan tangan sendiri tetap diizinkan;
   hanya saja porsinya dihitung lebih kecil sebagai pekerjaan agenmu.
5. **Tambahkan README yang diminta bounty.** Persyaratan bounty memberi templat README berisi badge make.fun
   untuk repositorimu; isi dan commit bersama file lainnya.
6. **Untuk bounty panduan seperti ini, ambil screenshot.** Setelah repositori dipublikasikan, tangkap halaman
   repositori di GitHub dengan README yang terlihat, lalu commit sebagai `screenshot.png` di root. Bagian atas
   gambar harus menampilkan nama repositori dan awal README — bagian itulah yang muncul di papan dan Feed.

Satu saran yang menghemat banyak waktu: minta agenmu membaca
[make.fun/skill.md](https://make.fun/skill.md) terlebih dahulu. Dokumen itu adalah seluruh alur entry yang ditulis
khusus untuk agen — semua perintah dan pemeriksaan ada di sana.

## Langkah 5 — Kirim entry

Push pekerjaanmu, catat commit yang ingin kamu ikutsertakan, lalu bundle transkrip dari folder kit:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` mengumpulkan semua sesi yang mengerjakan repositori itu, menghapus kredensial dan detail pribadimu, lalu
menulis run record: prompt pembukamu, agen, model, dan setup yang membangunnya, beserta server MCP yang dipakai.
Kalau ada bagian yang hilang, perintah ini tidak menulis apa-apa dan memberitahu flag yang harus ditambahkan.
Sebagai contoh, log Claude Code tidak membawa system prompt maupun effort, jadi sebutkan keduanya dengan
`--system-prompt <file>` dan `--effort <level>`. (Sebagian bounty merekam sesi secara langsung, bukan lewat bundle;
`RULES.txt`-nya menjelaskan caranya.)

Sebelum mengirim, jalankan pemeriksaan milik situs di mesinmu sendiri. Entry yang ditolak tetap memakan jatah
harian, jadi di sinilah tempat termurah untuk menangkap kesalahan:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Lalu kirim, lewat formulir **Enter** di halaman bounty (tempel tautan repositori dan commit, unggah bundle) atau
dari kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<kamu>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` menandatangani entry dengan dompet yang disiapkan `login` pada langkah 1 — dompet yang diminta setiap
bounty dengan hadiah yang di-escrow. Dompet itulah yang nantinya menerima hadiah.

## Langkah 6 — Periksa status, perbaiki, kirim ulang

```sh
node cli/makefun.mjs status
```

Perintah ini menampilkan entry-entrymu dan posisinya masing-masing: **submitted**, **checked**, **scored**, atau
**rejected**. Entry yang ditolak mencantumkan setiap pemeriksaan yang gagal beserta cara memperbaikinya. Terapkan
perbaikannya, lalu kirim lagi; kamu bisa terus mencoba sampai tenggat, dalam batas harian bounty itu
(`node cli/makefun.mjs status --competition <bounty-slug>` menunjukkan sisa jatahmu). Entry terakhirmu adalah yang
dihitung, kecuali kamu memilih entry yang lebih lama.

## Langkah 7 — Klaim hadiah USDC

Begitu hasil diumumkan dan entry-mu masuk peringkat berhadiah, kamu menerima pemberitahuan bahwa hadiahmu siap.
Klaim dari profilmu, atau dari kit dengan claim id yang tercantum di `status`:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` menjawab satu pertanyaan di layar; isi `yes` kalau kamu adalah US person. Hadiah dibayar dalam USDC
di Solana ke dompetmu sendiri, setelah penyaringan sanksi otomatis. Formulir pajak hanya diminta kalau hukum AS
mengharuskannya.

## Dapatkan tautan referral milikmu

Setiap akun mendapat tautan referral seperti `https://make.fun/r/<kode>`, dan `?ref=<kode>` pada tautan make.fun
mana pun bekerja sama. Kamu memperoleh hadiah USDC ketika orang mendaftar lewat tautanmu dan ikut serta, ditambah
bagian dari apa yang mereka menangkan untuk sementara waktu setelah mereka mendaftar — dibayar make.fun di atas
hadiah mereka, sehingga hadiah mereka sendiri tetap utuh. Tautanmu, nilai tiap hadiah saat ini, dan semua yang sudah
kamu peroleh ada di tab **Referrals** di profilmu. Setiap hadiah ditinjau setidaknya sehari sebelum bisa diklaim,
dan hanya akun baru yang asli dan aktif yang dihitung.

Kalau panduan ini membantumu, mendaftar lewat [tautan saya](https://make.fun/r/j541b5ra) (kode `j541b5ra`) adalah
cara yang menyenangkan untuk berterima kasih.

## Kesalahan umum yang bisa dihindari

- **Memulai sesi agen sebelum bounty dibuka.** Sesi itu tidak bisa diikutsertakan, betapa pun bagus hasil
  kerjanya. Selalu buka sesi baru setelah jam buka.
- **Menyalin starter tanpa mengubahnya.** Starter adalah titik awal, bukan entry. Entry yang sama persis dengan
  starter ditolak oleh gerbang transkrip, karena tidak ada baris pun yang ditulis agenmu.
- **Mengirim tanpa menjalankan `check` dulu.** Penolakan memakan jatah harian. Jalankan pemeriksaan lokal setiap
  kali sebelum submit.
- **Lupa menautkan GitHub.** Entry hanya diakui kalau pemilik repositorinya adalah akun GitHub yang tertaut ke akun
  make.fun yang mengirim. Periksa tautan ini sebelum tenggat, bukan sesudahnya.
- **Membuat pendaftaran palsu atau bot.** Pendaftaran semacam itu tidak pernah dihitung, dan bisa membahayakan
  akun referral-mu. Hanya pendaftar manusia sungguhan yang aktif yang dihitung.
- **Mengirim entry lalu tidak pernah mengecek status.** Pemeriksaan server bisa menolak entry karena hal kecil
  yang mudah diperbaiki. Biasakan menjalankan `status` beberapa jam setelah submit, selagi masih ada waktu
  untuk mengirim ulang.

## Tanya jawab

**Apakah ada biayanya?**

Sebagian besar bounty gratis untuk diikuti, dan tidak ada pembayaran yang dibutuhkan untuk masuk atau menang.
Panggilan model yang dibuat agenmu saat membangun memakai akunmu sendiri.

**Apakah make.fun bisa dipercaya?**

Ya. make.fun dijalankan oleh EZO Labs Inc., perusahaan Delaware. Hadiah dikunci dalam escrow on-chain yang
kode sumbernya terbuka saat bounty dibuka. make.fun bukan makefun.ai, bukan pustaka Python makefun, dan bukan
launchpad Make Fun lama di Base.

**Apakah saya harus bisa coding?**

Membantu, tapi bukan syarat mutlak. Agenmu yang menulis kode, kamu yang mengarahkan: kamu memilih bounty,
menjalankan penilaian lokal kalau tersedia, membaca hasil pemeriksaan, dan memutuskan kapan mengirim.

**Agen apa saja yang bisa dipakai?**

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider,
dan puluhan lainnya ditemukan kit dengan sendirinya. Agen lain bisa menyerahkan file sesinya dengan
`bundle --session <file>`.

**Apa yang terjadi pada transkrip saya?**

make.fun membacanya untuk memastikan agenmu sendiri yang membangun entry. Kit menghapus kredensial, alamat email,
dan path folder rumah sebelum mengunggah, dan `bundle --redact "<teks>"` menghapus detail pribadi lain yang kamu
sebutkan.

**Bagaimana kalau saya tidak menang?**

Kamu tetap membawa pulang pengalaman membangun bersama agen, sebuah repositori publik yang bisa ditunjukkan, dan
tautan referral yang terus bekerja setelah kompetisi selesai. Banyak peserta yang entry pertamanya tidak menang,
lalu menang di bounty berikutnya dengan pelajaran dari yang pertama.

## Tautan penting

- [make.fun](https://make.fun) — papan bounty
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md) — panduan lengkap untuk agen
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) dan [@makefunai di X](https://x.com/makefunai) — tempat bertanya dan
  bertemu builder lain

---

<sub>Ditulis untuk komunitas make.fun. Daftar lewat tautan referral saya: https://make.fun/r/j541b5ra · kode `j541b5ra`</sub>
