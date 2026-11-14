# RANGKUMAN MODUL 04: Konsistensi dan Replikasi pada Sistem Terdistribusi

# Nama Lengkap : Diana Amelia

# NIM : 255410042

# Kelas : Informatika-1

# AI yang digunakan : chatgpt

# Prompt : #bertindaklah aku sebagai mahasiswa aktif dalam mata kuliah sistem terdistribusi dan terdesentralisasi, berikan aku rangkuman dari modul 04 mata kuliah ini dalam bentuk markdown, jabarkan secara detail dan ringkas mengenai isi dari modul tersebut agar mudah dipahami untuk tugas laporan rangkuman modul tersebut. berikan aku format pengerjannya dalam bentuk markdown (README.md).

# Hasil Rangkuman Modul 04 :

## 1. Pendahuluan

Sistem terdistribusi merupakan sistem yang terdiri dari beberapa komputer atau server yang saling terhubung melalui jaringan untuk bekerja sama dalam menyediakan layanan dan mengelola data. Dalam penerapannya, data sering kali disimpan di beberapa server atau lokasi yang berbeda untuk meningkatkan ketersediaan, kecepatan akses, dan keandalan sistem.

Namun, penyimpanan data di banyak server menimbulkan tantangan tersendiri, terutama dalam menjaga agar seluruh salinan data tetap konsisten. Ketika terjadi perubahan data pada salah satu server, perubahan tersebut harus dapat diteruskan ke server lainnya agar tidak terjadi perbedaan informasi.

Oleh karena itu, terdapat dua konsep penting dalam sistem terdistribusi, yaitu **Consistency (Konsistensi)** dan **Replication (Replikasi)**.

- **Konsistensi** berfungsi memastikan bahwa data yang tersebar di berbagai node tetap sesuai dengan aturan yang telah ditentukan.
- **Replikasi** merupakan proses membuat dan memelihara salinan data pada beberapa node atau server.

Kedua konsep tersebut saling berkaitan dalam membangun sistem terdistribusi yang andal, tersedia, dan memiliki performa yang baik.

## 2. Konsistensi pada Sistem Terdistribusi

### 2.1 Pengertian Konsistensi

Konsistensi merupakan kondisi ketika semua node atau server dalam sistem terdistribusi memiliki data yang sama atau menampilkan data sesuai dengan aturan konsistensi tertentu pada waktu tertentu.

Dalam sistem terdistribusi, sebuah aplikasi dapat mempunyai beberapa salinan data yang tersebar di berbagai server. Ketika terjadi perubahan data pada satu server, sistem perlu memastikan bahwa perubahan tersebut juga diterapkan pada server lainnya.

Sebagai contoh, sebuah aplikasi memiliki tiga server yang menyimpan data pengguna. Ketika pengguna mengubah nama akun melalui server pertama, server kedua dan ketiga juga perlu mendapatkan perubahan tersebut agar informasi yang ditampilkan tetap sesuai.

### 2.2 Pentingnya Konsistensi

Konsistensi sangat penting karena pengguna dapat mengakses data dari server yang berbeda. Tanpa mekanisme konsistensi, pengguna berpotensi mendapatkan informasi yang berbeda meskipun mengakses data yang sama.

Contoh kasus transaksi perbankan:

1. Nasabah melakukan transfer uang dari rekening A ke rekening B.
2. Server pertama berhasil mengurangi saldo rekening A.
3. Server kedua belum menerima perubahan untuk menambahkan saldo rekening B.
4. Nasabah mencoba menggunakan saldo rekening B untuk transaksi lain.
5. Transaksi dapat ditolak karena saldo pada server kedua belum diperbarui.

Permasalahan tersebut menunjukkan bahwa ketidakkonsistenan data dapat menyebabkan kesalahan dalam proses bisnis dan merugikan pengguna.

Dengan demikian, konsistensi bertujuan memastikan bahwa pengguna mendapatkan informasi yang benar dan sesuai dengan kondisi data yang berlaku.

## 3. Teorema CAP (CAP Theorem)

### 3.1 Pengertian CAP Theorem

CAP Theorem merupakan konsep dalam sistem terdistribusi yang menjelaskan adanya kompromi antara tiga karakteristik utama, yaitu:

