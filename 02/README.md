# RANGKUMAN MODUL 02: PROSES DAN KOMUNIKASI ANTAR PROSES PADA SISTEM TERDISTRIBUSI

# Nama Lengkap : Diana Amelia

# NIM : 255410042

# Kelas : Informatika-1

# AI yang digunakan : chatgpt

# Prompt : #bertindaklah aku sebagai mahasiswa aktif dalam mata kuliah sistem terdistribusi dan terdesentralisasi, berikan aku rangkuman dari modul 02 mata kuliah ini dalam bentuk markdown, jabarkan secara detail dan ringkas mengenai isi dari modul tersebut agar mudah dipahami untuk tugas laporan rangkuman modul tersebut. berikan aku format pengerjannya dalam bentuk markdown (README.md).

# Hasil Rangkuman Modul 02 :

## 1. Pendahuluan

Pada sistem terdistribusi, terdapat sekumpulan komputer atau node yang saling terhubung dan bekerja sama untuk menjalankan suatu sistem sebagai satu kesatuan logis. Setiap komputer dapat menjalankan prosesnya masing-masing, tetapi tetap membutuhkan komunikasi dengan komputer lain agar dapat menyelesaikan tugas secara terkoordinasi.

Modul 02 membahas mengenai proses dan komunikasi antarproses (_Inter-Process Communication_ atau IPC) dalam lingkungan sistem terdistribusi. Materi ini menjelaskan bagaimana proses dibuat, dikelola, berkomunikasi, melakukan sinkronisasi, serta berkoordinasi dengan proses lain yang berada pada komputer berbeda.

Komunikasi antarproses menjadi bagian penting karena setiap node dalam sistem terdistribusi tidak memiliki akses langsung terhadap memori bersama seperti pada sistem komputer tunggal. Oleh karena itu, diperlukan mekanisme komunikasi tertentu agar pertukaran informasi dapat berjalan dengan baik.

## 2. Pengertian Proses

Proses merupakan sebuah program yang sedang dieksekusi oleh sistem operasi. Proses tidak hanya terdiri dari instruksi program, tetapi juga memiliki informasi dan sumber daya yang dibutuhkan selama proses tersebut berjalan.

Dalam sistem operasi, proses menjadi unit dasar untuk menjalankan pekerjaan komputer. Setiap proses dapat memiliki identitas, status, ruang memori, serta sumber daya yang digunakan.

Pada sistem terdistribusi, proses dapat berjalan pada komputer atau node yang berbeda. Masing-masing proses bekerja secara independen, tetapi dapat saling berkomunikasi untuk mencapai tujuan tertentu.

Dengan demikian, proses merupakan komponen utama yang memungkinkan sistem terdistribusi menjalankan berbagai tugas secara bersamaan.

## 3. Manajemen Proses

Manajemen proses merupakan kegiatan untuk mengatur proses agar dapat berjalan secara efektif dan sesuai dengan kebutuhan sistem. Dalam modul ini terdapat tiga bagian utama manajemen proses.

### 3.1 Process Creation

_Process Creation_ merupakan proses pembuatan atau pembentukan proses baru. Proses ini terjadi ketika sistem membutuhkan pekerjaan atau tugas baru untuk dijalankan.

Contohnya, ketika pengguna membuka aplikasi, sistem operasi akan membuat proses baru untuk menjalankan aplikasi tersebut.

Dalam sistem terdistribusi, proses baru juga dapat dibuat pada node tertentu untuk menangani permintaan atau pekerjaan dari node lainnya.

### 3.2 Process Migration

_Process Migration_ merupakan pemindahan proses dari satu komputer atau node ke komputer atau node lainnya.

Pemindahan ini dapat dilakukan untuk menyeimbangkan beban kerja, meningkatkan penggunaan sumber daya, atau menyesuaikan kebutuhan sistem.

Contohnya, ketika sebuah server mengalami beban kerja yang tinggi, sebagian pekerjaan dapat dialihkan ke server lain agar kinerja sistem tetap optimal.

