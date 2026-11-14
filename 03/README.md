# RANGKUMAN MODUL 03: Sinkronisasi dan Koordinasi pada Sistem Terdistribusi

# Nama Lengkap : Diana Amelia

# NIM : 255410042

# Kelas : Informatika-1

# AI yang digunakan : chatgpt

# Prompt : #bertindaklah aku sebagai mahasiswa aktif dalam mata kuliah sistem terdistribusi dan terdesentralisasi, berikan aku rangkuman dari modul 03 mata kuliah ini dalam bentuk markdown, jabarkan secara detail dan ringkas mengenai isi dari modul tersebut agar mudah dipahami untuk tugas laporan rangkuman modul tersebut.

# Hasil Rangkuman Modul 03 :

## 1. Pendahuluan

Sistem terdistribusi merupakan sistem yang terdiri dari beberapa komputer atau _node_ yang saling terhubung melalui jaringan untuk menjalankan suatu layanan atau pekerjaan. Setiap node dapat menjalankan proses secara bersamaan dan memiliki keadaan (_state_) masing-masing.

Oleh karena itu, diperlukan mekanisme sinkronisasi agar seluruh proses, data, dan sumber daya dapat dikelola secara terkoordinasi.

**Sinkronisasi** adalah proses mengoordinasikan proses, data, dan sumber daya pada berbagai node untuk memastikan operasi berjalan secara konsisten dan andal.

Tanpa sinkronisasi yang tepat, sistem dapat mengalami konflik data, _race condition_, ketidaksesuaian informasi, dan kesalahan dalam penggunaan sumber daya.

Modul 03 membahas konsep sinkronisasi, tantangan sinkronisasi, sinkronisasi waktu fisik, sinkronisasi waktu logis, _mutual exclusion_, serta pemilihan koordinator.

## 2. Tujuan Pembelajaran

Setelah mempelajari modul ini, mahasiswa diharapkan mampu:

1. Memahami alasan sinkronisasi diperlukan dalam sistem terdistribusi.
2. Menjelaskan berbagai tantangan dalam sinkronisasi.
3. Memahami sinkronisasi waktu fisik beserta protokol dan algoritmanya.
4. Memahami sinkronisasi waktu logis dan algoritma yang berkaitan.
5. Memahami masalah _mutual exclusion_ dan berbagai algoritma penyelesaiannya.
6. Menjelaskan pentingnya pemilihan koordinator dalam sistem terdistribusi.
7. Memberikan contoh penerapan sinkronisasi dan koordinasi dalam industri.

## 3. Pengertian dan Pentingnya Sinkronisasi

### 3.1 Pengertian Sinkronisasi

Sinkronisasi merupakan mekanisme untuk mengatur dan mengoordinasikan proses, data, serta sumber daya yang tersebar pada beberapa node dalam sistem terdistribusi.

Tujuan utamanya adalah memastikan seluruh bagian sistem bekerja secara konsisten sehingga dapat mencegah konflik data dan menjaga keandalan sistem.

### 3.2 Contoh Race Condition pada E-Commerce

Contoh permasalahan sinkronisasi dapat ditemukan pada aplikasi E-Commerce.

Misalnya, sebuah toko online memiliki stok Produk X sebanyak 10 unit. Kemudian, dua pengguna melakukan pembelian secara bersamaan.

Urutan prosesnya:

1. Pengguna A membaca stok Produk X sebanyak 10.
2. Pengguna B juga membaca stok sebanyak 10.
3. Pengguna A membeli satu produk sehingga stok menjadi 9.
4. Pengguna B juga membeli satu produk berdasarkan data stok sebelumnya.
5. Sistem akhirnya mencatat stok tetap 9.

Padahal, karena terdapat dua transaksi pembelian, stok seharusnya menjadi 8.

Permasalahan tersebut terjadi karena kedua proses mengakses dan mengubah data secara bersamaan tanpa mekanisme sinkronisasi yang tepat.

Kondisi ini disebut _race condition_, yaitu keadaan ketika hasil suatu proses dipengaruhi oleh urutan atau waktu eksekusi proses yang berjalan bersamaan.

### 3.3 Mengapa Sinkronisasi Penting?

