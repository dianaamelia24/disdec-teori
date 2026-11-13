# Rangkuman Modul 01 : PENGENALAN SISTEM TERDISTRIBUSI DAN TERDESENTRALISASI

# Nama Lengkap : Diana Amelia

# NIM : 255410042

# Kelas : Informatika-1

# AI yang digunakan : chatgpt

# Prompt : #bertindaklah aku sebagai mahasiswa aktif dalam mata kuliah sistem terdistribusi dan terdesentralisasi, berikan aku rangkuman dari modul 01 mata kuliah ini dalam bentuk markdown, jabarkan secara detail mengenai isi dari modul tersebut agar mudah dipahami untuk tugas laporan rangkuman modul tersebut. kemudian berikan aku langkah2 untuk mengerjakan dalam bentuk markdown (README.md).

# Hasil Rangkuman Modul 01 :

## 1. Pendahuluan

Perkembangan teknologi informasi yang semakin pesat menyebabkan pertumbuhan jumlah data, pengguna, dan kebutuhan layanan digital meningkat secara signifikan. Berbagai platform digital seperti Google, Netflix, YouTube, Instagram, dan layanan berbasis blockchain membutuhkan infrastruktur teknologi yang mampu menangani banyak permintaan pengguna secara bersamaan.

Sistem komputer konvensional yang hanya mengandalkan satu komputer atau satu server memiliki keterbatasan dalam menangani beban kerja yang besar. Apabila server mengalami gangguan, layanan dapat terhenti dan pengguna tidak dapat mengakses sistem tersebut.

Untuk mengatasi permasalahan tersebut, dikembangkan konsep sistem terdistribusi dan sistem terdesentralisasi. Kedua konsep ini menjadi dasar dalam membangun infrastruktur teknologi modern yang mampu bekerja dengan lebih fleksibel, memiliki skalabilitas tinggi, dan tetap beroperasi ketika sebagian komponennya mengalami kegagalan.

Sistem terdistribusi berfokus pada pembagian beban kerja ke beberapa komputer yang saling terhubung, sedangkan sistem terdesentralisasi berfokus pada pembagian kendali atau kontrol agar tidak hanya bergantung pada satu pihak atau satu titik pengendali.

Keduanya memiliki peran penting dalam mendukung perkembangan teknologi modern, meskipun mempunyai prinsip dan tujuan yang berbeda.

## 2. Arti Penting Sistem Terdistribusi dan Terdesentralisasi

Sistem terdistribusi dan terdesentralisasi menjadi semakin penting karena adanya beberapa kebutuhan utama dalam dunia teknologi informasi.

2.1 Pertumbuhan Data dan Pengguna yang Sangat Besar

Saat ini, jumlah pengguna internet dan aktivitas digital terus meningkat. Setiap aktivitas pengguna dapat menghasilkan data dalam jumlah besar, seperti unggahan foto, video, pesan, transaksi, dan aktivitas lainnya.

Sistem harus mampu mengelola data tersebut secara efisien. Dengan menggunakan sistem terdistribusi, pemrosesan dan penyimpanan data dapat dibagi ke beberapa komputer sehingga tidak seluruh beban ditanggung oleh satu perangkat saja.

2.2 Kebutuhan Skalabilitas

Skalabilitas merupakan kemampuan suatu sistem, jaringan, proses, atau organisasi untuk berkembang dan menangani peningkatan beban kerja, jumlah pengguna, maupun permintaan tanpa mengorbankan kinerja atau kualitas layanan.

Contohnya, ketika sebuah platform media sosial mengalami peningkatan jumlah pengguna, sistem harus mampu menambah kapasitas pemrosesan dan penyimpanan agar tetap dapat memberikan layanan dengan baik.

Dengan sistem terdistribusi, kapasitas dapat dikembangkan melalui penambahan komputer atau server yang saling bekerja sama.

2.3 Fault Tolerance