### 3.3 Process Monitoring

_Process Monitoring_ merupakan kegiatan memantau proses yang sedang berjalan.

Tujuannya adalah mengetahui kondisi proses, penggunaan sumber daya, serta mendeteksi apabila terjadi gangguan atau kesalahan.

Monitoring membantu administrator atau sistem dalam memastikan seluruh proses berjalan sebagaimana mestinya.

## 4. Sistem Terdistribusi dan Komunikasi

Sistem terdistribusi merupakan sekumpulan komputer atau node independen yang bekerja bersama dan dikoordinasikan sebagai satu kesatuan logis.

Setiap node menjalankan proses masing-masing. Agar seluruh node dapat bekerja sama, diperlukan mekanisme komunikasi antarproses.

Komunikasi ini memungkinkan satu node mengirimkan informasi atau permintaan kepada node lainnya sehingga pekerjaan dapat diselesaikan secara terkoordinasi.

### Contoh Penerapan

1. **Multiplayer Games**

   Dalam permainan multiplayer, setiap pemain menggunakan perangkat yang berbeda. Sistem harus mengirimkan informasi mengenai posisi pemain, tindakan, dan kondisi permainan agar seluruh pemain mendapatkan informasi yang konsisten.

2. **Gojek dan Grab**

   Aplikasi layanan transportasi melibatkan beberapa layanan, seperti antarmuka pengguna, layanan pengemudi, pelacakan lokasi, dan perhitungan biaya. Semua layanan tersebut harus saling berkomunikasi untuk memproses pesanan.

3. **WhatsApp**

   Fitur chat dan video call membutuhkan komunikasi antarperangkat melalui infrastruktur terdistribusi agar pesan dan informasi dapat dikirimkan kepada pengguna lain.

## 5. Model Komunikasi Pesan

Komunikasi pesan merupakan mekanisme pertukaran informasi antarproses. Dalam modul ini terdapat beberapa model komunikasi yang digunakan dalam sistem terdistribusi.

### 5.1 Komunikasi Langsung (Direct Communication)

Komunikasi langsung merupakan mekanisme komunikasi ketika proses saling mengirimkan pesan secara langsung melalui saluran komunikasi.

Salah satu teknologi yang digunakan adalah **Socket**.

Socket memungkinkan dua proses berkomunikasi melalui jaringan dengan menggunakan alamat dan port tertentu.

Contohnya adalah komunikasi antara aplikasi client dan server ketika pengguna mengakses suatu layanan.

### 5.2 Komunikasi Tidak Langsung (Indirect Communication)

Komunikasi tidak langsung merupakan mekanisme komunikasi ketika proses tidak berkomunikasi secara langsung, tetapi menggunakan perantara seperti _mailbox_ atau _message queue_.

Pesan dikirimkan ke tempat penyimpanan sementara, kemudian proses penerima mengambil pesan tersebut ketika dibutuhkan.

Contohnya adalah penggunaan message queue untuk menyimpan permintaan pekerjaan sebelum diproses oleh layanan tertentu.

### 5.3 Publish/Subscribe (Pub/Sub)

Publish/Subscribe merupakan model komunikasi ketika suatu proses mengirimkan informasi kepada suatu topik, kemudian proses lain yang berlangganan pada topik tersebut akan menerima informasi.

Dalam model ini terdapat dua komponen utama:

- **Publisher:** Proses yang menghasilkan dan mengirimkan pesan.
- **Subscriber:** Proses yang menerima pesan berdasarkan topik yang diikuti.

Keunggulan model Pub/Sub adalah publisher tidak harus mengetahui secara langsung siapa saja penerima pesannya.

Model ini cocok digunakan pada sistem yang memiliki banyak layanan dan membutuhkan distribusi informasi secara fleksibel.

## 6. Proses pada Sistem Terdistribusi

Proses pada sistem terdistribusi dapat berada pada node atau komputer yang berbeda. Kondisi tersebut menyebabkan proses tidak dapat menggunakan _shared memory_ secara langsung seperti pada sistem komputer tunggal.