1. **Consistency (C):** Menjamin bahwa pembacaan data memberikan nilai yang konsisten sesuai dengan jaminan sistem.
2. **Availability (A):** Menjamin bahwa setiap permintaan pengguna mendapatkan respons dari sistem.
3. **Partition Tolerance (P):** Kemampuan sistem untuk tetap beroperasi meskipun terjadi gangguan atau terputusnya komunikasi jaringan antar-node.

Dalam kondisi terjadi network partition, sistem terdistribusi harus menentukan prioritas antara konsistensi dan ketersediaan.

### 3.2 Penerapan CAP Theorem

Contoh penerapan pada aplikasi e-commerce yang memiliki dua server:

- Server A melayani pengguna wilayah barat Indonesia.
- Server B melayani pengguna wilayah timur Indonesia.

Ketika koneksi jaringan antara kedua server terputus, terdapat dua pilihan pendekatan:

**A. AP (Availability + Partition Tolerance)**

Sistem tetap melayani transaksi dari kedua wilayah meskipun komunikasi antar-server terputus.

Kelebihan:

- Pengguna tetap dapat melakukan transaksi.
- Layanan tetap tersedia.
- Aktivitas pengguna tidak harus dihentikan.

Kekurangan:

- Data stok barang dapat berbeda sementara.
- Risiko terjadinya ketidaksesuaian jumlah stok.

**B. CP (Consistency + Partition Tolerance)**

Sistem lebih mengutamakan konsistensi data dengan membatasi atau menolak transaksi tertentu sampai komunikasi jaringan kembali normal.

Kelebihan:

- Mengurangi risiko perbedaan data.
- Informasi stok lebih terjaga konsistensinya.

Kekurangan:

- Sebagian transaksi tidak dapat dilakukan.
- Ketersediaan layanan berkurang selama gangguan jaringan.

### 3.3 Kesimpulan CAP Theorem

CAP Theorem menunjukkan bahwa ketika terjadi partisi jaringan, sistem harus memilih prioritas antara konsistensi dan ketersediaan. Partition Tolerance menjadi aspek penting karena gangguan jaringan merupakan kemungkinan yang harus dihadapi oleh sistem terdistribusi.

## 4. Model Konsistensi

Model konsistensi merupakan aturan atau jaminan yang menjelaskan bagaimana dan kapan perubahan data pada suatu node dapat dilihat oleh node atau klien lainnya.

Setiap model mempunyai tingkat jaminan yang berbeda dalam proses penyebaran perubahan data.

### 4.1 Strong Consistency

Strong Consistency merupakan model konsistensi yang menjamin bahwa setelah suatu data diperbarui, pembacaan berikutnya akan mendapatkan nilai terbaru sesuai dengan urutan operasi yang dijamin sistem.

Biasanya model ini memerlukan koordinasi antar-node menggunakan protokol seperti Two-Phase Commit atau Paxos.

**Contoh:** Sistem perbankan yang mengharuskan perubahan saldo rekening diketahui oleh server terkait sebelum transaksi dianggap selesai.

**Karakteristik:**

- Tingkat konsistensi tinggi.
- Membutuhkan koordinasi antar-server.
- Berpotensi menghasilkan latensi yang lebih tinggi.

### 4.2 Eventual Consistency

Eventual Consistency merupakan model konsistensi yang tidak mengharuskan semua node memiliki data yang sama secara langsung. Namun, seluruh replika akan mencapai kondisi konsisten apabila tidak ada pembaruan baru dalam jangka waktu tertentu dan proses sinkronisasi berhasil.

Model ini cocok digunakan pada sistem yang lebih mengutamakan ketersediaan dan kecepatan akses.

**Contoh:** Amazon DynamoDB dan Apache Cassandra.

**Karakteristik:**

- Perubahan data tidak harus langsung tersebar ke seluruh node.
- Memiliki kemungkinan perbedaan data sementara.
- Mengutamakan ketersediaan dan performa.

#### Konsep BASE

Eventual Consistency berkaitan dengan konsep BASE yang terdiri dari:

1. **Basically Available:** Sistem tetap berusaha menyediakan layanan baca dan tulis meskipun terjadi kegagalan sebagian atau pemisahan jaringan.
2. **Soft State:** Kondisi data pada replika dapat berubah seiring waktu karena proses sinkronisasi.
3. **Eventual Consistency:** Seluruh replika pada akhirnya akan memiliki data yang konsisten apabila tidak ada pembaruan baru setelah beberapa waktu.

### 4.3 Causal Consistency

Causal Consistency merupakan model konsistensi yang menjaga urutan operasi apabila suatu operasi memiliki hubungan sebab-akibat dengan operasi lainnya.