Sinkronisasi memiliki beberapa manfaat penting, yaitu:

- **Integritas data:** mencegah terjadinya konflik dan ketidaksesuaian data.
- **Sinkronisasi state:** memastikan keadaan aplikasi tetap konsisten di seluruh node.
- **Koordinasi tugas:** mengatur proses yang berjalan secara bersamaan.
- **Pengelolaan sumber daya:** mengatur penggunaan sumber daya bersama.
- **Recovery:** membantu proses pemulihan sistem dengan mempertahankan state.
- **Efisiensi:** mencegah operasi yang redundan atau berulang.
- **Load balancing:** membantu pembagian beban kerja.
- **Pencegahan deadlock:** mengurangi risiko proses saling menunggu tanpa akhir.
- **Skalabilitas:** mendukung perkembangan sistem dengan jumlah node yang semakin banyak.

Contoh penerapan sinkronisasi state adalah permainan _online multiplayer_ yang harus memperbarui posisi, kesehatan, dan inventaris pemain pada seluruh klien agar permainan tetap konsisten.

## 4. Tantangan Sinkronisasi

Dalam penerapannya, sinkronisasi sistem terdistribusi menghadapi beberapa tantangan, antara lain:

1. **Network Latency dan Partitioning**

   Keterlambatan jaringan dapat menyebabkan pesan antar-node tidak diterima secara bersamaan. Selain itu, _network partitioning_ dapat menyebabkan sebagian node kehilangan komunikasi dengan node lainnya.

2. **Skalabilitas**

   Semakin banyak node yang terlibat, semakin kompleks proses koordinasi dan sinkronisasi yang harus dilakukan.

3. **Fault-Tolerant System**

   Sistem harus mampu menghadapi kegagalan node atau komponen tanpa menyebabkan seluruh layanan berhenti beroperasi.

4. **Concurrency Control**

   Beberapa proses dapat berjalan bersamaan dan mengakses sumber daya yang sama sehingga diperlukan pengaturan akses.

5. **Data Consistency**

   Data yang tersimpan pada beberapa node harus tetap konsisten dan tidak saling bertentangan.

6. **Sinkronisasi Waktu**

   Setiap komputer dapat memiliki waktu yang berbeda sehingga diperlukan mekanisme penyelarasan waktu agar pencatatan dan pengurutan kejadian dapat dilakukan dengan benar.

## 5. Sinkronisasi Waktu Fisik

### 5.1 Pengertian Sinkronisasi Waktu Fisik

Sinkronisasi waktu fisik adalah proses menyelaraskan _real-time clock_ atau jam nyata pada komputer dalam sistem terdistribusi dengan standar waktu yang sama.

Tujuannya adalah memastikan seluruh node memiliki acuan waktu yang konsisten.

Sinkronisasi waktu fisik penting untuk:

- Menghubungkan catatan log dari berbagai komputer.
- Mengatur penjadwalan kejadian.
- Menjaga konsistensi sistem.
- Membantu proses koordinasi antar-node.

Proses sinkronisasi dapat dilakukan menggunakan protokol jaringan maupun sumber waktu berbasis perangkat keras seperti _atomic clock_ dan GPS.

### 5.2 Standar Waktu

Beberapa standar waktu yang dibahas dalam modul adalah:

- **GMT (Greenwich Mean Time):** standar waktu yang disebutkan sudah tidak digunakan.
- **UTC (Coordinated Universal Time):** standar waktu yang didefinisikan oleh ITU (_International Telecommunication Union_) dan digunakan sejak 1963. UTC berbasis pada TAI (_International Atomic Time_).
- **LTC (Coordinated Lunar Time):** standar waktu yang masih dalam proses pengembangan.

### 5.3 Sumber Sinkronisasi Waktu

Salah satu sumber waktu yang digunakan dalam sistem terdistribusi adalah _atomic clock_.

Modul menjelaskan bahwa sumber waktu dapat diperoleh melalui satelit GPS yang membawa jam atom.

Alur sinkronisasinya secara umum:

1. _Atomic clock_ menjadi sumber acuan waktu.
2. Satelit GPS menyediakan sinyal waktu berdasarkan jam atom.
3. GPS dongle menerima sinyal waktu dari satelit.
4. Server Linux menerima dan menggunakan informasi waktu tersebut.
5. Perangkat klien seperti Linux, Windows, Mac, dan telepon seluler melakukan sinkronisasi melalui server.

Dengan mekanisme tersebut, berbagai perangkat dapat menggunakan acuan waktu yang sama.

### 5.4 Network Time Protocol (NTP)

NTP (_Network Time Protocol_) merupakan protokol yang digunakan untuk melakukan sinkronisasi waktu melalui jaringan.

Dalam sistem terdistribusi, NTP membantu komputer dan server menyelaraskan waktu berdasarkan sumber waktu yang dijadikan acuan.

NTP memungkinkan perangkat klien memperoleh informasi waktu dari server sehingga pencatatan log dan pengaturan waktu sistem menjadi lebih konsisten.

### 5.5 Precision Time Protocol (PTP)

PTP (_Precision Time Protocol_) merupakan protokol sinkronisasi waktu yang distandardisasi oleh IEEE melalui standar IEEE 1588.

Beberapa standar PTP yang dibahas dalam modul:

- **IEEE 1588-2002:** standar awal PTP.
- **IEEE 1588-2008:** dikenal sebagai PTP Version 2 dan tidak kompatibel secara mundur dengan versi 2002.
- **IEEE 1588-2019:** memberikan peningkatan yang kompatibel secara mundur terhadap standar 2008.
- **IEEE 802.1AS:** adaptasi PTP yang disebut gPTP (_generalized Precision Time Protocol_) untuk kebutuhan AVB (_Audio Video Bridging_) dan TSN (_Time-Sensitive Networking_).

Salah satu persyaratan implementasi PTP yang dibahas dalam modul adalah NIC (_Network Interface Card_) harus mendukung fitur _hardware timestamping_.

### 5.6 Perbandingan NTP dan PTP

| Aspek        | NTP                                 | PTP                                                                                 |
| ------------ | ----------------------------------- | ----------------------------------------------------------------------------------- |
| Kepanjangan  | Network Time Protocol               | Precision Time Protocol                                                             |
| Fungsi       | Sinkronisasi waktu melalui jaringan | Sinkronisasi waktu berdasarkan standar IEEE 1588                                    |
| Standar      | NTP                                 | IEEE 1588                                                                           |
| Implementasi | Server dan perangkat klien          | Membutuhkan dukungan hardware timestamping pada NIC untuk implementasi yang dibahas |

## 6. Sinkronisasi Waktu Logis

### 6.1 Pengertian Sinkronisasi Waktu Logis

Sinkronisasi waktu logis merupakan metode untuk menentukan urutan sebab-akibat (_causal order_) dari kejadian dalam sistem terdistribusi.

Berbeda dengan waktu fisik, sinkronisasi waktu logis tidak bertujuan menyamakan jam komputer dengan waktu dunia nyata. Fokus utamanya adalah menentukan hubungan urutan antar-kejadian.

Prinsip dasarnya adalah:

Jika kejadian A terjadi sebelum B, dan B terjadi sebelum C, maka A juga terjadi sebelum C.

Konsep ini berkaitan dengan _Logical Clock_ yang diperkenalkan oleh Leslie Lamport.

### 6.2 Vector Clocks

_Vector Clock_ merupakan mekanisme pencatatan waktu logis menggunakan struktur vektor yang memiliki satu komponen untuk setiap proses.

Dalam contoh modul terdapat tiga proses:

- Proses A berada pada indeks 0.
- Proses B berada pada indeks 1.
- Proses C berada pada indeks 2.

Kondisi awal masing-masing proses adalah:

| Proses | Vector Clock |
| ------ | ------------ |
| A      | `[0, 0, 0]`  |
| B      | `[0, 0, 0]`  |
| C      | `[0, 0, 0]`  |

### 6.3 Aturan Vector Clock

Terdapat beberapa aturan dasar dalam penggunaan Vector Clock:

1. Setiap terjadi suatu kejadian (_event_), komponen milik proses tersebut ditambah 1.
2. Sebelum mengirim pesan, proses menambah nilai clock miliknya.
3. Pesan yang dikirim membawa informasi Vector Clock.
4. Ketika menerima pesan, proses melakukan perbandingan menggunakan nilai maksimum setiap komponen (_element-wise maximum_).
5. Setiap kejadian internal berikutnya tetap menambah komponen milik proses tersebut.

### 6.4 Contoh Proses Vector Clock

Misalkan terdapat tiga proses A, B, dan C dengan kondisi awal `[0, 0, 0]`.

Urutan prosesnya:

1. A melakukan kejadian internal sehingga menjadi `[1, 0, 0]`.
2. A akan mengirim pesan kepada B. Sebelum mengirim, clock A bertambah menjadi `[2, 0, 0]`.
3. B menerima pesan dari A dan memperbarui clock menggunakan _element-wise maximum_, sehingga menjadi `[2, 0, 0]`.
4. B melakukan pengiriman pesan kepada C sehingga clock menjadi `[2, 1, 0]`.
5. C menerima pesan dan memperbarui clock menjadi `[2, 1, 0]`.
6. C melakukan kejadian internal sehingga menjadi `[2, 1, 1]`.
7. C melakukan kejadian internal kembali sehingga menjadi `[2, 1, 2]`.

Hasil akhir Vector Clock:

| Proses | Nilai Akhir |
| ------ | ----------- |
| A      | `[2, 0, 0]` |
| B      | `[2, 1, 0]` |
| C      | `[2, 1, 2]` |

### 6.5 Aturan Perbandingan Vector Clock

Untuk mengetahui hubungan antar-kejadian, digunakan aturan berikut:

- Kejadian A terjadi sebelum B apabila seluruh komponen Vector Clock A lebih kecil atau sama dengan komponen B dan minimal satu komponen lebih kecil.
- Kejadian disebut _concurrent_ atau independen apabila hubungan tersebut tidak terpenuhi.

Contoh:

- `[0, 0, 0]` terjadi sebelum `[1, 0, 0]`.
- `[2, 0, 0]` terjadi sebelum `[2, 1, 0]`.
- `[2, 1, 2]` dan `[2, 0, 0]` merupakan kejadian independen.

Vector Clock sangat berguna untuk mengetahui hubungan sebab-akibat antarproses dalam sistem terdistribusi.

## 7. Mutual Exclusion

### 7.1 Pengertian Mutual Exclusion

_Mutual Exclusion_ merupakan prinsip dalam ilmu komputer yang memastikan hanya satu proses atau _thread_ yang dapat mengakses sumber daya bersama pada satu waktu.

Sumber daya bersama dapat berupa:

- Printer.
- File.
- Database.
- Memori bersama.

Bagian kode yang digunakan untuk mengakses sumber daya bersama disebut _Critical Section_ (CS).

Apabila lebih dari satu proses mengakses sumber daya tersebut secara bersamaan tanpa pengaturan, dapat terjadi inkonsistensi maupun kerusakan data.

### 7.2 Prinsip Mutual Exclusion

Terdapat empat prinsip utama:

1. **Mutual Exclusion**

   Hanya satu proses yang diperbolehkan menggunakan sumber daya bersama dalam satu waktu.

2. **Progress**

   Jika tidak ada proses yang sedang menggunakan _Critical Section_, proses lain yang membutuhkan akses harus dapat memperoleh kesempatan.

3. **Bounded Waiting**

   Tidak boleh ada proses yang menunggu selamanya untuk memperoleh akses ke sumber daya.

4. **Fairness**

   Permintaan akses harus dilayani berdasarkan urutan yang wajar.

### 7.3 Algoritma Mutual Exclusion

#### A. Centralized Algorithm

Centralized Algorithm merupakan algoritma yang menggunakan satu node sebagai koordinator untuk mengatur akses ke _Critical Section_.

Cara kerjanya:

1. Proses meminta izin kepada koordinator.
2. Koordinator memberikan akses apabila _Critical Section_ sedang kosong.
3. Setelah proses selesai, koordinator memberikan izin kepada proses berikutnya.

**Kelebihan:**

- Mudah dipahami dan diterapkan.
- Biaya komunikasi relatif rendah.