Setiap node memiliki ruang memori masing-masing sehingga diperlukan mekanisme komunikasi melalui jaringan.

Oleh karena itu, IPC (_Inter-Process Communication_) menjadi bagian penting dalam sistem terdistribusi.

IPC memungkinkan proses yang berjalan pada komputer berbeda untuk saling bertukar data, mengirimkan pesan, dan bekerja sama dalam menyelesaikan tugas.

## 7. Inter-Process Communication (IPC)

IPC adalah mekanisme yang digunakan untuk memungkinkan dua proses atau lebih saling berkomunikasi dan bertukar informasi.

Dalam modul ini dijelaskan empat jenis IPC utama.

### 7.1 Shared Memory

Shared Memory merupakan mekanisme komunikasi ketika beberapa proses menggunakan area memori yang sama untuk bertukar data.

Proses dapat membaca dan menulis informasi melalui area memori tersebut.

Namun, mekanisme ini tidak cocok untuk sistem terdistribusi yang prosesnya berada pada node berbeda karena setiap node tidak memiliki akses langsung terhadap memori fisik node lainnya.

### 7.2 Message Passing

Message Passing merupakan mekanisme komunikasi dengan cara mengirim dan menerima pesan antarproses.

Setiap proses dapat mengirimkan data melalui jaringan tanpa harus mengakses memori proses lain.

Salah satu standar yang digunakan adalah MPI (_Message Passing Interface_).

MPI menyediakan mekanisme komunikasi untuk aplikasi yang membutuhkan pertukaran pesan antarproses, khususnya dalam komputasi paralel.

Implementasi MPI dapat digunakan melalui bahasa pemrograman Python dengan pustaka `mpi4py`.

### 7.3 Remote Procedure Call (RPC)

RPC merupakan mekanisme yang memungkinkan suatu proses memanggil fungsi atau prosedur yang berada pada komputer lain seolah-olah fungsi tersebut dijalankan secara lokal.

Dengan RPC, pengembang tidak perlu mengatur seluruh proses komunikasi jaringan secara manual karena mekanisme pemanggilan dan pertukaran data ditangani oleh sistem RPC.

Salah satu contoh implementasinya adalah **gRPC**.

gRPC memungkinkan komunikasi antarservice dengan mekanisme pemanggilan prosedur jarak jauh sehingga cocok digunakan pada arsitektur microservices.

### 7.4 Middleware

Middleware merupakan perangkat lunak perantara yang membantu aplikasi atau proses berkomunikasi dan bertukar informasi.

Middleware menyediakan fasilitas komunikasi sehingga aplikasi tidak harus menangani seluruh detail komunikasi jaringan secara langsung.

Salah satu bentuk middleware yang dibahas dalam modul adalah MOM (_Message-Oriented Middleware_).

## 8. Message-Oriented Middleware (MOM)

Message-Oriented Middleware merupakan infrastruktur yang memfasilitasi komunikasi dan pertukaran data antar aplikasi melalui pesan (_message_).

Pesan menjadi unit informasi mandiri yang dikirimkan melalui saluran komunikasi tertentu.

Salah satu karakteristik utama MOM adalah komunikasi dilakukan secara asinkron. Artinya, pengirim pesan tidak harus menunggu penerima selesai memproses pesan tersebut.

### 8.1 Standar dan Protokol MOM

Beberapa standar dan protokol MOM yang dibahas dalam modul adalah:

1. **XATMI (X/Open Transaction Management API)**

   Spesifikasi dari kelompok X/Open yang berkaitan dengan komunikasi dan pemrosesan transaksi terdistribusi.

2. **AMQP (Advanced Message Queuing Protocol)**

   Protokol komunikasi berbasis pesan yang umumnya digunakan dalam aplikasi enterprise.

3. **HLA (High Level Architecture)**

   Standar IEEE 1516 yang digunakan untuk mendukung interoperabilitas dalam lingkungan simulasi terdistribusi.