Operasi yang saling berhubungan harus terlihat dalam urutan yang benar, sedangkan operasi yang tidak memiliki hubungan sebab-akibat dapat terlihat dalam urutan berbeda.

**Contoh:** Pada media sosial, sebuah postingan harus muncul terlebih dahulu sebelum komentar atau reaksi terhadap postingan tersebut ditampilkan.

### 4.4 Read-Your-Writes Consistency

Read-Your-Writes Consistency merupakan model yang menjamin bahwa pengguna dapat melihat perubahan data yang telah ditulis atau diperbarui oleh dirinya sendiri ketika melakukan pembacaan berikutnya.

Model ini tidak menjamin bahwa pengguna lain langsung melihat perubahan yang sama.

**Contoh:** Ketika pengguna mengirim pesan melalui aplikasi messaging, pesan tersebut langsung muncul di layar pengirim meskipun penerima belum melihatnya.

### 4.5 Monotonic Read Consistency

Monotonic Read Consistency merupakan model yang menjamin bahwa pengguna tidak akan melihat versi data yang lebih lama dari versi yang sebelumnya telah dilihat.

Dengan demikian, informasi yang sudah diperbarui tidak akan terlihat kembali menjadi versi lama bagi pengguna yang sama.

**Contoh:** Ketika pengguna membuka timeline media sosial, kemudian melakukan refresh, sistem tidak menampilkan kembali versi timeline yang lebih lama dari versi yang sudah dilihat sebelumnya.

### 4.6 Sequential Consistency

Sequential Consistency merupakan model konsistensi yang memastikan seluruh operasi terlihat seolah-olah dijalankan dalam satu urutan tertentu yang sama oleh semua node.

Namun, urutan tersebut tidak harus mengikuti waktu nyata atau real-time.

**Contoh:** Pada aplikasi media sosial, seluruh pengguna melihat urutan postingan yang sama meskipun terdapat sedikit keterlambatan dalam proses penyebaran data.

### 4.7 Linearizability

Linearizability merupakan model konsistensi yang sangat kuat dan merupakan varian dari Strong Consistency.

Model ini menjamin bahwa operasi terlihat seolah-olah dilakukan secara atomik pada satu titik waktu tertentu. Urutan operasi juga harus menghormati urutan waktu nyata, sehingga setelah suatu penulisan selesai, pembacaan berikutnya oleh klien mana pun harus mencerminkan penulisan tersebut atau penulisan selanjutnya.

**Contoh:** Pengecekan keunikan username saat pendaftaran akun. Sistem harus memastikan bahwa dua pengguna tidak dapat mendaftarkan username yang sama secara bersamaan.

Contoh sistem yang disebutkan dalam modul:

- etcd.
- ZooKeeper.
- Google Spanner.

## 5. Trade-off antara Latensi dan Konsistensi

Dalam sistem terdistribusi, terdapat hubungan antara tingkat konsistensi dengan latensi atau waktu respons sistem.

Secara umum:

- Semakin tinggi tingkat konsistensi, semakin besar kemungkinan latensi meningkat.
- Semakin rendah tingkat konsistensi, semakin kecil latensi yang diperlukan.

### 5.1 Strong Consistency dan Latensi

Pada Strong Consistency, sistem harus memastikan perubahan data telah tersinkronisasi sesuai dengan jaminan konsistensi sebelum memberikan respons.

Hal tersebut membutuhkan komunikasi antar-server yang dapat meningkatkan waktu tunggu.

### 5.2 Eventual Consistency dan Latensi

Pada Eventual Consistency, sistem dapat memberikan respons tanpa harus menunggu seluruh replika selesai melakukan sinkronisasi.

Akibatnya, respons menjadi lebih cepat, tetapi terdapat kemungkinan pengguna membaca data yang belum diperbarui.

### 5.3 Contoh Kasus

Misalnya terdapat dua pusat data, yaitu Jakarta dan Yogyakarta. Pengguna melakukan perubahan data melalui pusat data Jakarta.

- **Strong Consistency:** Sistem menunggu sampai perubahan data tersinkronisasi dengan pusat data Yogyakarta sebelum memberikan respons. Data lebih konsisten, tetapi respons menjadi lebih lambat.
- **Eventual Consistency:** Sistem memberikan respons langsung dari Jakarta, sementara perubahan diteruskan ke Yogyakarta setelahnya. Respons lebih cepat, tetapi data dapat berbeda sementara.