Fault tolerance merupakan kemampuan suatu sistem untuk tetap beroperasi secara normal meskipun terjadi kegagalan atau kerusakan pada sebagian komponennya, baik perangkat keras (hardware) maupun perangkat lunak (software).

Sebagai contoh, ketika salah satu server mengalami kerusakan, server lain dapat membantu menangani permintaan pengguna. Dengan demikian, layanan tidak harus berhenti secara keseluruhan.

Kemampuan ini sangat penting bagi layanan digital yang harus tersedia sepanjang waktu.

2.4 Kinerja dan Ketersediaan Layanan 24/7

Layanan modern dituntut memiliki performa tinggi dan dapat diakses kapan saja. Pengguna mengharapkan layanan tetap tersedia tanpa mengalami gangguan yang berarti.

Sistem terdistribusi dan terdesentralisasi membantu memenuhi kebutuhan tersebut melalui pembagian beban kerja, penyebaran komponen, dan pengurangan ketergantungan terhadap satu titik pengendali.

Tanpa konsep sistem terdistribusi dan terdesentralisasi, layanan berskala besar seperti Google, Netflix, dan teknologi blockchain akan sulit diwujudkan.

## 3. Pengertian Sistem Terdistribusi

Menurut Andrew S. Tanenbaum dan Maarten van Steen (2007), sistem terdistribusi adalah:

"A collection of independent computers that appears to its users as a single coherent system."

Artinya, sistem terdistribusi merupakan sekumpulan komputer independen yang saling bekerja sama dan terlihat oleh pengguna sebagai satu kesatuan sistem yang utuh.

Dalam sistem ini, setiap komputer dapat memiliki tugas dan sumber daya masing-masing, tetapi seluruh komputer saling berkomunikasi melalui jaringan untuk menjalankan suatu layanan.

3.1 Komponen Independen

Sistem terdistribusi terdiri dari beberapa komputer atau node yang dapat beroperasi secara independen. Setiap komputer mempunyai kemampuan untuk menjalankan proses tertentu tanpa harus selalu bergantung pada komputer lainnya.

Walaupun bekerja secara mandiri, seluruh komponen tetap berkoordinasi untuk mencapai tujuan sistem secara keseluruhan.

3.2 Komunikasi Melalui Jaringan

Setiap komputer dalam sistem terdistribusi saling berkomunikasi menggunakan jaringan komputer.

Komunikasi ini diperlukan untuk bertukar informasi, mengirimkan permintaan, mengirimkan hasil pemrosesan, serta melakukan koordinasi antarbagian sistem.

3.3 Transparansi Sistem

Transparansi merupakan salah satu konsep penting dalam sistem terdistribusi. Artinya, kompleksitas yang terjadi di dalam sistem sebisa mungkin tidak perlu diketahui oleh pengguna.

Beberapa bentuk transparansi yang dijelaskan dalam modul adalah:

Transparansi Lokasi: Pengguna tidak perlu mengetahui lokasi fisik server atau sumber daya yang sedang diakses.

Transparansi Akses: Pengguna dapat mengakses sumber daya tanpa harus mengetahui perbedaan mekanisme akses pada setiap komputer.

Transparansi Replikasi: Pengguna tidak perlu mengetahui bahwa suatu data memiliki beberapa salinan pada komputer yang berbeda.

Transparansi Kegagalan: Sistem berusaha menyembunyikan atau menangani kegagalan komponen agar pengguna tetap dapat menggunakan layanan.

Dengan adanya transparansi, sistem terdistribusi dapat memberikan pengalaman penggunaan yang lebih sederhana meskipun memiliki infrastruktur yang kompleks.

## 4. Arsitektur Sistem Dasar

Dalam sistem terdistribusi terdapat beberapa bentuk arsitektur dasar yang digunakan untuk mengatur hubungan dan komunikasi antar komputer.

4.1 Client-Server

Arsitektur client-server merupakan model sistem yang membagi peran komputer menjadi dua bagian utama, yaitu client dan server.

