# RANGKUMAN MODUL 06: Distributed File System

# Nama Lengkap : Diana Amelia

# NIM : 255410042

# Kelas : Informatika-1

# AI yang digunakan : chatgpt

# Prompt : #bertindaklah aku sebagai mahasiswa aktif dalam mata kuliah sistem terdistribusi dan terdesentralisasi, berikan aku rangkuman dari modul 06 mata kuliah ini dalam bentuk markdown (README.md), jabarkan secara detail dan ringkas mengenai isi dari modul tersebut agar mudah dipahami untuk tugas laporan rangkuman modul tersebut.

# Hasil Rangkuman Modul 06 :

## 1. Pendahuluan

Distributed File System (DFS) merupakan salah satu konsep penting dalam sistem terdistribusi yang memungkinkan pengelolaan dan penyimpanan data pada beberapa komputer atau server secara bersamaan. Dengan teknologi ini, berbagai media penyimpanan yang tersebar dapat diintegrasikan sehingga terlihat seperti satu sistem penyimpanan yang utuh.

Pada Modul 06 dibahas mengenai konsep dasar File System, Distributed File System, cara kerja DFS, berbagai implementasi DFS, Hadoop Distributed File System (HDFS), serta hubungan antara DFS dengan Cloud Storage.

Tujuan utama pembelajaran ini adalah memahami bagaimana data dapat disimpan, dikelola, dan diakses secara terdistribusi dengan tetap memperhatikan keandalan, ketersediaan, dan performa sistem.

## 2. Pengertian File System

File System (FS) adalah metode yang digunakan oleh sistem operasi untuk mengelola dan mengatur file pada media penyimpanan, seperti hard disk, SSD, dan USB flash drive.

File System berfungsi untuk mengatur bagaimana data disimpan, diberi nama, diakses, dibaca, dan dikelola oleh sistem operasi.

Beberapa contoh File System berdasarkan sistem operasi:

- **Linux:** ext4, XFS, btrfs, ReiserFS.
- **Windows/DOS:** FAT16, FAT32, NTFS.
- **macOS:** APFS (Apple File System).

### 2.1 Cara Kerja File System

Dalam sistem operasi, aplikasi tidak berkomunikasi secara langsung dengan perangkat penyimpanan. Terdapat beberapa lapisan yang mengatur proses tersebut.

Alur kerja File System:

1. **Application:** Aplikasi melakukan permintaan operasi file, seperti membaca atau menulis data.
2. **System Call Interface:** Menjadi penghubung antara aplikasi dan layanan sistem operasi.
3. **Virtual File System (VFS):** Menyediakan antarmuka umum agar aplikasi dapat mengakses berbagai jenis File System.
4. **File System Driver:** Driver pada kernel menerjemahkan operasi sesuai jenis File System yang digunakan.
5. **Hardware:** Media penyimpanan menjalankan proses pembacaan dan penulisan data.

Ilustrasi alur:

```text
Application
     |
     v
System Call Interface
     |
     v
Virtual File System (VFS)
     |
     v
File System Driver (Kernel)
     |
     v
Storage Hardware
```

### 2.2 Perbedaan File System dan Hierarki File System

File System dan hierarki File System merupakan dua konsep yang berbeda.

- **File System:** Mekanisme atau metode yang digunakan untuk mengelola file pada media penyimpanan.
- **Hierarki File System:** Struktur atau susunan file dan direktori dalam sistem operasi.

Pengguna umumnya hanya melihat susunan direktori dan file tanpa perlu mengetahui jenis File System yang digunakan di baliknya.

## 3. Pengertian Distributed File System (DFS)

Distributed File System adalah suatu sistem abstraksi terkoordinasi dari sekumpulan media penyimpanan yang berada pada beberapa komputer atau node. Sistem ini menggabungkan berbagai media penyimpanan sehingga dari sisi pengguna terlihat seperti satu media penyimpanan yang terintegrasi.