Kesimpulannya, pemilihan model konsistensi perlu disesuaikan dengan kebutuhan aplikasi, terutama antara ketepatan data dan kecepatan layanan.

## 6. Replikasi Data (Data Replication)

### 6.1 Pengertian Replikasi Data

Replikasi data merupakan proses membuat dan memelihara salinan data yang sama pada beberapa node atau server dalam sistem terdistribusi.

Tujuan utamanya adalah meningkatkan ketersediaan, keandalan, dan kecepatan akses data.

Sebagai contoh, sebuah perusahaan memiliki database utama di Jakarta. Untuk meningkatkan ketersediaan layanan, perusahaan menambahkan salinan database di Yogyakarta dan Denpasar.

Dengan adanya replikasi, ketika salah satu server mengalami kegagalan, server lainnya masih dapat menyediakan data.

### 6.2 Tujuan Replikasi Data

Terdapat beberapa tujuan utama penerapan replikasi data:

1. **Availability (Ketersediaan):** Jika salah satu server mengalami kegagalan, server lain masih mempunyai salinan data sehingga layanan dapat tetap berjalan.
2. **Performance (Kinerja):** Pengguna dapat membaca data dari server yang lokasinya lebih dekat sehingga waktu akses menjadi lebih cepat.
3. **Reliability (Keandalan):** Meminimalkan risiko kehilangan data karena data memiliki salinan di beberapa lokasi.
4. **Scalability (Skalabilitas):** Beban permintaan pembacaan data dapat dibagi ke beberapa server sehingga tidak hanya bergantung pada satu server.

### 6.3 Jenis-Jenis Replikasi

**A. Master-Slave (Primary-Secondary)**

Merupakan jenis replikasi yang menggunakan satu server utama sebagai tempat penulisan data, sedangkan server lainnya berperan sebagai replika yang umumnya digunakan untuk membaca data.

Karakteristik:

- Penulisan data dilakukan melalui master.
- Slave menerima perubahan dari master.
- Struktur pengelolaan lebih sederhana.
- Master berpotensi menjadi bottleneck.

Contoh: PostgreSQL Streaming Replication.

**B. Multi-Master (Peer-to-Peer)**

Merupakan jenis replikasi yang memungkinkan beberapa node melakukan operasi baca dan tulis.

Karakteristik:

- Setiap node dapat melakukan perubahan data.
- Lebih fleksibel dalam distribusi operasi.
- Memiliki potensi konflik apabila beberapa node memperbarui data yang sama secara bersamaan.

Contoh yang disebutkan dalam modul:

- PostgreSQL Logical Replication.
- Apache Cassandra.
- MongoDB.
- Apache Ignite.

**C. Synchronous Replication**

Merupakan replikasi yang mengharuskan perubahan data dikirim dan dikonfirmasi oleh replika sesuai mekanisme sinkronisasi sebelum operasi dianggap selesai.

Karakteristik:

- Konsistensi lebih terjaga.
- Waktu respons dapat lebih lama.
- Memerlukan koordinasi antar-node.

Contoh: Google Spanner.

**D. Asynchronous Replication**

Merupakan replikasi yang memungkinkan transaksi pada server utama selesai terlebih dahulu sebelum perubahan dikirim ke replika.

Karakteristik:

- Proses penulisan lebih cepat.
- Tidak perlu menunggu semua replika.
- Memiliki risiko keterlambatan sinkronisasi atau kehilangan perubahan pada replika ketika terjadi kegagalan.

Contoh: MySQL Asynchronous Replication dan DynamoDB.

## 7. Strategi Sinkronisasi Replika

Strategi sinkronisasi merupakan metode yang digunakan untuk memastikan perubahan data dapat diteruskan dan diterapkan pada replika.

Dalam modul ini, strategi sinkronisasi dibagi berdasarkan beberapa aspek.

### 7.1 Berdasarkan Waktu Sinkronisasi

**A. Asynchronous**

Server sumber melakukan commit tanpa menunggu replika menerima atau menerapkan perubahan.

Kelebihan:

- Performa lebih cepat.
- Tidak perlu menunggu respons seluruh replika.

Kekurangan:

- Risiko kehilangan data pada replika lebih tinggi ketika terjadi kegagalan.
- Replika dapat tertinggal dari server utama.

**B. Semi-Synchronous**