Client: Perangkat atau aplikasi yang mengirimkan permintaan layanan.

Server: Komputer yang menerima permintaan, melakukan pemrosesan, dan memberikan respons kepada client.

Contohnya adalah ketika seseorang membuka sebuah website. Browser bertindak sebagai client yang mengirimkan permintaan kepada server. Selanjutnya, server memproses permintaan tersebut dan mengirimkan halaman website kepada browser.

Kelebihan arsitektur client-server adalah pengelolaan layanan dapat dilakukan secara terpusat sehingga administrasi dan pengaturan sistem menjadi lebih mudah.

Namun, apabila server utama mengalami gangguan, layanan yang bergantung kepadanya dapat terganggu. Hal ini dapat menyebabkan munculnya single point of failure.

4.2 Peer-to-Peer (P2P)

Peer-to-peer merupakan arsitektur jaringan yang memungkinkan setiap komputer atau node berperan sebagai pihak yang menyediakan sekaligus menggunakan sumber daya.

Dalam model ini, tidak selalu terdapat server pusat yang mengatur seluruh komunikasi. Setiap node dapat berkomunikasi dan bertukar data secara langsung dengan node lainnya.

Contohnya adalah BitTorrent, yaitu teknologi berbagi file yang memungkinkan pengguna mengunduh dan membagikan bagian-bagian file dari pengguna lain.

Kelebihan arsitektur P2P adalah sumber daya dapat dibagikan antaranggota jaringan sehingga beban tidak hanya bergantung pada satu server.

4.3 Hybrid

Arsitektur hybrid merupakan kombinasi dari model client-server dan peer-to-peer.

Model ini menggabungkan kelebihan kedua arsitektur tersebut. Beberapa fungsi dapat dikendalikan melalui server pusat, sedangkan proses pertukaran data tertentu dapat dilakukan secara langsung antar-node.

Dengan pendekatan ini, sistem dapat memperoleh fleksibilitas dalam pengelolaan jaringan sekaligus memanfaatkan kemampuan komunikasi langsung antarperangkat.

## 5. Karakteristik Sistem Terdistribusi

Sistem terdistribusi mempunyai beberapa karakteristik utama yang membedakannya dari sistem komputer biasa.

5.1 Transparansi Lokasi

Transparansi lokasi berarti pengguna tidak perlu mengetahui di mana suatu sumber daya disimpan atau diproses.

Sebagai contoh, ketika pengguna membuka file yang tersimpan pada layanan penyimpanan cloud, pengguna cukup memilih file tersebut tanpa perlu mengetahui lokasi server yang menyimpannya.

5.2 Skalabilitas

Skalabilitas memungkinkan sistem dikembangkan untuk menangani peningkatan jumlah pengguna, data, dan permintaan layanan.

Penambahan komputer atau server dapat dilakukan untuk meningkatkan kapasitas sistem sesuai kebutuhan.

5.3 Fault Tolerance

Fault tolerance memungkinkan sistem tetap berjalan meskipun sebagian komponennya mengalami kegagalan.

Hal ini dapat dilakukan melalui pembagian tugas dan penyediaan komponen yang dapat membantu ketika komponen lain mengalami gangguan.

5.4 Kinerja Tinggi

Pembagian beban kerja ke beberapa komputer memungkinkan proses dilakukan secara bersamaan.

Dengan demikian, pekerjaan dapat diselesaikan secara lebih efisien dibandingkan apabila seluruh pekerjaan hanya dilakukan oleh satu komputer.

5.5 Heterogenitas

Heterogenitas berarti sistem terdistribusi dapat terdiri dari perangkat keras, sistem operasi, bahasa pemrograman, dan teknologi jaringan yang berbeda-beda.

Meskipun memiliki perbedaan, komponen tersebut tetap dapat bekerja sama melalui mekanisme komunikasi dan protokol yang sesuai.

## 6. Pengertian Sistem Terdesentralisasi