DFS tidak hanya sekadar File System yang tersebar pada lebih dari satu komputer, tetapi juga memiliki kemampuan untuk menangani beberapa permasalahan dalam sistem terdistribusi, yaitu:

1. **Heterogenitas:** Mampu menangani perbedaan perangkat keras maupun sistem yang digunakan oleh setiap node.
2. **Kegagalan (Failure):** Mampu menangani gangguan pada salah satu node atau media penyimpanan.
3. **Konkurensi (Concurrency):** Memungkinkan beberapa pengguna atau proses mengakses data secara bersamaan.

Tujuan utama DFS adalah menghasilkan sistem penyimpanan yang terintegrasi, andal, dan memiliki kinerja tinggi.

### 3.1 Perbedaan DAS, NAS, SAN, dan DFS

Berikut merupakan perbedaan beberapa jenis teknologi penyimpanan:

| Jenis                          | Pengertian                                                                                    |
| ------------------------------ | --------------------------------------------------------------------------------------------- |
| DAS (Direct-Attached Storage)  | Media penyimpanan yang terhubung langsung dengan komputer atau server.                        |
| NAS (Network-Attached Storage) | Perangkat penyimpanan yang menyediakan akses file melalui jaringan.                           |
| SAN (Storage Area Network)     | Sistem penyimpanan berbasis block-level yang dapat dihubungkan langsung ke server.            |
| DFS (Distributed File System)  | Sistem penyimpanan yang mengelola file dan direktori secara terdistribusi pada beberapa node. |

DFS merupakan abstraksi pada tingkat perangkat lunak yang mengelola data dalam bentuk file dan direktori.

Sementara itu, SAN menyediakan penyimpanan dalam bentuk blok yang dapat digunakan dan diformat menggunakan File System tersendiri.

SAN dapat digunakan sebagai media penyimpanan untuk DFS, meskipun penggunaan tersebut tidak disarankan dalam materi modul. SAN umumnya digunakan sebagai backend untuk database berskala besar, pengolahan video dan audio, serta virtualisasi.

DFS lebih mengarah pada penggunaan DAS pada setiap node.

## 4. Berbagai Jenis Distributed File System

Terdapat beberapa contoh Distributed File System yang umum digunakan, antara lain:

1. **Google File System (GFS)**

   Google File System merupakan sistem file terdistribusi yang dikembangkan oleh Google untuk mengelola penyimpanan data dalam skala besar.

2. **Colossus**

   Colossus merupakan penerus Google File System yang digunakan dalam berbagai layanan Google, seperti YouTube, Gmail, dan Google Docs.

3. **CephFS**

   CephFS merupakan sistem file terdistribusi yang menjadi bagian dari ekosistem penyimpanan Ceph.

4. **Gluster**

   Gluster merupakan solusi penyimpanan terdistribusi yang memungkinkan penggabungan kapasitas penyimpanan dari beberapa server.

5. **HDFS (Hadoop Distributed File System)**

   HDFS merupakan sistem file terdistribusi yang menjadi bagian utama dari Apache Hadoop dan dirancang untuk menyimpan dataset berukuran besar.

6. **Lustre**

   Lustre merupakan sistem file terdistribusi yang banyak digunakan dalam lingkungan komputasi berkinerja tinggi.

## 5. Studi Kasus: Hadoop Distributed File System (HDFS)

### 5.1 Pengertian HDFS

Hadoop Distributed File System (HDFS) merupakan sistem File System yang bersifat open source, scalable, terdistribusi, dan fault-tolerant.

HDFS dirancang untuk mengelola serta menyimpan dataset berukuran besar pada klaster yang terdiri dari beberapa komputer atau server.

HDFS merupakan komponen utama dari Apache Hadoop yang digunakan dalam pemrosesan data berskala besar.

HDFS menggunakan konsep pembagian file menjadi beberapa blok, kemudian mendistribusikan blok tersebut ke beberapa server. Selain itu, HDFS menerapkan replikasi data untuk meningkatkan ketersediaan dan keandalan penyimpanan.