Server sumber menunggu setidaknya satu replika menerima data sebelum proses dianggap berhasil sesuai mekanisme yang digunakan.

Kelebihan:

- Menjadi kompromi antara performa dan konsistensi.
- Lebih aman dibandingkan asynchronous dalam hal penerimaan perubahan oleh replika.

Kekurangan:

- Masih terdapat kemungkinan replika lain tertinggal.

Contoh: MySQL Semi-Synchronous Replication.

**C. Synchronous**

Server sumber menunggu seluruh replika yang disyaratkan menyelesaikan proses commit sebelum transaksi dianggap selesai.

Kelebihan:

- Jaminan konsistensi lebih tinggi.
- Meminimalkan perbedaan data antar-replika.

Kekurangan:

- Performa lebih rendah.
- Latensi meningkat karena membutuhkan koordinasi antar-server.

### 7.2 Berdasarkan Arah Replikasi

1. **Master-Slave:** Satu server utama melakukan operasi baca dan tulis, sedangkan server lainnya berperan sebagai replika.
2. **Master-Master:** Beberapa server mempunyai peran dan kemampuan yang setara dalam melakukan operasi baca dan tulis.
3. **Master-Master Asymmetric:** Beberapa server dapat melakukan baca dan tulis, tetapi memiliki peran, kapasitas, atau kemampuan yang berbeda.

### 7.3 Berdasarkan Cara Sinkronisasi

**A. Pull-Based**

Replika secara berkala memeriksa server sumber untuk mengetahui apakah terdapat perubahan data.

Jika ditemukan perubahan, replika mengambil dan memperbarui datanya. Jika tidak ada perubahan, replika tidak melakukan pembaruan.

**Kelebihan:**

- Replika dapat mengatur waktu pemeriksaan.
- Tidak membutuhkan pengiriman setiap perubahan secara langsung.

**Kekurangan:**

- Perubahan dapat terlambat diketahui karena pemeriksaan dilakukan secara periodik.

**B. Push-Based**

Server sumber secara aktif mengirimkan perubahan data kepada replika ketika terjadi pembaruan.

Metode ini dapat menggunakan:

- CDC (Change Data Capture).
- WebSockets.
- SSE (Server-Sent Events).

**Kelebihan:**

- Perubahan dapat segera diteruskan.
- Tidak perlu menunggu pemeriksaan periodik.

**Kekurangan:**

- Membutuhkan mekanisme pengiriman perubahan yang aktif dan dapat diandalkan.

**C. Hybrid**

Merupakan kombinasi antara Pull-Based dan Push-Based untuk mendapatkan manfaat dari kedua pendekatan tersebut.

### 7.4 Berdasarkan Penanganan Konflik

Ketika beberapa node melakukan pembaruan terhadap data yang sama secara bersamaan, sistem perlu memiliki mekanisme untuk menangani konflik.

Beberapa metode yang digunakan adalah:

**A. LWW (Last Write Wins)**

Merupakan metode yang menentukan hasil berdasarkan penulisan terakhir menggunakan timestamp.

Jika terdapat beberapa perubahan terhadap data yang sama, perubahan dengan timestamp terbaru akan dipertahankan, sedangkan perubahan lainnya diabaikan.

**B. Vector Clock**

Merupakan metode yang menggunakan vektor untuk membantu menentukan hubungan urutan dan ketergantungan antar-perubahan pada node.

Vector Clock dapat membantu mengidentifikasi apakah suatu perubahan terjadi sebelum, sesudah, atau secara konkuren dengan perubahan lainnya.

**C. CRDT (Conflict-free Replicated Data Types)**

CRDT merupakan pendekatan yang menggunakan struktur data khusus agar perubahan pada beberapa replika dapat digabungkan tanpa menimbulkan konflik yang menghambat tercapainya kesamaan data.

Contoh penerapan: Yjs, yang dapat digunakan untuk aplikasi kolaborasi seperti editor dokumen bersama.

**D. OT (Operational Transformation)**

OT merupakan metode penanganan konflik dengan mentransformasikan operasi berdasarkan perubahan yang terjadi pada data lokal.

Tujuannya agar beberapa perubahan yang dilakukan secara bersamaan tetap dapat digabungkan dengan hasil akhir yang konsisten.

## 8. Contoh Penerapan CRDT dan OT

### 8.1 Contoh CRDT

Misalnya Agnes Monica dan Bambang ingin menghitung jumlah akses pengunjung website secara terpisah.

Kondisi awal:

```json
{
  "Agnes Monica": 0,
  "Bambang": 0
}
```

Kemudian terjadi pembaruan:

**Agnes Monica mencatat 5 pengunjung:**

```json
{
  "Agnes Monica": 5,
  "Bambang": 0
}
```

**Bambang mencatat 3 pengunjung:**

```json
{
  "Agnes Monica": 0,
  "Bambang": 3
}
```

Ketika kedua perangkat melakukan sinkronisasi, CRDT menggunakan aturan nilai maksimum (Max) untuk setiap pengguna.

Perhitungan:

```text
Agnes Monica = max(5, 0) = 5
Bambang      = max(0, 3) = 3
```

Hasil akhir:

```json
{
  "Agnes Monica": 5,
  "Bambang": 3
}
```

Total pengunjung:

```text
5 + 3 = 8 pengunjung
```

Dari contoh tersebut, dapat dipahami bahwa CRDT memungkinkan perubahan lokal dari dua node digabungkan sehingga menghasilkan data akhir yang sama.

### 8.2 Contoh OT

Misalnya Agnes Monica dan Bambang mengedit dokumen yang berisi teks:

```text
abc
```

Keduanya melakukan perubahan secara bersamaan.

**Perubahan Agnes Monica:**

Menyisipkan karakter `x` pada indeks 0.

```text
abc → xabc
```

**Perubahan Bambang:**

Menghapus karakter `c` pada indeks 2.

```text
abc → ab
```

Jika operasi kedua pengguna diterapkan secara langsung tanpa transformasi, hasilnya dapat berbeda.

- Pada dokumen Agnes, penghapusan indeks 2 dapat menghapus karakter `b`, sehingga menjadi `xac`.
- Pada dokumen Bambang, penyisipan karakter `x` di indeks 0 menghasilkan `xab`.

Karena hasilnya berbeda, diperlukan Operational Transformation.

**Penyelesaian menggunakan OT:**

Operasi penghapusan dari Bambang disesuaikan dengan posisi terbaru dokumen Agnes. Indeks penghapusan berubah dari 2 menjadi 3.

Hasil akhir pada kedua dokumen:

```text
xab
```

Dengan demikian, OT memastikan bahwa perubahan yang dilakukan secara bersamaan dapat menghasilkan dokumen akhir yang sama.

## 9. Protokol Replikasi

Protokol replikasi merupakan mekanisme atau aturan yang digunakan untuk mengatur proses penyebaran data dan koordinasi antar-node dalam sistem terdistribusi.

Dalam modul ini terdapat lima protokol utama.

### 9.1 Primary-Based (Master-Slave)

Protokol ini menggunakan satu node utama sebagai pusat operasi penulisan data, sedangkan node lainnya berperan sebagai replika untuk membaca data.

Karakteristik:

- Penulisan data dilakukan melalui primary.
- Perubahan diteruskan ke replika.
- Pengelolaan data lebih terpusat.

### 9.2 Quorum-Based

Quorum-Based merupakan mekanisme replikasi yang menentukan keberhasilan operasi baca dan tulis berdasarkan jumlah minimum node yang memberikan konfirmasi.

Terdapat tiga parameter utama:

- **N:** Jumlah keseluruhan node.
- **W:** Jumlah minimum node yang harus mengonfirmasi operasi write.
- **R:** Jumlah minimum node yang harus memberikan respons operasi read.

Salah satu syarat untuk memastikan irisan antara operasi baca dan tulis adalah:

```text
W + R > N
```

**Contoh:**

Sebuah sistem database memiliki tiga node:

```text
N = 3
W = 2
R = 2
```

Pemeriksaan:

```text
W + R > N
2 + 2 > 3
4 > 3 (Terpenuhi)
```

Artinya, operasi tulis memerlukan minimal dua konfirmasi node, sedangkan operasi baca memerlukan respons minimal dua node.

**Skenario Write:**

1. Klien mengirimkan perintah `x = 100`.
2. Permintaan dikirim ke Node A, B, dan C.
3. Node A berhasil menyimpan data dan memberikan ACK.
4. Node B berhasil menyimpan data dan memberikan ACK.
5. Node C mengalami keterlambatan atau timeout.
6. Karena sudah mendapatkan dua ACK, operasi write dinyatakan berhasil.

**Skenario Read:**