Sistem terdesentralisasi merupakan sistem yang menerapkan pembagian kontrol atau kendali kepada beberapa pihak atau node, sehingga tidak seluruh keputusan dan pengelolaan sistem bergantung pada satu titik pusat.

Untuk memahami konsep ini, perlu diketahui perbedaan antara sentralisasi dan desentralisasi.

6.1 Sentralisasi

Sentralisasi adalah sistem yang memiliki satu titik kontrol utama. Seluruh pengambilan keputusan dan pengelolaan sistem berada di bawah kendali pusat.

Kelebihannya adalah pengaturan dan pengawasan lebih mudah dilakukan karena terdapat satu pihak yang memiliki kewenangan utama.

Namun, sistem sentralisasi memiliki kelemahan berupa ketergantungan terhadap pusat kendali. Jika pusat mengalami gangguan, keseluruhan sistem dapat terdampak.

6.2 Desentralisasi

Desentralisasi merupakan sistem yang membagi kontrol kepada beberapa pihak atau node. Tidak terdapat satu titik pusat yang memiliki kendali penuh terhadap seluruh sistem.

Keputusan dapat dihasilkan melalui mekanisme kerja sama dan konsensus antaranggota jaringan.

Konsensus adalah mekanisme yang digunakan oleh beberapa node untuk mencapai kesepakatan mengenai suatu keputusan atau kondisi sistem.

Dengan adanya pembagian kontrol, sistem tidak hanya bergantung pada satu pihak atau satu titik pengendali.

6.3 Contoh Sistem Terdesentralisasi

Beberapa contoh sistem terdesentralisasi yang disebutkan dalam modul adalah:

Blockchain: Teknologi yang memungkinkan pencatatan transaksi dan pengelolaan data melalui jaringan node dengan mekanisme konsensus.

DNS (Domain Name System): Sistem yang digunakan untuk menerjemahkan nama domain menjadi alamat IP melalui infrastruktur yang tersebar dan memiliki struktur hierarkis.

BitTorrent: Teknologi berbagi file yang memungkinkan pertukaran data secara langsung antaranggota jaringan.

## 7. Perbedaan Kedua Sistem

Meskipun memiliki keterkaitan, sistem terdistribusi dan sistem terdesentralisasi merupakan dua konsep yang berbeda.

Perbedaan utama keduanya terletak pada fokus penerapannya.

7.1 Sistem Terdistribusi

Sistem terdistribusi berfokus pada pembagian beban kerja atau pemrosesan ke beberapa komputer.

Tujuan utamanya adalah meningkatkan kemampuan sistem dalam menangani data dan permintaan pengguna, meningkatkan kinerja, serta mendukung skalabilitas dan ketersediaan layanan.

Contoh penerapannya adalah Google File System dan MinIO Object Storage.

7.2 Sistem Terdesentralisasi

Sistem terdesentralisasi berfokus pada pembagian kontrol atau kewenangan kepada beberapa node atau pihak.

Tujuan utamanya adalah mengurangi ketergantungan terhadap satu pengendali pusat dan memungkinkan keputusan dilakukan melalui mekanisme bersama.

Contoh penerapannya adalah blockchain.

## 8. Studi Kasus Sistem Terdistribusi

Dalam kehidupan sehari-hari, terdapat banyak teknologi yang menerapkan prinsip sistem terdistribusi.

8.1 Google File System (GFS) dan HDFS

Google File System dan Hadoop Distributed File System (HDFS) merupakan teknologi penyimpanan yang dirancang untuk menangani data dalam jumlah besar.

Data dapat disimpan dan dikelola melalui beberapa komputer sehingga kapasitas penyimpanan tidak hanya bergantung pada satu perangkat.

Pendekatan ini memungkinkan pengelolaan data berskala besar menjadi lebih efisien.

8.2 Apache Kafka dan Apache Pulsar

Apache Kafka dan Apache Pulsar merupakan teknologi yang digunakan untuk messaging dan streaming data.