### 5.2 Karakteristik HDFS

Beberapa karakteristik utama HDFS adalah:

- **Open Source:** Dapat digunakan dan dikembangkan secara terbuka.
- **Scalable:** Dapat dikembangkan dengan menambahkan node atau server baru.
- **Distributed:** Data disimpan dan didistribusikan ke beberapa komputer.
- **Fault-Tolerant:** Mampu menangani kegagalan komponen penyimpanan.
- **Replication:** Membuat salinan data pada beberapa node untuk meningkatkan ketersediaan.
- **Big Data Support:** Dirancang untuk mengelola dan menyimpan dataset berukuran besar.

HDFS menggunakan commodity hardware, yaitu perangkat keras komputer yang diproduksi secara massal, relatif murah, mudah dipertukarkan, dan tersedia dari berbagai vendor.

### 5.3 Cara Kerja HDFS

Secara umum, HDFS bekerja dengan membagi file menjadi beberapa blok data yang kemudian disimpan pada beberapa node dalam sebuah klaster.

Tahapan cara kerjanya:

1. Pengguna memasukkan file ke dalam HDFS.
2. HDFS membagi file menjadi beberapa blok data.
3. Blok data didistribusikan ke beberapa server atau node.
4. Sistem membuat salinan blok berdasarkan konfigurasi replikasi.
5. Ketika pengguna ingin membaca file, HDFS mengakses blok-blok yang tersimpan pada node terkait.
6. Blok tersebut disajikan kembali sebagai satu file kepada pengguna.

Dengan mekanisme tersebut, HDFS dapat memanfaatkan kapasitas penyimpanan dari banyak komputer sekaligus.

Replikasi juga membantu menjaga ketersediaan data apabila terjadi kerusakan atau kegagalan pada salah satu node.

## 6. Instalasi dan Konfigurasi Apache Hadoop HDFS

Dalam praktik Modul 06, digunakan Apache Hadoop versi 3.5.0 untuk memahami implementasi Distributed File System secara langsung.

### 6.1 Persyaratan Software

Beberapa perangkat lunak yang diperlukan untuk instalasi Hadoop antara lain:

- JDK versi 17 dan/atau 21.
- Apache Hadoop versi 3.5.0.
- pdsh.
- SSH.
- SSHD yang sudah berjalan.

JDK 17 digunakan untuk server dan kompilasi Apache Hadoop, sedangkan client dapat menggunakan JDK 17 atau 21.

### 6.2 Mengunduh Apache Hadoop

Apache Hadoop dapat diunduh melalui halaman resmi:

https://hadoop.apache.org/releases.html

Setelah proses pengunduhan selesai, file Hadoop diekstrak dan ditempatkan pada direktori yang diinginkan.

Contoh perintah:

```bash
cd ~/software/storage/

tar -xvf ~/master/data-engineering/apache-hadoop/hadoop-3.5.0.tar.gz

ln -s hadoop-3.5.0 hadoop
```

Direktori instalasi Hadoop selanjutnya disebut sebagai `$HADOOP_HOME`.

### 6.3 Konfigurasi Environment Variable

Environment variable digunakan agar perintah Hadoop dapat dijalankan melalui terminal.

Setelah konfigurasi environment selesai, jalankan:

```bash
source ~/env/bash/storage/hadoop.sh
```

Untuk memastikan instalasi berhasil, jalankan:

```bash
hadoop
```

Jika Hadoop menampilkan informasi penggunaan perintah, berarti instalasi awal telah berhasil dikenali oleh sistem.

### 6.4 Instalasi pdsh dan Konfigurasi SSH

pdsh digunakan untuk menjalankan perintah pada beberapa host atau komputer secara bersamaan.

Apabila menggunakan SSH sebagai remote command, konfigurasi dapat dilakukan dengan:

```bash
export PDSH_RCMD_TYPE=ssh
```

Selanjutnya, agar SSH ke localhost tidak memerlukan login menggunakan password, jalankan:

```bash
ssh-keygen -t rsa -P '' -f ~/.ssh/id_rsa

cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys

chmod 0600 ~/.ssh/authorized_keys
```

Konfigurasi tersebut digunakan untuk memungkinkan autentikasi SSH menggunakan pasangan kunci.

### 6.5 Konfigurasi HDFS

Konfigurasi Hadoop dilakukan pada direktori:

```text
$HADOOP_HOME/etc/hadoop/
```

Terdapat beberapa file konfigurasi utama yang digunakan.

**A. hdfs-site.xml**

File ini digunakan untuk mengatur konfigurasi HDFS, salah satunya jumlah replikasi data.

Contoh konfigurasi:

```xml
<configuration>
    <property>
        <name>dfs.replication</name>
        <value>1</value>
    </property>
</configuration>
```

Nilai `1` menunjukkan bahwa konfigurasi contoh tersebut menggunakan satu salinan blok data.

**B. core-site.xml**

File ini digunakan untuk menentukan alamat File System default Hadoop.

Contoh konfigurasi:

```xml
<configuration>
    <property>
        <name>fs.defaultFS</name>
        <value>hdfs://localhost:9000</value>
    </property>

    <property>
        <name>hadoop.proxyuser.yourusername.groups</name>
        <value>*</value>
    </property>

    <property>
        <name>hadoop.proxyuser.yourusername.hosts</name>
        <value>*</value>
    </property>
</configuration>
```

Konfigurasi `fs.defaultFS` menunjukkan alamat HDFS yang digunakan, yaitu localhost dengan port 9000.

Nama `yourusername` perlu disesuaikan dengan nama pengguna yang digunakan.

**C. mapred-site.xml**

File ini digunakan untuk mengatur konfigurasi MapReduce.

Contoh konfigurasi:

```xml
<configuration>
    <property>
        <name>mapreduce.framework.name</name>
        <value>yarn</value>
    </property>

    <property>
        <name>mapreduce.application.classpath</name>
        <value>$HADOOP_CLASSPATH:$HADOOP_HOME/share/hadoop/mapreduce/*:$HADOOP_MAPRED_HOME/share/hadoop/mapreduce/lib/*</value>
    </property>
</configuration>
```

Konfigurasi tersebut menentukan bahwa framework yang digunakan untuk menjalankan MapReduce adalah YARN.

**D. yarn-site.xml**

File ini digunakan untuk mengatur konfigurasi YARN, termasuk layanan tambahan dan pengaturan penggunaan memori.

Contoh konfigurasi:

```xml
<configuration>
    <property>
        <name>yarn.nodemanager.aux-services</name>
        <value>mapreduce_shuffle</value>
    </property>

    <property>
        <name>yarn.nodemanager.env-whitelist</name>
        <value>JAVA_HOME,HADOOP_COMMON_HOME,HADOOP_HDFS_HOME,HADOOP_CONF_DIR,CLASSPATH_PREPEND_DISTCACHE,HADOOP_YARN_HOME,HADOOP_HOME,PATH,LANG,TZ,HADOOP_MAPRED_HOME</value>
    </property>

    <property>
        <name>yarn.nodemanager.resource.memory-mb</name>
        <value>4096</value>
    </property>

    <property>
        <name>yarn.scheduler.minimum-allocation-mb</name>
        <value>2048</value>
    </property>

    <property>
        <name>yarn.nodemanager.vmem-pmem-ratio</name>
        <value>2.1</value>
    </property>
</configuration>
```

Konfigurasi tersebut mengatur layanan NodeManager, variabel lingkungan, alokasi memori, dan rasio memori virtual terhadap memori fisik.

### 6.6 Format NameNode

Setelah konfigurasi Hadoop selesai, tahap berikutnya adalah melakukan format NameNode.

Proses format NameNode dilakukan satu kali pada saat inisialisasi awal HDFS.

**Penting:** Format NameNode tidak boleh dilakukan berulang kali karena dapat menghapus berbagai file yang telah diproses dan disimpan di HDFS.