**Kekurangan:**

- Memiliki _single point of failure_.
- Koordinator dapat menjadi _bottleneck_ ketika banyak proses meminta akses.

#### B. Ricart–Agrawala Algorithm

Ricart–Agrawala merupakan algoritma _mutual exclusion_ yang bekerja secara terdistribusi penuh tanpa menggunakan koordinator pusat.

Cara kerjanya:

1. Setiap proses mengirimkan pesan permintaan dengan _timestamp_.
2. Proses harus memperoleh jawaban OK dari seluruh proses lainnya.
3. Setelah semua jawaban diterima, proses dapat memasuki _Critical Section_.

Jumlah pesan yang dibutuhkan untuk satu kali memasuki Critical Section adalah:

`2 × (N − 1)`

Keterangan:

- N adalah jumlah proses.
- N−1 pesan merupakan pesan permintaan.
- N−1 pesan merupakan pesan balasan.

**Kelebihan:**

- Tidak bergantung pada koordinator pusat.
- Bersifat terdistribusi penuh.

**Kekurangan:**

- Membutuhkan komunikasi pesan yang cukup banyak.
- Memiliki _overhead_ komunikasi yang tinggi.

#### C. Token-Based Algorithm

Token-Based Algorithm merupakan algoritma yang menggunakan sebuah token unik untuk mengatur akses ke _Critical Section_.

Cara kerjanya:

1. Token diedarkan di antara proses.
2. Proses harus memiliki token untuk memasuki _Critical Section_.
3. Setelah selesai menggunakan sumber daya, token diteruskan ke proses berikutnya.

**Kelebihan:**

- Hanya membutuhkan satu pesan untuk setiap entri ke _Critical Section_.

**Kekurangan:**

- Jika token hilang, diperlukan mekanisme pemulihan.
- Deteksi kehilangan token cukup sulit.

### 7.4 Perbandingan Algoritma Mutual Exclusion

| Algoritma       | Cara Kerja                                               | Kelebihan                  | Kekurangan                             |
| --------------- | -------------------------------------------------------- | -------------------------- | -------------------------------------- |
| Centralized     | Menggunakan koordinator pusat                            | Sederhana dan biaya rendah | Single point of failure dan bottleneck |
| Ricart–Agrawala | Permintaan dan balasan antarproses menggunakan timestamp | Terdistribusi penuh        | Overhead pesan tinggi                  |
| Token-Based     | Menggunakan token unik                                   | Satu pesan per entri CS    | Sulit mendeteksi token hilang          |

## 8. Pemilihan Koordinator

### 8.1 Pengertian Pemilihan Koordinator

Dalam sistem terdistribusi, beberapa node atau proses terkadang membutuhkan satu koordinator untuk mengatur aktivitas sistem.

Koordinator memiliki beberapa fungsi, yaitu:

- Mengelola sumber daya bersama.
- Menyinkronkan operasi.
- Membuat keputusan global.

Namun, koordinator dapat mengalami kegagalan atau terdapat node baru yang bergabung ke dalam sistem.

Oleh karena itu, diperlukan mekanisme pemilihan koordinator baru secara otomatis agar sistem tetap dapat berjalan.

### 8.2 Algoritma Pemilihan Koordinator

Beberapa algoritma yang dapat digunakan untuk pemilihan koordinator adalah:

1. **Bully Algorithm**

   Merupakan algoritma yang digunakan untuk memilih koordinator baru dalam sistem terdistribusi.

2. **Ring Algorithm**

   Merupakan algoritma pemilihan koordinator yang melibatkan proses dalam susunan berbentuk cincin.

3. **Raft atau Paxos**

   Merupakan pendekatan berbasis konsensus yang digunakan untuk mencapai kesepakatan antar-node dalam sistem terdistribusi.

### 8.3 Contoh Penerapan

Modul memberikan contoh penerapan algoritma koordinasi pada teknologi industri:

- **Apache ZooKeeper:** menggunakan Zab (_ZooKeeper Atomic Broadcast_) yang dalam modul disebut mirip dengan Paxos.
- **Kubernetes:** menggunakan Raft melalui etcd.