Messaging berkaitan dengan pengiriman pesan atau informasi antarbagian sistem, sedangkan streaming merupakan proses pengiriman dan pemrosesan data secara berkelanjutan.

Keduanya dapat digunakan untuk mendukung komunikasi antarlayanan dan pengolahan data dalam jumlah besar.

8.3 Netflix dan Twitch

Netflix dan Twitch merupakan contoh layanan digital yang membutuhkan infrastruktur terdistribusi untuk mendukung aktivitas penggunanya.

Netflix menyediakan layanan streaming video, sedangkan Twitch menyediakan layanan streaming dan interaksi secara langsung.

Sistem harus mampu melayani banyak pengguna, mengelola data, serta mendistribusikan konten secara efisien.

8.4 YouTube

YouTube merupakan platform berbagi video yang harus menangani penyimpanan, pemrosesan, dan distribusi video dalam skala besar.

Penggunaan pendekatan terdistribusi mendukung pengelolaan berbagai kebutuhan layanan tersebut.

8.5 Instagram, Threads, Facebook, dan TikTok

Platform media sosial membutuhkan sistem yang dapat menangani banyak pengguna secara bersamaan.

Setiap pengguna dapat mengunggah foto, video, komentar, dan pesan. Seluruh aktivitas tersebut menghasilkan data yang harus diproses dan disimpan.

Sistem terdistribusi membantu mendukung pemrosesan dan penyediaan layanan kepada pengguna dalam jumlah besar.

## 9. Studi Kasus Sistem Terdesentralisasi

9.1 Blockchain

Blockchain merupakan salah satu contoh teknologi terdesentralisasi yang paling dikenal.

Blockchain bekerja melalui jaringan komputer atau node yang saling terhubung untuk menyimpan dan memverifikasi informasi.

Dalam sistem ini, keputusan dan validasi transaksi dilakukan melalui mekanisme konsensus. Dengan demikian, pencatatan transaksi tidak hanya bergantung pada satu server atau pengendali pusat.

Contoh platform blockchain yang disebutkan dalam modul adalah:

Bitcoin

Ethereum

Algorand

Sui

Near

Aptos

9.2 DNS (Domain Name System)

DNS merupakan sistem yang digunakan untuk menerjemahkan nama domain menjadi alamat IP sehingga perangkat dapat menemukan server tujuan.

DNS menggunakan infrastruktur yang tersebar dan memiliki struktur hierarkis. Hal ini memungkinkan proses pencarian informasi domain dilakukan melalui berbagai komponen yang saling berhubungan.

9.3 BitTorrent

BitTorrent merupakan teknologi berbagi file yang menggunakan pendekatan peer-to-peer.

Pengguna dapat mengunduh dan membagikan bagian file kepada pengguna lainnya. Dengan demikian, proses distribusi file tidak harus bergantung pada satu server pusat.

## 10. CAP Theorem

CAP Theorem merupakan konsep penting dalam perancangan sistem terdistribusi yang diperkenalkan oleh Eric Brewer pada tahun 2000.

CAP merupakan singkatan dari tiga karakteristik utama, yaitu Consistency, Availability, dan Partition Tolerance.

10.1 Consistency (Konsistensi)

Consistency merupakan kondisi ketika setiap operasi pembacaan data mengembalikan hasil penulisan terbaru atau menghasilkan error.

Artinya, data yang dibaca harus mencerminkan kondisi terbaru sesuai dengan jaminan konsistensi sistem.

10.2 Availability (Ketersediaan)

Availability merupakan kondisi ketika setiap permintaan yang diterima oleh node yang tidak mengalami kegagalan akan memperoleh respons yang tidak menghasilkan error, meskipun data yang diberikan belum tentu merupakan data terbaru.

Dengan kata lain, sistem tetap memberikan layanan kepada pengguna.

10.3 Partition Tolerance (Toleransi Partisi)