4. **MQTT (Message Queuing Telemetry Transport)**

   Protokol komunikasi ringan yang umumnya digunakan pada perangkat dengan keterbatasan sumber daya, seperti perangkat IoT.

5. **DDS (Data Distribution Service)**

   Standar dari OMG yang digunakan untuk distribusi data dalam sistem terdistribusi.

6. **XMPP (Extensible Messaging and Presence Protocol)**

   Protokol komunikasi berbasis pesan yang mendukung pertukaran pesan dan informasi kehadiran pengguna.

## 9. Studi Kasus: Microservices

Microservices merupakan pendekatan pengembangan perangkat lunak dengan membagi aplikasi menjadi beberapa layanan kecil yang memiliki tanggung jawab tertentu.

Setiap layanan dapat berjalan secara independen dan berkomunikasi dengan layanan lainnya melalui mekanisme komunikasi jaringan.

Contohnya adalah aplikasi e-commerce yang memiliki beberapa layanan berikut:

- **User Service:** Mengelola data pengguna.
- **Product Service:** Mengelola informasi produk.
- **Order Service:** Mengelola pesanan.
- **Payment Service:** Mengelola pembayaran.
- **Notification Service:** Mengirimkan notifikasi kepada pengguna.

Ketika pengguna melakukan pembelian, Order Service dapat berkomunikasi dengan Product Service untuk memeriksa ketersediaan barang dan Payment Service untuk memproses pembayaran.

Komunikasi antarservice dapat menggunakan RPC, REST, message queue, atau mekanisme komunikasi lainnya.

Microservices menunjukkan bagaimana IPC menjadi bagian penting dalam membangun aplikasi yang terdistribusi.

## 10. Komunikasi Sinkron dan Asinkron

Dalam sistem terdistribusi, komunikasi antarproses dapat dibedakan menjadi komunikasi sinkron dan asinkron.

### 10.1 Komunikasi Sinkron (Synchronous Communication)

Komunikasi sinkron merupakan mekanisme ketika proses pengirim harus menunggu respons dari proses penerima sebelum melanjutkan pekerjaan tertentu.

Contohnya adalah pemanggilan API secara langsung. Ketika aplikasi meminta data kepada server, aplikasi menunggu hingga server memberikan respons.

Karakteristik:

- Pengirim menunggu respons penerima.
- Alur komunikasi lebih terstruktur.
- Cocok untuk operasi yang membutuhkan hasil secara langsung.
- Dapat menyebabkan waktu tunggu apabila layanan penerima lambat.

### 10.2 Komunikasi Asinkron (Asynchronous Communication)

Komunikasi asinkron merupakan mekanisme ketika pengirim tidak harus menunggu proses penerima selesai mengolah pesan.

Pesan dapat dikirim melalui message queue atau middleware, kemudian diproses oleh penerima ketika tersedia.

Karakteristik:

- Pengirim tidak harus menunggu respons langsung.
- Proses dapat berjalan secara independen.
- Cocok untuk pekerjaan yang membutuhkan pemrosesan di latar belakang.
- Membutuhkan mekanisme pengelolaan pesan agar pesan tidak hilang atau diproses secara tidak semestinya.

**Perbedaan utama:** Komunikasi sinkron mengharuskan pengirim menunggu respons, sedangkan komunikasi asinkron memungkinkan pengirim melanjutkan pekerjaan tanpa menunggu penerima menyelesaikan pemrosesan pesan.

## 11. Permasalahan dalam Komunikasi Antarproses

Dalam sistem terdistribusi, komunikasi antarproses memiliki beberapa tantangan yang harus diperhatikan.

### 11.1 Reliability (Keandalan)

Reliability merupakan kemampuan sistem untuk memastikan pesan yang dikirim dapat diterima secara lengkap dan sesuai dengan urutan yang diharapkan.

Permasalahan dapat terjadi akibat kehilangan paket jaringan, gangguan koneksi, atau kerusakan sistem.