Hal tersebut menunjukkan bahwa pemilihan koordinator dan konsensus merupakan bagian penting dalam pengelolaan sistem terdistribusi modern.

## 9. Keterkaitan Antar Materi

Seluruh materi dalam Modul 03 memiliki keterkaitan satu sama lain.

1. Sinkronisasi diperlukan untuk mengoordinasikan proses, data, dan sumber daya pada berbagai node.
2. Sinkronisasi waktu fisik digunakan untuk menyelaraskan waktu nyata antar-komputer.
3. Sinkronisasi waktu logis digunakan untuk menentukan urutan sebab-akibat suatu kejadian.
4. Mutual Exclusion digunakan untuk mengatur akses terhadap sumber daya bersama agar tidak terjadi konflik.
5. Pemilihan koordinator digunakan untuk menentukan node yang bertanggung jawab dalam mengatur koordinasi sistem.

Dengan menerapkan mekanisme tersebut, sistem terdistribusi dapat bekerja secara lebih konsisten, terkoordinasi, dan andal.

## 10. Kesimpulan

Berdasarkan materi Modul 03, sinkronisasi dan koordinasi merupakan aspek penting dalam membangun sistem terdistribusi yang konsisten dan dapat diandalkan.

Sistem terdistribusi terdiri dari banyak node yang dapat menjalankan proses secara bersamaan. Hal tersebut dapat menimbulkan berbagai permasalahan, seperti _race condition_, perbedaan waktu, konflik akses sumber daya, dan kegagalan koordinator.

Untuk mengatasi permasalahan tersebut, digunakan beberapa mekanisme, seperti sinkronisasi waktu fisik menggunakan NTP dan PTP, sinkronisasi waktu logis menggunakan Vector Clock, serta algoritma _mutual exclusion_ untuk mengatur akses terhadap sumber daya bersama.

Selain itu, pemilihan koordinator melalui algoritma Bully, Ring, Raft, dan Paxos membantu sistem menentukan pemimpin yang bertanggung jawab dalam mengatur koordinasi.

Dengan memahami seluruh konsep tersebut, mahasiswa dapat mengetahui bagaimana sistem terdistribusi menjaga konsistensi data, mengatur proses yang berjalan bersamaan, serta mempertahankan keandalan layanan meskipun terdapat berbagai tantangan dalam jaringan.

## 11. Istilah Penting

| Istilah          | Pengertian                                                               |
| ---------------- | ------------------------------------------------------------------------ |
| Node             | Komputer atau unit pemrosesan dalam sistem terdistribusi                 |
| Sinkronisasi     | Proses mengoordinasikan proses, data, dan sumber daya                    |
| Race Condition   | Kondisi ketika hasil proses dipengaruhi urutan eksekusi proses bersamaan |
| Data Race        | Akses bersamaan terhadap data yang dapat menyebabkan konflik             |
| State            | Keadaan atau kondisi suatu proses atau aplikasi                          |
| Network Latency  | Keterlambatan komunikasi jaringan                                        |
| UTC              | Standar waktu universal                                                  |
| NTP              | Protokol sinkronisasi waktu melalui jaringan                             |
| PTP              | Protokol sinkronisasi waktu berdasarkan standar IEEE 1588                |
| Logical Clock    | Mekanisme untuk menentukan urutan kejadian secara logis                  |
| Vector Clock     | Jam logis berbentuk vektor untuk mencatat kejadian antarproses           |
| Mutual Exclusion | Mekanisme pembatasan akses sumber daya bersama                           |
| Critical Section | Bagian kode yang mengakses sumber daya bersama                           |
| Token            | Penanda unik untuk memperoleh hak akses ke Critical Section              |
| Coordinator      | Node yang bertugas mengatur koordinasi sistem                            |
| Consensus        | Mekanisme untuk mencapai kesepakatan antar-node                          |

## 12. Sumber Referensi

Dr. Bambang Purnomosidi D. P. **Modul 03: Sinkronisasi dan Koordinasi pada Sistem Terdistribusi.** Program Studi Informatika, Fakultas Teknologi Informasi, Universitas Teknologi Digital Indonesia (UTDI). Mata Kuliah FIF25002T.