Partition Tolerance merupakan kemampuan sistem untuk tetap beroperasi meskipun komunikasi antar-node mengalami gangguan, terputus, atau terfragmentasi.

Gangguan komunikasi dapat menyebabkan beberapa bagian jaringan tidak dapat bertukar informasi secara normal.

10.4 Trade-off dalam CAP Theorem

Dalam distributed data store, ketiga karakteristik CAP tidak dapat dijamin secara bersamaan ketika terjadi network partition.

Ketika partition terjadi, perancang sistem harus menentukan prioritas antara konsistensi dan ketersediaan.

Terdapat dua pendekatan utama:

A. AP (Availability + Partition Tolerance)

Sistem mengutamakan ketersediaan layanan dan kemampuan menghadapi gangguan komunikasi antar-node.

Permintaan terhadap data tetap dilayani, tetapi terdapat risiko bahwa data yang diberikan belum sinkron atau belum merupakan data terbaru.

Dengan demikian, sistem mengorbankan konsistensi selama kondisi partition berlangsung.

Contoh yang dicantumkan dalam modul: MongoDB.

B. CP (Consistency + Partition Tolerance)

Sistem mengutamakan konsistensi data dan kemampuan menghadapi gangguan komunikasi antar-node.

Ketika terjadi partition, permintaan pembacaan maupun penulisan data tertentu dapat ditolak agar konsistensi tetap terjaga.

Dengan demikian, sistem mengorbankan ketersediaan layanan selama kondisi partition berlangsung.

Contoh yang dicantumkan dalam modul: Apache Cassandra.

10.5 Kesimpulan CAP Theorem

CAP Theorem menunjukkan bahwa perancangan sistem terdistribusi memerlukan pertimbangan terhadap kebutuhan sistem.

Apabila konsistensi data menjadi prioritas utama, sistem dapat memilih pendekatan CP. Namun, apabila ketersediaan layanan lebih diutamakan, sistem dapat memilih pendekatan AP.

Pemilihan tersebut harus disesuaikan dengan karakteristik dan kebutuhan aplikasi yang dibangun.

## 11. Konsistensi Data

Konsistensi data merupakan salah satu aspek penting dalam sistem terdistribusi karena data dapat disimpan atau direplikasi pada beberapa komputer yang berbeda.

Modul menjelaskan dua jenis konsistensi data.

11.1 Strong Consistency

Strong Consistency merupakan kondisi ketika hasil pembacaan data selalu mencerminkan nilai terbaru sesuai dengan urutan operasi yang dijamin sistem.

Artinya, ketika terjadi perubahan data, pembacaan berikutnya harus memperoleh data terbaru sesuai jaminan konsistensi tersebut.

Contohnya adalah sistem perbankan. Informasi saldo dan transaksi harus memiliki konsistensi yang kuat agar tidak terjadi kesalahan dalam pencatatan keuangan.

11.2 Eventual Consistency

Eventual Consistency merupakan kondisi ketika data yang tersimpan pada beberapa bagian sistem mungkin belum sama dalam waktu tertentu, tetapi pada akhirnya akan menjadi konsisten apabila tidak ada perubahan baru dan proses sinkronisasi berhasil.

Contohnya adalah media sosial. Ketika seseorang mengunggah sebuah foto atau memperbarui informasi, perubahan tersebut mungkin tidak langsung terlihat oleh seluruh pengguna pada waktu yang sama.

Namun, setelah proses sinkronisasi berlangsung, informasi akan menjadi konsisten.

## 12. Tantangan

Walaupun memiliki banyak keunggulan, penerapan kedua sistem ini juga menghadapi berbagai tantangan.

12.1 Latency dan Throughput

Latency merupakan waktu yang dibutuhkan oleh sistem untuk memproses suatu permintaan hingga menghasilkan respons.

Semakin tinggi latency, semakin lama pengguna harus menunggu hasil dari sistem.

