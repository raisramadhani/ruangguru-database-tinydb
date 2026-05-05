# Pembahasan Quiz: Penyimpanan Data (TinyDB)

## 📚 Penjelasan Blok Utama TinyDB

Sebelum masuk ke pembahasan soal, mari kita ingat kembali fungsi dari masing-masing blok TinyDB berdasarkan gambar referensi:

- **`StoreValue` (Menyimpan Data):** Blok ini bertugas memasukkan data ke dalam _database_. Ia membutuhkan dua penempatan (socket):
  - `tag`: Berfungsi sebagai "label identitas" atau nama laci penyimpanan (contoh: `"Skor"` atau `"Nama"`).
  - `valueToStore`: Berisi data atau barang nyata yang ingin disimpan (contoh: angka `100` atau teks `"Budi"`).
- **`GetValue` (Mengambil Data):** Blok ini bertugas menarik data yang sudah disimpan agar bisa ditampilkan. Ia membutuhkan dua penempatan:
  - `tag`: Nama label data yang ingin dicari/dipanggil.
  - `valueIfTagNotThere`: Nilai cadangan (_default_) yang akan dikeluarkan oleh sistem jika _tag_ yang dicari ternyata kosong atau belum pernah dibuat (sangat berguna untuk pengguna yang baru pertama kali menginstal aplikasi).
- **`ClearTag`:** Berfungsi untuk menghapus data secara spesifik hanya pada `tag` tertentu saja (misal: hanya mereset data `"Skor"` tanpa menghapus `"Nama"`).
- **`ClearAll`:** Berfungsi ibarat tombol _format_, ia akan menghapus **seluruh** isi _database_ TinyDB di aplikasi tersebut tanpa pandang bulu.
- **`GetTags` & `GetEntries`:** Blok tingkat lanjut yang digunakan untuk mengambil daftar seluruh nama _tag_ yang pernah dibuat, atau mengambil seluruh isi (pasangan _tag_ dan _value_) sekaligus dari dalam _database_.

---

## 📝 Pembahasan Soal

**1. Jawaban: B. Menyimpan data secara permanen langsung di dalam memori HP pengguna.**

- Fungsi utama TinyDB adalah sebagai database lokal (offline).
- Data yang disimpan tidak akan hilang meskipun HP dimatikan atau aplikasi ditutup.

**2. Jawaban: RAM**

- Variabel (Variable) bersifat sementara seperti RAM pada komputer.
- Saat aplikasi ditutup, memori akan dikosongkan dan data di dalamnya lenyap.

**3. Jawaban: Storage**

- Di MIT App Inventor, komponen yang berhubungan dengan penyimpanan file dan database (termasuk TinyDB) dikelompokkan dalam laci (drawer) **Storage**.

**4. Jawaban: B. Komponennya bekerja di balik layar dan tidak memiliki wujud tampilan di layar aplikasi pengguna.**

- TinyDB adalah komponen mesin (Non-Visible).
- Ia tidak memiliki bentuk visual (seperti tombol atau teks) di layar HP, melainkan bekerja secara sembunyi-sembunyi mengatur data.

**5. Jawaban: C. Sebagai isi data atau barang nyata yang ingin kita simpan ke dalam database.**

- `valueToStore` adalah barang/isi yang akan dimasukkan ke dalam loker.
- Pada kasus ini, isinya adalah teks apapun yang diketik oleh pengguna di dalam TextBox (`TB_Nama.Text`).

**6. Jawaban: B. call TinyDB1.GetValue**

- _Store_ = Menyimpan.
- _Get_ = Mengambil / Mendapatkan.
- Jadi, untuk menarik data kita memanggil fungsi `GetValue`.

**7. Jawaban: B. Sebagai data cadangan (default) yang ditampilkan jika aplikasi belum pernah menyimpan data...**

- `valueIfTagNotThere` adalah jaring pengaman.
- Jika program disuruh mencari Tag "SkorTertinggi" tapi ternyata tidak ada (misalnya karena baru pertama main), maka ia akan mengeluarkan nilai cadangan ini agar program tidak _error_.

**8. Jawaban: A, C, dan D**

- Opsi B salah, karena satu komponen TinyDB bisa menyimpan ratusan hingga ribuan data asalkan **Tag** yang digunakan berbeda-beda.

**9. Jawaban: B. when Screen1.Initialize do**

- Event `Initialize` artinya "Saat layar pertama kali dimuat/dibuka".
- Ini adalah waktu paling tepat untuk menarik data (seperti skor atau nama) dari database dan menampilkannya sebelum pengguna mulai bermain.

**10. Jawaban: Data awal (100) akan terhapus dan tergantikan (tertimpa/overwrite) oleh data baru (500).**

- Jika kita menyimpan data baru menggunakan Tag yang **sama persis** dengan yang sudah ada, TinyDB akan membuang data lama dan menggantinya dengan data yang paling baru.

**11. Jawaban: B. call TinyDB1.GetValue**

- Sesuai namanya, _Get_ berarti mengambil. Blok ini dikhususkan untuk menarik `Value` berdasarkan `Tag` yang diminta.

**12. Jawaban: C. Karena tag adalah label identitas data...**

- Ibarat laci lemari, kita butuh label (Tag) agar tahu di laci mana kita menyimpan Koin, di laci mana kita menyimpan Skor, dsb. Jika tidak ada tag, komputer akan kebingungan mencari datanya.

**13. Jawaban: C. Tidak akan muncul apa-apa (mendapat nilai teks kosong).**

- Jika pengguna baru pertama kali main, data belum ada di HP-nya.
- Maka blok ini akan mengeluarkan nilai cadangan (`valueIfTagNotThere`). Karena nilai cadangannya adalah blok teks kosong (`""`), maka tidak akan muncul huruf/angka apapun di layar.

**14. Jawaban: B. valueToStore**

- Koin adalah nilai atau data yang ingin kita simpan. Oleh karena itu, variabel koin harus dipasangkan ke socket `valueToStore` (nilai yang akan disimpan).

**15. Jawaban: A. call TinyDB1.ClearTag**

- `ClearTag` berfungsi untuk menghapus satu loker/data secara spesifik berdasarkan nama Tag-nya saja (misal: hanya menghapus "Skor").
- Sedangkan `ClearAll` akan menghapus seluruh data yang ada di dalam game tanpa pandang bulu.

**16. Jawaban: A. Blok Teks Kosong (Magenta)**

- Tag `"data_elektronik"` mengisyaratkan bahwa data yang disimpan berupa teks (nama-nama barang).
- Untuk data bertipe teks (_String_), nilai cadangan (`valueIfTagNotThere`) yang paling tepat adalah blok teks kosong berwarna magenta (`""`).

**17. Jawaban: B. Blok Angka 0 (Biru)**

- Tag `"nilai_siswa"` mengisyaratkan bahwa data yang disimpan berupa **Angka** (Matematika).
- Untuk data bertipe angka yang nantinya mungkin akan dijumlahkan atau dikurangi, nilai cadangan (`valueIfTagNotThere`) yang paling tepat dan aman adalah blok Math/angka `0` berwarna biru. Jika menggunakan teks `"0"`, aplikasi berisiko mengalami _error_ saat dilakukan perhitungan matematika.