### 6.7 Konfigurasi JAVA_HOME

Konfigurasi JAVA_HOME dilakukan melalui file:

```text
$HADOOP_HOME/etc/hadoop/hadoop-env.sh
```

Lokasi instalasi Java harus disesuaikan dengan lokasi JDK yang digunakan pada komputer atau server.

### 6.8 Menjalankan HDFS

Setelah seluruh konfigurasi selesai, daemon HDFS dapat dijalankan sesuai prosedur pada panduan praktik.

Pemantauan sistem dapat dilakukan melalui antarmuka web yang disediakan oleh Hadoop.

Apabila seluruh proses berhasil, Hadoop dan HDFS sudah siap digunakan untuk melakukan operasi penyimpanan file.

Untuk melihat daftar lengkap perintah HDFS, pengguna dapat mengakses dokumentasi resmi:

https://hadoop.apache.org/docs/current/hadoop-project-dist/hadoop-common/FileSystemShell.html

## 7. Pengertian Cloud Storage

Cloud Storage merupakan layanan penyimpanan data secara online yang memungkinkan pengguna menyimpan dan mengakses data melalui server jarak jauh menggunakan jaringan internet.

Berbeda dengan penyimpanan lokal yang menggunakan hard disk atau SSD pada komputer pribadi, Cloud Storage memanfaatkan infrastruktur server yang dikelola oleh penyedia layanan cloud.

Data yang disimpan dapat berada pada beberapa server, bahkan di lokasi geografis yang berbeda.

Cloud Storage memungkinkan pengguna mengakses data dari berbagai perangkat selama memiliki koneksi jaringan dan hak akses yang sesuai.

Contoh layanan Cloud Storage:

1. Amazon S3.
2. Azure Blob Storage.
3. Google Cloud Storage (GCS).

## 8. Hubungan Cloud Storage dengan Distributed File System

Cloud Storage dan Distributed File System memiliki hubungan yang erat dalam pengelolaan penyimpanan data.

Cloud Storage berfungsi sebagai tempat atau media penyimpanan data, sedangkan DFS bertugas mengelola dan mengorganisasikan data tersebut melalui mekanisme File System.

Dengan kata lain:

- **Cloud Storage:** Menyediakan kapasitas penyimpanan pada infrastruktur cloud.
- **DFS:** Mengatur bagaimana data disimpan, diakses, dan dikelola sebagai file dan direktori.

Salah satu contoh penerapannya adalah penggunaan Amazon S3 bersama HDFS.

Dalam penerapan tersebut, S3 berperan sebagai Cloud Storage, sedangkan HDFS digunakan untuk melakukan operasi File System.

Konfigurasi integrasi tersebut dapat dilakukan melalui file `core-site.xml`.

## 9. Tipe-Tipe Cloud Storage

Dalam Modul 06 dijelaskan bahwa Cloud Storage memiliki tiga tipe utama.

### 9.1 Object Storage

Object Storage merupakan jenis penyimpanan yang menyimpan data dalam bentuk objek.

Setiap objek memiliki data, metadata, dan identitas tertentu sehingga dapat dikelola serta diakses melalui layanan penyimpanan.

Object Storage umum digunakan untuk menyimpan data dalam jumlah besar.

Contoh: Amazon S3 dan Google Cloud Storage.

### 9.2 File Storage

File Storage merupakan jenis penyimpanan yang mengelola data dalam bentuk file dan direktori.

Struktur penyimpanannya menggunakan hierarki folder sehingga pengguna dapat mengakses data berdasarkan lokasi direktori dan nama file.

Model ini cocok untuk aplikasi yang membutuhkan pengelolaan file secara terstruktur.

### 9.3 Block Storage

Block Storage merupakan jenis penyimpanan yang membagi data menjadi blok-blok berukuran tertentu.

Setiap blok dapat dikelola dan diakses secara terpisah oleh sistem.

Block Storage biasanya digunakan sebagai media penyimpanan untuk server, database, dan kebutuhan sistem yang membutuhkan akses penyimpanan tingkat blok.