Throughput merupakan jumlah pekerjaan, permintaan, atau data yang dapat diproses oleh sistem dalam periode waktu tertentu.

Sistem yang baik harus mampu menjaga latency tetap rendah dan throughput tetap tinggi agar dapat melayani pengguna secara efisien.

12.2 Keamanan Sistem

Sistem terdistribusi dan terdesentralisasi memiliki tantangan keamanan karena terdiri dari banyak node yang saling berkomunikasi melalui jaringan.

Beberapa ancaman yang perlu diperhatikan adalah serangan DDoS dan Sybil Attack.

Distributed Denial of Service (DDoS) merupakan serangan yang bertujuan membanjiri suatu layanan dengan permintaan dalam jumlah besar sehingga sistem kesulitan melayani pengguna yang sebenarnya.

Serangan ini dapat mengganggu ketersediaan layanan.

12.3 Sybil Attack

Sybil Attack merupakan jenis serangan siber yang dilakukan dengan membuat banyak identitas palsu, seperti akun, node, atau pseudonim dalam jumlah besar.

Tujuannya adalah mendominasi pengaruh, suara, atau reputasi di dalam jaringan.

Dalam sistem peer-to-peer atau blockchain, penyerang dapat menggunakan banyak identitas palsu untuk memanipulasi mekanisme pengambilan keputusan atau merusak integritas sistem.

Dengan menyamar sebagai banyak pengguna yang sah, penyerang dapat melakukan tindakan tidak sah dan berusaha memperoleh akses terhadap informasi sensitif.

Oleh karena itu, sistem terdesentralisasi membutuhkan mekanisme keamanan yang dapat memastikan bahwa identitas dan partisipasi node tidak mudah dimanipulasi.

12.4 Kompleksitas Manajemen Node

Sistem yang memiliki banyak komputer atau node membutuhkan pengelolaan yang lebih kompleks.

Setiap node harus dapat berkomunikasi, bertukar data, dan menjalankan tugas sesuai perannya.

Ketika salah satu node mengalami gangguan, sistem harus mampu mendeteksi dan menangani permasalahan tersebut tanpa mengganggu keseluruhan layanan.

12.5 Governance (Tata Kelola)

Governance merupakan tantangan khusus dalam sistem terdesentralisasi.

Karena kontrol dibagi kepada beberapa pihak, diperlukan mekanisme untuk mengatur pengambilan keputusan, perubahan aturan, dan penyelesaian perbedaan pendapat.

Tanpa tata kelola yang baik, sistem dapat mengalami konflik dalam menentukan keputusan atau arah pengembangan.

## 13. Tren Masa Depan

Perkembangan teknologi terus mendorong munculnya berbagai pendekatan baru dalam sistem terdistribusi dan terdesentralisasi.

Modul menjelaskan beberapa tren masa depan sebagai berikut.

13.1 Cloud-Native

Cloud-native merupakan pendekatan pengembangan aplikasi yang dirancang agar dapat berjalan secara optimal dalam lingkungan cloud.

Teknologi yang berkaitan dengan pendekatan ini antara lain Docker dan Kubernetes.

Docker: Teknologi yang digunakan untuk mengemas aplikasi beserta kebutuhan pendukungnya ke dalam container.

Kubernetes: Platform yang digunakan untuk mengelola dan mengatur container dalam lingkungan sistem berskala besar.

Keduanya membantu pengembangan dan pengelolaan aplikasi modern yang membutuhkan fleksibilitas dan skalabilitas.

13.2 Edge dan Fog Computing

Edge Computing merupakan pendekatan pemrosesan data yang dilakukan lebih dekat dengan sumber data atau perangkat yang menghasilkan data.

Sementara itu, Fog Computing merupakan pendekatan yang menyediakan lapisan komputasi dan pengolahan data antara perangkat edge dengan pusat cloud.

Kedua pendekatan tersebut mendukung pemrosesan data secara lebih dekat dengan sumbernya dan menjadi bagian dari perkembangan infrastruktur komputasi terdistribusi.