Solusi yang dapat digunakan:

- **Acknowledgement:** Penerima memberikan konfirmasi bahwa pesan telah diterima.
- **Retransmission:** Mengirimkan ulang pesan apabila terjadi kegagalan pengiriman.
- **TCP:** Menggunakan protokol transport yang menyediakan pengiriman data secara andal dan berurutan.

### 11.2 Ordering (Urutan Pesan)

Ordering merupakan mekanisme untuk memastikan pesan diproses berdasarkan urutan yang logis dan dapat diprediksi.

Hal ini penting karena perubahan urutan pesan dapat menyebabkan kesalahan dalam pemrosesan data.

Beberapa mekanisme yang disebutkan dalam modul adalah:

- Pipes dengan mekanisme FIFO (_First In First Out_).
- Message queues.
- Shared memory.
- Sockets dan message passing.
- RPC.

### 11.3 Security (Keamanan)

Keamanan diperlukan untuk melindungi informasi yang dikirimkan antarproses agar tidak dapat diakses atau dimanipulasi oleh pihak yang tidak berwenang.

Beberapa pendekatan yang digunakan adalah:

- Enkripsi untuk melindungi data.
- Autentikasi untuk memastikan identitas pihak yang berkomunikasi.

### 11.4 Performance (Kinerja)

Kinerja komunikasi antarproses dipengaruhi oleh beberapa faktor, terutama:

- **Latency:** Waktu yang dibutuhkan untuk mengirimkan data dari pengirim ke penerima.
- **Bandwidth:** Kapasitas jaringan dalam mengirimkan data pada periode waktu tertentu.

Sistem terdistribusi harus memperhatikan kedua faktor tersebut agar komunikasi berjalan secara efisien.

## 12. Protokol Komunikasi

Protokol komunikasi merupakan aturan yang digunakan untuk mengatur pertukaran data antarperangkat atau antarproses dalam jaringan.

Dalam modul terdapat beberapa protokol yang dibahas.

### 12.1 TCP (Transmission Control Protocol)

TCP merupakan protokol transport yang menyediakan komunikasi data secara andal dan berurutan.

TCP memastikan data yang dikirim dapat diterima dengan mekanisme pemeriksaan dan pengiriman ulang apabila diperlukan.

### 12.2 UDP (User Datagram Protocol)

UDP merupakan protokol transport yang mengirimkan data tanpa mekanisme jaminan pengiriman seperti TCP.

UDP memiliki karakteristik yang lebih sederhana dan tidak memerlukan proses pembentukan koneksi seperti TCP.

### 12.3 HTTP (Hypertext Transfer Protocol)

HTTP merupakan protokol yang digunakan untuk pertukaran informasi antara client dan server.

HTTP banyak digunakan dalam komunikasi aplikasi berbasis web dan layanan API.

### 12.4 Protokol atau Teknologi Komunikasi Tingkat Aplikasi

Modul juga membahas beberapa teknologi komunikasi yang berjalan di atas HTTP, yaitu:

- **gRPC:** Teknologi komunikasi antarservice menggunakan mekanisme Remote Procedure Call.
- **GraphQL:** Teknologi untuk mengambil data melalui API dengan menentukan struktur data yang dibutuhkan oleh client.
- **REST:** Gaya arsitektur untuk membangun layanan web melalui sumber daya dan metode komunikasi HTTP.

Ketiga teknologi tersebut dapat digunakan untuk mendukung komunikasi antarservice dalam sistem terdistribusi.

## 13. Konsep Sinkronisasi

Sinkronisasi merupakan proses untuk menyelaraskan aktivitas atau waktu antarproses dalam sistem terdistribusi.

Setiap node pada sistem terdistribusi memiliki jam lokal masing-masing. Karena adanya perbedaan perangkat keras, latensi jaringan, dan faktor lainnya, waktu pada setiap node dapat mengalami perbedaan.

Sinkronisasi clock diperlukan untuk:

1. Menjaga urutan kejadian dalam sistem.
2. Mendukung konsistensi data.
3. Memastikan koordinasi antarproses.
4. Mengurangi kesalahan akibat perbedaan waktu pada setiap node.

### 13.1 Metode Sinkronisasi Clock

Beberapa metode sinkronisasi yang dibahas dalam modul meliputi:

- **Atomic Clock:** Digunakan sebagai sumber waktu yang sangat akurat.
- **GPS (Global Positioning System):** Dapat digunakan sebagai sumber referensi waktu.
- **TAI (International Atomic Time):** Skala waktu atom internasional.
- **UTC (Coordinated Universal Time):** Standar waktu universal.

Selain itu, terdapat protokol yang digunakan untuk menyelaraskan waktu antarperangkat:

- **NTP (Network Time Protocol):** Protokol untuk sinkronisasi waktu melalui jaringan.
- **PTP (Precision Time Protocol):** Protokol sinkronisasi waktu dengan tingkat presisi lebih tinggi dibandingkan NTP.

## 14. Logical Clock

Logical Clock merupakan mekanisme pencatatan urutan kejadian dalam sistem terdistribusi tanpa harus bergantung sepenuhnya pada waktu sebenarnya (_real clock_).

Salah satu algoritma yang dibahas adalah **Lamport Logical Clock** yang diperkenalkan oleh Leslie Lamport.

Algoritma ini digunakan untuk mengetahui hubungan urutan kejadian antarproses dalam sistem terdistribusi.

### 14.1 Aturan Lamport Logical Clock

Terdapat tiga aturan utama:

1. Setiap terjadi suatu kejadian, nilai logical clock akan bertambah satu.
2. Ketika mengirim pesan, proses menyertakan nilai logical clock ke dalam pesan.
3. Ketika menerima pesan, proses membandingkan nilai logical clock lokal dengan nilai dari pesan, mengambil nilai terbesar, kemudian menambahkan satu.

### 14.2 Contoh Penerapan Lamport Logical Clock

Dalam modul terdapat contoh sistem penjualan yang memiliki tiga service:

- Sales Service.
- Product Service.
- Invoice Service.

Ketiga service awalnya memiliki nilai logical clock sebesar 0.

Prosesnya adalah sebagai berikut:

**Tahap 1: Sales Service**

Sales Service menerima dan mencatat transaksi penjualan.

- Logical clock awal: 0.
- Terjadi pencatatan transaksi sehingga clock bertambah menjadi 1.
- Sales Service mengirimkan pesan ke Product Service dengan timestamp 1.

**Tahap 2: Product Service**

Product Service menerima pesan dari Sales Service dengan timestamp 1.

- Logical clock lokal: 0.
- Timestamp pesan: 1.
- Diambil nilai terbesar, yaitu 1.
- Nilai tersebut ditambah 1 sehingga logical clock menjadi 2.
- Product Service mengirimkan pesan kepada Invoice Service dengan timestamp 2.

**Tahap 3: Invoice Service**

Invoice Service menerima pesan dari Product Service dengan timestamp 2.

- Logical clock lokal: 0.
- Timestamp pesan: 2.
- Diambil nilai terbesar, yaitu 2.
- Nilai tersebut ditambah 1 sehingga logical clock menjadi 3.
- Invoice Service kemudian menghasilkan faktur.

Hasil urutan logical clock:

| Service         | Logical Clock |
| --------------- | ------------: |
| Sales Service   |             1 |
| Product Service |             2 |
| Invoice Service |             3 |

Dengan mekanisme tersebut, sistem dapat mengetahui urutan kejadian berdasarkan hubungan komunikasi antarservice meskipun waktu aktual pada masing-masing komputer mengalami perbedaan.

### 14.3 Pengembangan Logical Clock

Lamport Logical Clock menggunakan pendekatan scalar clock. Dalam perkembangannya, terdapat beberapa pendekatan lain yang disebutkan dalam modul:

1. **Vector Clocks:** Dikembangkan oleh Colin Fidge dan Friedemann Mattern (1988).
2. **Plausible Clocks:** Dikembangkan oleh Torres-Rojas dan Ahamad (1999).
3. **Chain Clocks:** Dikembangkan oleh Agarwal dan Garg (2005).
4. **Interval Tree Clocks:** Dikembangkan oleh Almeida dan rekan-rekan (2008).
5. **Blum Clocks:** Dikembangkan oleh Lum Ramabaja (2019).

## 15. Koordinasi Proses

Koordinasi proses merupakan mekanisme yang memungkinkan beberapa proses independen pada komputer berbeda bekerja sama untuk mencapai tujuan bersama.

Koordinasi diperlukan untuk mengatur komunikasi, sinkronisasi, dan penggunaan sumber daya agar tidak terjadi konflik.

Beberapa permasalahan yang ingin dihindari melalui koordinasi adalah:

- **Deadlock:** Kondisi ketika proses saling menunggu sumber daya sehingga tidak dapat melanjutkan pekerjaan.
- **Race Condition:** Kondisi ketika hasil eksekusi dipengaruhi oleh urutan atau waktu akses beberapa proses terhadap sumber daya yang sama.

Beberapa teknologi yang disebutkan dalam modul untuk mendukung koordinasi proses adalah:

1. Apache ZooKeeper.
2. etcd.
3. Consul.
4. ClickHouse Keeper.
5. Oxia.
6. KRaft.

Teknologi tersebut digunakan untuk mendukung pengelolaan koordinasi dalam lingkungan sistem terdistribusi.

## 16. Tantangan dan Solusi pada Sistem Terdistribusi

Sistem terdistribusi memiliki berbagai tantangan yang dapat memengaruhi kestabilan dan konsistensi sistem.

Berikut beberapa permasalahan beserta solusi yang dijelaskan dalam modul.

| Tantangan          | Penjelasan                                                         | Solusi                                     |
| ------------------ | ------------------------------------------------------------------ | ------------------------------------------ |
| Message Loss       | Pesan hilang ketika dikirimkan melalui jaringan.                   | Retransmission dan acknowledgement.        |
| Deadlock           | Proses saling menunggu sehingga tidak dapat melanjutkan pekerjaan. | Timeout dan algoritma deteksi deadlock.    |
| Data Inconsistency | Data antar-node tidak memiliki kondisi yang konsisten.             | Consensus Protocol seperti Raft dan Paxos. |
| Security           | Risiko akses tidak sah atau penyadapan komunikasi.                 | SSL/TLS dan OAuth2.                        |

Solusi tersebut membantu meningkatkan keandalan, keamanan, dan konsistensi komunikasi dalam sistem terdistribusi.

## 17. Isu Terkini dalam Sistem Terdistribusi

Perkembangan teknologi menyebabkan sistem terdistribusi menghadapi berbagai tantangan dan kebutuhan baru.

Dalam modul terdapat tiga isu terkini yang dibahas.

### 17.1 Edge and Fog Computing

Edge Computing merupakan pendekatan pemrosesan data yang dilakukan lebih dekat dengan sumber data atau perangkat pengguna.

Fog Computing memperluas konsep tersebut dengan menyediakan lapisan komputasi dan layanan di antara perangkat edge dan cloud.

Keduanya bertujuan untuk mengurangi keterlambatan komunikasi serta meningkatkan efisiensi pemrosesan data.

### 17.2 Observability and Tracing

Observability merupakan kemampuan untuk memahami kondisi internal suatu sistem melalui informasi yang dihasilkan selama sistem berjalan.

Tracing digunakan untuk melacak perjalanan suatu permintaan ketika melewati beberapa service dalam sistem terdistribusi.

Salah satu komponen pendukungnya adalah telemetry, yaitu pengumpulan informasi mengenai aktivitas, kinerja, dan kondisi sistem.

Dengan observability dan tracing, pengembang dapat menemukan sumber masalah ketika terjadi gangguan komunikasi atau kegagalan layanan.

### 17.3 Container Orchestration