1. Klien meminta data `x`.
2. Sistem meminta data dari minimal dua node.
3. Node A memberikan nilai terbaru, yaitu `x = 100`.
4. Node C mungkin masih memiliki nilai lama.
5. Karena jumlah node yang dibaca memenuhi quorum dan irisan antara quorum baca dan tulis terjamin, sistem dapat menemukan data terbaru sesuai mekanisme quorum yang digunakan.

### 9.3 State Machine Replication

State Machine Replication merupakan pendekatan yang membuat beberapa server atau replika menjalankan perintah yang sama dalam urutan yang sama.

Tujuannya adalah memastikan seluruh replika menghasilkan kondisi akhir yang sama meskipun masing-masing menyimpan data secara lokal.

**Contoh:**

Terdapat tiga replika, yaitu A, B, dan C. Kondisi awal seluruh replika adalah:

```text
x = 10
```

Kemudian klien mengirimkan perintah:

```text
SET x = 20
```

Tahapan proses:

1. Klien mengirim permintaan kepada leader, yaitu Replika A.
2. Replika A menentukan nomor urutan perintah dan menyimpannya ke dalam log.
3. Leader mengirimkan perintah kepada Replika B dan C.
4. Replika B dan C mengonfirmasi bahwa perintah telah masuk ke log.
5. Setelah mendapatkan konfirmasi sesuai mekanisme yang digunakan, perintah dianggap committed.
6. Seluruh replika menjalankan perintah yang sama.
7. Kondisi akhir seluruh replika menjadi `x = 20`.
8. Leader mengirimkan hasil kepada klien.

### 9.4 Gossip Protocol

Gossip Protocol merupakan mekanisme penyebaran informasi antar-node dengan cara setiap node secara berkala memilih beberapa node lain secara acak untuk membagikan informasi terbaru.

Protokol ini digunakan dalam distributed database seperti Apache Cassandra, antara lain untuk memeriksa keberadaan node dan menyebarkan informasi.

**Tahapan proses:**

1. Node A mendeteksi adanya perubahan data atau perubahan status node.
2. Node A memilih satu hingga tiga peer secara acak.
3. Node A mengirimkan informasi terbaru kepada peer tersebut.
4. Node penerima memperbarui status lokalnya.
5. Node penerima kemudian memilih node lain secara acak untuk menyebarkan informasi.
6. Proses berulang hingga informasi menyebar ke seluruh cluster.

Keunggulan Gossip Protocol adalah proses penyebaran informasi tidak harus bergantung pada satu server pusat.

### 9.5 Chain Replication

Chain Replication merupakan protokol replikasi yang mengatur node dalam bentuk rantai (chain), sehingga pembaruan data diteruskan melalui urutan node tertentu.

Secara umum, pada pendekatan ini operasi penulisan diproses melalui rantai replika, sedangkan pembacaan dilayani oleh node yang ditentukan oleh protokol.

Tujuannya adalah mengatur urutan pembaruan dan menjaga kesesuaian data antar-replika.

Catatan: Modul menampilkan Chain Replication sebagai salah satu protokol replikasi, tetapi penjelasan rinci mekanisme dan tahapan operasionalnya tidak dibahas pada halaman materi yang tersedia.

## 10. Studi Kasus Implementasi

Pada bagian akhir modul, terdapat dua studi kasus penerapan replikasi pada teknologi yang digunakan dalam sistem nyata.

### 10.1 PostgreSQL 18 Streaming Replication

PostgreSQL merupakan sistem manajemen basis data relasional yang mendukung replikasi data.

Streaming Replication merupakan mekanisme untuk meneruskan perubahan yang terjadi pada database utama kepada server standby melalui pengiriman informasi perubahan database.

Secara umum, pendekatan ini berkaitan dengan arsitektur Primary-Secondary, di mana server utama menjadi sumber perubahan dan server standby menerima perubahan tersebut.

Tujuan penerapannya:

- Menyediakan salinan database pada server lain.
- Mendukung ketersediaan layanan.
- Membantu pemulihan ketika server utama mengalami kegagalan.

### 10.2 Apache Ignite 3 Master-Master

Apache Ignite merupakan teknologi distributed database yang mendukung pengelolaan data terdistribusi.

Dalam materi ini, Apache Ignite 3 diperkenalkan sebagai studi kasus pendekatan Master-Master.

Pendekatan Master-Master memungkinkan beberapa node mempunyai kemampuan untuk melakukan operasi baca dan tulis sesuai konfigurasi sistem.