13.3 Web3 dan DeFi

Web3 merupakan konsep perkembangan internet yang berkaitan dengan penggunaan teknologi terdesentralisasi.

Salah satu teknologi yang mendukung perkembangan Web3 adalah blockchain.

DeFi atau Decentralized Finance merupakan konsep layanan keuangan yang memanfaatkan teknologi terdesentralisasi untuk menjalankan berbagai aktivitas keuangan.

Keduanya menjadi bagian dari perkembangan teknologi yang berusaha mengurangi ketergantungan pada pengelolaan layanan secara terpusat.

13.4 Federated Data dan Federated Learning

Federated Learning merupakan pendekatan dalam kecerdasan buatan yang memungkinkan proses pelatihan model dilakukan pada beberapa perangkat atau lokasi yang berbeda.

Pendekatan ini berkaitan dengan konsep AI terdistribusi karena proses pembelajaran tidak harus sepenuhnya dilakukan pada satu pusat pemrosesan data.

Teknologi ini menjadi salah satu tren dalam pengembangan sistem kecerdasan buatan yang memanfaatkan sumber daya komputasi dari berbagai lokasi.

## 14. Kesimpulan

Berdasarkan pembahasan Modul 01, dapat disimpulkan bahwa sistem terdistribusi dan sistem terdesentralisasi merupakan dua konsep penting dalam perkembangan teknologi informasi modern.

Sistem terdistribusi merupakan sekumpulan komputer independen yang saling berkomunikasi melalui jaringan dan bekerja sama sehingga terlihat sebagai satu kesatuan sistem. Fokus utamanya adalah pembagian beban kerja, peningkatan kinerja, skalabilitas, dan kemampuan menghadapi kegagalan komponen.

Sementara itu, sistem terdesentralisasi merupakan sistem yang membagi kontrol atau kewenangan kepada beberapa pihak atau node sehingga tidak bergantung sepenuhnya pada satu titik pengendali. Mekanisme konsensus menjadi salah satu bagian penting dalam pengambilan keputusan pada sistem tersebut.

Keduanya memiliki hubungan yang erat, tetapi tidak dapat dianggap sebagai konsep yang sama. Sistem terdistribusi berorientasi pada pembagian pekerjaan, sedangkan sistem terdesentralisasi berorientasi pada pembagian kontrol.

Selain itu, materi CAP Theorem memberikan pemahaman bahwa perancangan sistem terdistribusi harus mempertimbangkan konsistensi, ketersediaan, dan toleransi terhadap gangguan jaringan. Pemilihan pendekatan AP atau CP perlu disesuaikan dengan kebutuhan sistem.

Materi ini juga menjelaskan berbagai tantangan, seperti latency, throughput, keamanan, Sybil Attack, kompleksitas pengelolaan node, dan governance. Di sisi lain, perkembangan cloud-native, edge computing, fog computing, Web3, DeFi, dan federated learning menunjukkan bahwa sistem terdistribusi dan terdesentralisasi akan terus menjadi fondasi penting dalam perkembangan teknologi masa depan.

Dengan mempelajari modul ini, mahasiswa diharapkan mampu memahami dasar-dasar sistem terdistribusi dan terdesentralisasi, membedakan kedua konsep tersebut, serta mengenali penerapannya dalam kehidupan sehari-hari dan dunia teknologi informasi.

## 15. Daftar Referensi

1. Tanenbaum, A. S., & van Steen, M. (2007). Distributed Systems: Principles and Paradigms. Second Edition. Prentice Hall.

2. Brewer, E. (2000). Towards Robust Distributed Systems. Proceedings of the Nineteenth Annual ACM Symposium on Principles of Distributed Computing.

3. Purnomosidi, B. (t.t.). Modul 01: Pengenalan Sistem Terdistribusi dan Terdesentralisasi. Fakultas Teknologi Informasi, Universitas Teknologi Digital Indonesia (UTDI).