Container Orchestration merupakan mekanisme untuk mengelola container agar aplikasi dapat dijalankan dan dikelola secara terstruktur.

Pengelolaan ini meliputi penjadwalan, pengaturan, dan pemantauan container dalam lingkungan sistem terdistribusi.

Contoh teknologi yang disebutkan dalam modul:

- Kubernetes.
- Docker Swarm.

Teknologi tersebut membantu mengelola aplikasi yang terdiri dari banyak layanan atau container agar dapat berjalan secara terkoordinasi.

## 18. Kesimpulan

Berdasarkan materi Modul 02, dapat disimpulkan bahwa proses dan komunikasi antarproses merupakan komponen penting dalam sistem terdistribusi.

Setiap node dalam sistem terdistribusi menjalankan proses secara independen, tetapi tetap membutuhkan komunikasi agar dapat bekerja sebagai satu kesatuan sistem. Oleh karena itu, diperlukan mekanisme IPC seperti Message Passing, RPC, dan Middleware.

Selain komunikasi, sistem terdistribusi juga membutuhkan sinkronisasi dan koordinasi proses untuk menjaga urutan kejadian, konsistensi data, serta menghindari konflik antarproses.

Penggunaan teknologi seperti gRPC, MPI, MQTT, NTP, Lamport Logical Clock, ZooKeeper, dan Kubernetes menunjukkan bahwa komunikasi dan koordinasi memiliki peranan penting dalam pengembangan sistem modern.

Dengan memahami materi ini, mahasiswa dapat mengetahui bagaimana proses bekerja, bagaimana proses saling berkomunikasi, serta bagaimana berbagai permasalahan dalam sistem terdistribusi dapat ditangani menggunakan mekanisme dan teknologi yang sesuai.

## 19. Poin Penting yang Dapat Dipelajari

Berikut beberapa poin utama yang menjadi inti pembelajaran Modul 02:

1. Proses merupakan program yang sedang dieksekusi oleh sistem operasi.
2. Manajemen proses meliputi process creation, process migration, dan process monitoring.
3. Sistem terdistribusi membutuhkan komunikasi antarproses karena setiap node berjalan secara independen.
4. IPC terdiri dari Shared Memory, Message Passing, RPC, dan Middleware.
5. Message Passing memungkinkan pertukaran data antarproses melalui pesan.
6. RPC memungkinkan pemanggilan prosedur pada komputer lain.
7. MOM mendukung komunikasi asinkron menggunakan mekanisme pertukaran pesan.
8. Komunikasi antarproses dapat dilakukan secara sinkron maupun asinkron.
9. Reliability, ordering, security, dan performance merupakan aspek penting dalam komunikasi.
10. Sinkronisasi clock membantu menjaga urutan kejadian dan konsistensi sistem.
11. Lamport Logical Clock digunakan untuk menentukan urutan kejadian berdasarkan hubungan antarproses.
12. Koordinasi proses diperlukan untuk menghindari deadlock dan race condition.
13. Edge Computing, observability, tracing, dan container orchestration menjadi bagian dari perkembangan sistem terdistribusi.

## 20. Pertanyaan Diskusi dalam Modul

Modul juga memberikan beberapa pertanyaan diskusi untuk memperdalam pemahaman mengenai teknologi komunikasi dalam sistem terdistribusi.

1. Apakah GraphQL merupakan contoh RPC?
2. Apakah REST merupakan contoh RPC?
3. Apakah telemetry merupakan solusi yang etis?

Pertanyaan tersebut dapat digunakan sebagai bahan diskusi lebih lanjut mengenai konsep komunikasi, arsitektur sistem, serta aspek etika dalam pengelolaan sistem terdistribusi.

---

**Referensi:**

Bambang Purnomosidi D. P. (2026). _Modul 02: Proses dan Komunikasi Antar Proses pada Sistem Terdistribusi_. Program Studi Informatika, Fakultas Teknologi Informasi, Universitas Teknologi Digital Indonesia (UTDI).