## 10. Kesimpulan

Berdasarkan pembahasan Modul 06, dapat disimpulkan bahwa Distributed File System merupakan teknologi yang memungkinkan penggabungan beberapa media penyimpanan dari berbagai komputer atau server menjadi satu sistem penyimpanan yang terintegrasi.

File System merupakan dasar pengelolaan data pada sistem operasi, sedangkan DFS mengembangkan konsep tersebut dengan mendistribusikan penyimpanan ke beberapa node.

Salah satu implementasi DFS yang dibahas adalah Hadoop Distributed File System (HDFS). HDFS dirancang untuk menyimpan dan mengelola dataset berukuran besar dengan cara membagi file menjadi blok-blok data, mendistribusikannya ke beberapa server, serta menerapkan replikasi untuk meningkatkan ketersediaan data.

Selain itu, Cloud Storage menjadi bagian penting dalam perkembangan teknologi penyimpanan modern karena memungkinkan data disimpan pada infrastruktur jarak jauh dan diakses melalui jaringan.

Cloud Storage memiliki tiga tipe utama, yaitu Object Storage, File Storage, dan Block Storage. Ketiganya memiliki cara pengelolaan dan penggunaan yang berbeda sesuai kebutuhan sistem.

Dengan mempelajari materi ini, mahasiswa dapat memahami bagaimana sistem penyimpanan terdistribusi bekerja, bagaimana HDFS diterapkan menggunakan Apache Hadoop, serta bagaimana Cloud Storage dapat dimanfaatkan sebagai bagian dari infrastruktur penyimpanan modern.

**Inti pembelajaran Modul 06:** Distributed File System memungkinkan penyimpanan data pada banyak komputer dikelola sebagai satu kesatuan, HDFS menjadi salah satu implementasi DFS untuk pengelolaan data berskala besar, sedangkan Cloud Storage menyediakan infrastruktur penyimpanan jarak jauh yang dapat dimanfaatkan dalam sistem terdistribusi.

## 11. Istilah-Istilah Penting

| Istilah                       | Pengertian                                                                            |
| ----------------------------- | ------------------------------------------------------------------------------------- |
| File System (FS)              | Metode untuk mengelola file pada media penyimpanan.                                   |
| Virtual File System (VFS)     | Antarmuka umum untuk mengakses berbagai jenis File System.                            |
| Distributed File System (DFS) | Sistem pengelolaan file yang menggunakan beberapa media penyimpanan pada banyak node. |
| Node                          | Komputer atau server yang menjadi bagian dari sistem terdistribusi.                   |
| HDFS                          | Hadoop Distributed File System, sistem file terdistribusi pada Apache Hadoop.         |
| Block                         | Bagian data hasil pembagian sebuah file pada HDFS.                                    |
| Replication                   | Proses membuat salinan data pada beberapa node.                                       |
| Fault-Tolerant                | Kemampuan sistem dalam menangani kegagalan komponen.                                  |
| NameNode                      | Komponen HDFS yang mengelola metadata dan namespace file system.                      |
| YARN                          | Komponen Hadoop untuk pengelolaan sumber daya dan penjadwalan aplikasi.               |
| Cloud Storage                 | Layanan penyimpanan data melalui jaringan pada server jarak jauh.                     |
| Object Storage                | Penyimpanan data dalam bentuk objek.                                                  |
| File Storage                  | Penyimpanan data dalam bentuk file dan direktori.                                     |
| Block Storage                 | Penyimpanan data dalam bentuk blok-blok.                                              |

---

**Sumber Referensi:**

1. Modul 06 – Distributed File System, Dr. Bambang Purnomosidi D. P., Fakultas Teknologi Informasi, Universitas Teknologi Digital Indonesia.
2. Panduan Praktik – Mulai Menggunakan Apache Hadoop HDFS, Dr. Bambang Purnomosidi D. P.
3. Dokumentasi resmi Apache Hadoop: https://hadoop.apache.org/