Tujuan pendekatan tersebut adalah mendukung distribusi operasi dan fleksibilitas pengelolaan data.

**Catatan:** Modul mengarahkan pembahasan kedua studi kasus ini lebih lanjut melalui dokumen lecture notes dan source code yang menyertai materi. Oleh karena itu, rincian konfigurasi dan implementasi teknis tidak dijabarkan lebih jauh dalam rangkuman ini.

## 11. Kesimpulan

Berdasarkan pembahasan Modul 04, dapat disimpulkan bahwa konsistensi dan replikasi merupakan dua konsep yang sangat penting dalam pembangunan sistem terdistribusi.

Konsistensi berperan dalam menjaga agar data yang tersebar di beberapa server tetap sesuai dengan aturan yang ditentukan. Sementara itu, replikasi berfungsi menyediakan salinan data pada beberapa node untuk meningkatkan ketersediaan, performa, keandalan, dan skalabilitas sistem.

Dalam penerapannya, sistem terdistribusi memiliki berbagai model konsistensi, seperti Strong Consistency, Eventual Consistency, Causal Consistency, Read-Your-Writes, Monotonic Read, Sequential Consistency, dan Linearizability. Setiap model memiliki karakteristik serta tingkat jaminan yang berbeda.

Selain itu, terdapat CAP Theorem yang menjelaskan kompromi antara Consistency, Availability, dan Partition Tolerance ketika terjadi gangguan jaringan. Sistem juga harus mempertimbangkan trade-off antara konsistensi dan latensi agar dapat memenuhi kebutuhan aplikasi.

Replikasi data dapat diterapkan menggunakan berbagai jenis dan strategi, seperti Master-Slave, Multi-Master, Synchronous, Asynchronous, Pull-Based, Push-Based, dan Hybrid. Apabila terjadi konflik akibat pembaruan secara bersamaan, sistem dapat menggunakan metode LWW, Vector Clock, CRDT, dan Operational Transformation.

Terakhir, berbagai protokol replikasi seperti Primary-Based, Quorum-Based, State Machine Replication, Gossip Protocol, dan Chain Replication digunakan untuk mengatur koordinasi dan penyebaran data antar-node.

Dengan memahami konsep-konsep tersebut, mahasiswa dapat mengetahui bagaimana sebuah sistem terdistribusi menjaga konsistensi data sekaligus mempertahankan ketersediaan dan performa layanan.

## 12. Poin-Poin Penting yang Perlu Dipahami

| Konsep                    | Inti Pembahasan                                                         |
| ------------------------- | ----------------------------------------------------------------------- |
| Consistency               | Menjaga kesesuaian data antar-node berdasarkan aturan konsistensi       |
| CAP Theorem               | Kompromi antara konsistensi, ketersediaan, dan toleransi partisi        |
| Strong Consistency        | Menjamin pembacaan mendapatkan data terbaru sesuai urutan operasi       |
| Eventual Consistency      | Data pada replika akan sama pada akhirnya jika tidak ada pembaruan baru |
| Linearizability           | Menjamin urutan operasi sesuai dengan waktu nyata                       |
| Data Replication          | Membuat dan memelihara salinan data di beberapa node                    |
| Master-Slave              | Satu server utama menangani penulisan                                   |
| Multi-Master              | Beberapa server dapat melakukan penulisan                               |
| Synchronous               | Menunggu konfirmasi replika sesuai mekanisme sinkronisasi               |
| Asynchronous              | Tidak menunggu replika sebelum commit pada sumber                       |
| CRDT                      | Menggabungkan perubahan data tanpa konflik yang menghambat konvergensi  |
| OT                        | Menyesuaikan operasi konkuren melalui transformasi                      |
| Quorum-Based              | Menentukan keberhasilan operasi berdasarkan jumlah konfirmasi node      |
| State Machine Replication | Replika menjalankan perintah yang sama dalam urutan yang sama           |
| Gossip Protocol           | Menyebarkan informasi antar-node secara bertahap                        |
| Chain Replication         | Meneruskan pembaruan melalui susunan node berbentuk rantai              |

## 13. Referensi

1. Bambang Purnomosidi D. P. (Tanpa tahun). _Modul 04: Konsistensi dan Replikasi pada Sistem Terdistribusi_. Fakultas Teknologi Informasi, Universitas Teknologi Digital Indonesia (UTDI).
2. Dokumentasi PostgreSQL – Streaming Replication.
3. Dokumentasi Apache Ignite – Distributed Database.
