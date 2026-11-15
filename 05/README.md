# RANGKUMAN MODUL 05: Fault Tolerance

# Nama Lengkap : Diana Amelia

# NIM : 255410042

# Kelas : Informatika-1

# AI yang digunakan : chatgpt

# Prompt : #bertindaklah aku sebagai mahasiswa aktif dalam mata kuliah sistem terdistribusi dan terdesentralisasi, berikan aku rangkuman dari modul 05 mata kuliah ini dalam bentuk markdown, jabarkan secara detail dan ringkas mengenai isi dari modul tersebut agar mudah dipahami untuk tugas laporan rangkuman modul tersebut. berikan aku format pengerjannya dalam bentuk markdown (README.md).

# Hasil Rangkuman Modul 05 :

## 1. Pendahuluan

Dalam sistem terdistribusi dan terdesentralisasi, sebuah aplikasi tidak hanya berjalan menggunakan satu komputer atau satu proses. Sistem terdiri dari beberapa komponen yang saling terhubung dan berkomunikasi melalui jaringan.

Kondisi tersebut memungkinkan terjadinya berbagai gangguan, seperti kerusakan perangkat keras, kesalahan perangkat lunak, gangguan jaringan, maupun kegagalan komunikasi antar-komponen.

Oleh karena itu, diperlukan mekanisme yang memungkinkan sistem tetap beroperasi meskipun sebagian komponennya mengalami kegagalan. Mekanisme tersebut dikenal sebagai **Fault Tolerance**.

Fault Tolerance menjadi salah satu aspek penting dalam membangun sistem yang memiliki ketersediaan tinggi (_High Availability_), terutama pada aplikasi yang bersifat kritis (_Mission Critical_) maupun sistem yang berkaitan dengan keselamatan (_Life-Critical System_).

Tujuan utama penerapan Fault Tolerance adalah menjaga agar layanan tetap dapat digunakan, mengurangi dampak kegagalan, dan mempercepat proses pemulihan sistem.

## 2. Tujuan Pembelajaran

Berdasarkan modul perkuliahan, tujuan pembelajaran materi Fault Tolerance adalah:

1. Memahami alasan Fault Tolerance diperlukan dalam sistem terdistribusi dan terdesentralisasi.
2. Memahami pengertian Fault Tolerance dan Fault Tolerant Systems.
3. Mengetahui berbagai jenis kesalahan (_Fault_) dalam sistem teknologi informasi.
4. Memahami klasifikasi Fault berdasarkan sumbernya.
5. Memahami berbagai Design Pattern untuk mencapai Fault Tolerance serta penerapannya menggunakan Python.
6. Mengetahui implementasi Fault Tolerance pada berbagai bahasa pemrograman dan perangkat pengembangan.

## 3. Pengertian Fault Tolerance

**Fault Tolerance** merupakan kemampuan suatu sistem untuk mempertahankan operasionalnya secara tepat meskipun terjadi kegagalan atau kesalahan pada satu atau lebih komponen di dalam sistem tersebut.

Dengan kata lain, sistem yang menerapkan Fault Tolerance tidak langsung berhenti beroperasi ketika salah satu komponennya mengalami gangguan.

Contohnya, sebuah aplikasi web memiliki dua server yang menjalankan aplikasi yang sama. Ketika salah satu server mengalami kegagalan, server lainnya masih dapat melayani permintaan pengguna.

Sistem yang mempunyai kemampuan tersebut disebut **Fault Tolerant System**.

Beberapa karakteristik yang berkaitan dengan Fault Tolerance adalah:

- **Reliability:** Kemampuan sistem untuk beroperasi secara konsisten tanpa mengalami kegagalan.
- **Availability:** Kemampuan sistem untuk tetap tersedia dan dapat diakses pengguna.
- **Redundancy:** Ketersediaan komponen atau sumber daya cadangan.
- **Recovery:** Kemampuan sistem untuk memulihkan operasional setelah mengalami kegagalan.

Perlu dipahami bahwa Fault Tolerance bukan berarti sistem tidak mungkin mengalami kegagalan, melainkan sistem dirancang agar kegagalan tidak menyebabkan seluruh layanan berhenti beroperasi.

## 4. Pentingnya Fault Tolerance dalam Sistem Terdistribusi dan Terdesentralisasi

Sistem terdistribusi dan terdesentralisasi mempunyai banyak komponen yang saling berkomunikasi melalui jaringan. Setiap komponen memiliki kemungkinan mengalami kegagalan secara independen.

Beberapa faktor yang menyebabkan Fault Tolerance menjadi penting antara lain:

1. **Banyaknya Komponen Sistem**

   Semakin banyak komponen yang digunakan, semakin besar kemungkinan salah satu komponen mengalami gangguan.

2. **Ketergantungan terhadap Jaringan**

   Komunikasi antar-komponen membutuhkan koneksi jaringan. Gangguan jaringan dapat menyebabkan keterlambatan, kehilangan paket, atau terputusnya komunikasi.

3. **Kebutuhan High Availability**

   Aplikasi tertentu harus tetap tersedia meskipun terjadi gangguan, misalnya layanan perbankan, sistem transaksi, dan layanan cloud.

4. **Menghindari Single Point of Failure**

   Sistem tidak boleh bergantung hanya pada satu komponen yang apabila mengalami kegagalan dapat menyebabkan seluruh layanan berhenti.

5. **Menjaga Kontinuitas Layanan**

   Pengguna tetap dapat mengakses layanan meskipun sebagian infrastruktur sedang mengalami masalah.

Dengan demikian, Fault Tolerance merupakan salah satu fondasi utama dalam membangun sistem terdistribusi yang andal dan memiliki tingkat ketersediaan tinggi.

## 5. Jenis-Jenis Fault

Dalam sistem teknologi informasi, terdapat beberapa jenis Fault yang dapat menyebabkan gangguan terhadap operasional sistem.

### 5.1 Transient Fault

Transient Fault merupakan kesalahan yang terjadi sementara dan biasanya akan hilang dengan sendirinya setelah kondisi penyebabnya berakhir.

**Contoh:**

- Gangguan listrik sesaat.
- Gangguan akibat petir.
- Gangguan jaringan yang berlangsung dalam waktu singkat.

Penanganannya dapat dilakukan dengan melakukan pengulangan proses (_Retry_) setelah kondisi kembali normal.

### 5.2 Intermittent Fault

Intermittent Fault merupakan kesalahan yang muncul dan menghilang secara berulang. Jenis kesalahan ini lebih sulit dideteksi karena tidak selalu terjadi secara terus-menerus.

**Contoh:**

- Hardware mengalami Overheat.
- Koneksi jaringan yang terkadang terputus.
- Komponen perangkat keras yang bekerja tidak stabil.

Penanganannya membutuhkan pemantauan dan pemeriksaan secara berkala agar penyebab gangguan dapat diketahui.

### 5.3 Permanent Fault

Permanent Fault merupakan kesalahan yang bersifat tetap atau terus berlangsung sampai dilakukan perbaikan atau penggantian komponen.

**Contoh:**

- Hard disk mengalami kerusakan.
- Server mengalami kerusakan perangkat keras.
- File sistem mengalami kerusakan permanen.

Penanganannya dapat menggunakan komponen cadangan, penggantian perangkat, atau pemulihan dari Backup.

### 5.4 Byzantine Fault

Byzantine Fault merupakan kondisi ketika suatu komponen memberikan hasil yang tidak konsisten, salah, atau bahkan acak kepada komponen lainnya.

Contohnya, dalam suatu jaringan yang terdiri dari beberapa Node, terdapat satu Node yang mengirimkan informasi berbeda kepada Node lain sehingga menyebabkan ketidaksepakatan.

Jenis Fault ini menjadi tantangan tersendiri dalam sistem terdistribusi karena komponen lain tidak selalu dapat mengetahui apakah informasi yang diterima benar atau salah.

Penanganannya membutuhkan mekanisme validasi, koordinasi, dan konsensus antar-Node.

## 6. Klasifikasi Fault Berdasarkan Sumber

Selain berdasarkan karakteristiknya, Fault juga dapat dikelompokkan berdasarkan sumber penyebabnya.

### 6.1 Hardware Faults

Hardware Faults merupakan kesalahan yang berasal dari perangkat keras komputer atau infrastruktur fisik.

**Contoh:**

- Disk Crash atau kerusakan media penyimpanan.
- Power Failure atau kegagalan pasokan listrik.
- Kerusakan RAM atau prosesor.

Dampaknya dapat berupa berhentinya proses aplikasi, hilangnya akses terhadap data, atau tidak berfungsinya server.

### 6.2 Software Faults

Software Faults merupakan kesalahan yang berasal dari perangkat lunak, baik karena kesalahan pemrograman maupun pengelolaan sumber daya.

**Contoh:**

- **Bugs:** Kesalahan kode program.
- **Memory Leak:** Penggunaan memori yang terus meningkat tanpa dilepaskan dengan benar.
- **Race Condition:** Kondisi ketika hasil program dipengaruhi oleh urutan eksekusi proses yang berjalan bersamaan.

Penanganannya dapat dilakukan melalui Debugging, pengujian perangkat lunak, Monitoring, dan penerapan mekanisme pemulihan.

### 6.3 Communication Faults

Communication Faults merupakan kesalahan yang terjadi pada proses komunikasi antar-komponen dalam sistem terdistribusi.

**Contoh:**

- Packet Loss atau kehilangan paket data.
- Network Partition atau terputusnya komunikasi antarbagian jaringan.
- Koneksi jaringan yang mengalami gangguan.

Jenis kesalahan ini dapat mengakibatkan keterlambatan respons, kegagalan permintaan, dan ketidaksinkronan data.

## 7. Teknik dan Design Patterns untuk Mencapai Fault Tolerance

Terdapat beberapa teknik yang dapat digunakan untuk meningkatkan kemampuan Fault Tolerance pada sistem terdistribusi.

### 7.1 Redundansi dan Replikasi

**Redundansi** merupakan teknik menyediakan sumber daya atau komponen tambahan sebagai cadangan apabila komponen utama mengalami kegagalan.

Sementara itu, **Replikasi** merupakan proses membuat salinan data, layanan, atau komponen pada beberapa Node.

Tujuan utama teknik ini adalah menghindari _Single Point of Failure_ (SPOF), yaitu kondisi ketika kegagalan satu komponen menyebabkan seluruh sistem berhenti bekerja.

**Contoh penerapan:**

Sebuah aplikasi memiliki tiga server yang menyediakan layanan yang sama. Jika satu server mengalami kerusakan, server lainnya masih dapat menjalankan layanan.

**Keuntungan:**

- Meningkatkan ketersediaan layanan.
- Mengurangi ketergantungan pada satu komponen.
- Menyediakan sumber daya cadangan.
- Mendukung proses pemulihan ketika terjadi kegagalan.

### 7.2 Load Balancing

Load Balancing merupakan teknik mendistribusikan permintaan pengguna ke beberapa Instance aplikasi menggunakan sebuah komponen yang disebut **Load Balancer**.

Tujuannya adalah membagi beban kerja agar tidak seluruh permintaan hanya ditangani oleh satu server.

Beberapa teknologi yang dapat digunakan adalah:

- Nginx.
- HAProxy.

**Contoh penerapan:**

Sebuah aplikasi web awalnya hanya memiliki satu Instance. Ketika jumlah pengguna meningkat, satu Instance tersebut dapat mengalami beban berlebihan.

Dengan Load Balancing, aplikasi dapat dijalankan dalam beberapa Instance. Selanjutnya, Nginx bertugas meneruskan permintaan pengguna ke Instance aplikasi yang tersedia.

**Manfaat Load Balancing:**

1. Membagi beban permintaan ke beberapa Instance.
2. Mengurangi risiko Overload pada satu server.
3. Mendukung Scaling aplikasi.
4. Meningkatkan ketersediaan layanan apabila dikombinasikan dengan mekanisme deteksi dan pengalihan dari Instance yang gagal.

### 7.3 Checkpointing dan Rollback Recovery

Checkpointing merupakan proses menyimpan status atau kondisi sistem secara berkala ke media penyimpanan.

Rollback Recovery merupakan proses mengembalikan sistem ke kondisi Checkpoint sebelumnya ketika terjadi kegagalan.

Kedua teknik ini saling berkaitan karena Checkpoint menyediakan titik pemulihan, sedangkan Rollback digunakan untuk mengembalikan sistem ke titik tersebut.

**Contoh:**

Sebuah aplikasi sedang memproses transaksi dalam jumlah besar. Sistem menyimpan Checkpoint setiap beberapa menit. Ketika terjadi kegagalan, aplikasi dapat melanjutkan proses dari Checkpoint terakhir yang tersimpan, bukan mengulang seluruh proses dari awal.

**Manfaat:**

- Mengurangi kehilangan data.
- Mengurangi waktu pemrosesan ulang.
- Mempercepat proses pemulihan sistem.

### 7.4 Heartbeat dan Failure Detection

Heartbeat merupakan sinyal yang dikirimkan secara berkala antar-komponen untuk menunjukkan bahwa suatu komponen masih aktif.

Failure Detection merupakan proses mendeteksi kegagalan komponen berdasarkan tidak diterimanya sinyal Heartbeat dalam jangka waktu tertentu.

**Cara kerjanya:**

1. Komponen A mengirimkan Heartbeat secara berkala.
2. Komponen B menerima Heartbeat tersebut.
3. Komponen B memantau waktu penerimaan Heartbeat.
4. Jika Heartbeat tidak diterima dalam batas waktu tertentu, komponen A diasumsikan mengalami kegagalan atau tidak responsif.
5. Sistem dapat melakukan tindakan penanganan sesuai mekanisme yang diterapkan.

Pola ini penting untuk membangun sistem terdistribusi yang andal karena memungkinkan deteksi dan penanganan kegagalan secara tepat waktu.

Pada materi ini, terdapat contoh program `check-server.py` untuk melakukan pemeriksaan sederhana terhadap kondisi server.

### 7.5 Retry Pattern

Retry merupakan pola penanganan kegagalan dengan cara mengulangi suatu operasi ketika operasi tersebut gagal dilakukan.

Pola ini cocok digunakan untuk mengatasi gangguan sementara, khususnya ketika aplikasi berkomunikasi dengan layanan eksternal.

Materi memperkenalkan library Python bernama **Tenacity** untuk mengelola proses Retry.

**Contoh implementasi Python:**

```python
from tenacity import (
    retry,
    stop_after_attempt,
    wait_exponential,
    retry_if_exception_type
)
import requests

@retry(
    stop=stop_after_attempt(5),
    wait=wait_exponential(
        multiplier=1,
        min=4,
        max=10
    ),
    retry=retry_if_exception_type(
        requests.exceptions.ConnectionError
    )
)
def make_http_request(url):
    response = requests.get(url)
    response.raise_for_status()
    return response.text

try:
    content = make_http_request("http://localhost:44777")
except Exception as e:
    print(f"Failed after multiple retries: {e}")
```

**Penjelasan:**

- `stop_after_attempt(5)` membatasi percobaan maksimal sebanyak lima kali.
- `wait_exponential()` menerapkan waktu tunggu yang meningkat secara eksponensial, dengan batas minimum empat detik dan maksimum sepuluh detik.
- `retry_if_exception_type()` menentukan jenis kesalahan yang akan menyebabkan pengulangan, yaitu `ConnectionError`.

Dengan demikian, aplikasi tidak langsung gagal ketika koneksi sementara mengalami gangguan.

### 7.6 Circuit Breaker Pattern

Circuit Breaker merupakan pola desain yang digunakan untuk mencegah terjadinya kegagalan berantai (_Cascading Failure_) dalam sistem, khususnya arsitektur Microservices.

Pola ini bekerja seperti pemutus arus listrik yang menghentikan sementara permintaan menuju layanan yang sedang mengalami kegagalan.

Circuit Breaker mempunyai tiga status utama:

**1. CLOSED**

Permintaan diizinkan untuk diteruskan ke layanan. Sistem tetap memantau jumlah kegagalan yang terjadi.

**2. OPEN**

Ketika jumlah kegagalan mencapai batas tertentu, permintaan berikutnya ditolak sementara agar layanan yang bermasalah memiliki waktu untuk pulih.

**3. HALF-OPEN**

Setelah waktu tunggu berakhir, sejumlah permintaan percobaan diizinkan untuk memeriksa apakah layanan telah pulih.

**Alur perpindahan status:**

```text
CLOSED
   |
   | Kegagalan mencapai batas
   v
OPEN
   |
   | Waktu tunggu berakhir
   v
HALF-OPEN
   |
   |-----------------------|
   |                       |
   v                       v
Berhasil                 Gagal
   |                       |
   v                       v
CLOSED                   OPEN
```

**Contoh implementasi Python:**

```python
import pybreaker
import requests

breaker = pybreaker.CircuitBreaker(
    fail_max=4,
    reset_timeout=20
)

@breaker
def make_http_request(url):
    response = requests.get(url)
    response.raise_for_status()
    return response.text

try:
    content = make_http_request("http://localhost:44777")
except Exception as e:
    print(e)
```

**Penjelasan:**

- `fail_max=4` menentukan batas kegagalan sebanyak empat kali.
- `reset_timeout=20` menentukan waktu tunggu 20 detik sebelum Circuit Breaker mencoba menguji kembali layanan.

Library yang digunakan adalah `pybreaker`.

**Perbedaan Retry dan Circuit Breaker:**

| Retry                                      | Circuit Breaker                                          |
| ------------------------------------------ | -------------------------------------------------------- |
| Mengulangi permintaan yang gagal.          | Menghentikan sementara permintaan ke layanan yang gagal. |
| Cocok untuk gangguan sementara.            | Cocok untuk mencegah kegagalan berantai.                 |
| Memiliki batas percobaan dan waktu tunggu. | Memiliki tiga status: Closed, Open, Half-Open.           |

### 7.7 Consensus and Coordination

Consensus merupakan proses ketika beberapa Node dalam sistem terdistribusi menyepakati satu nilai, status, atau urutan operasi meskipun terdapat kegagalan maupun keterlambatan jaringan.

Coordination merupakan praktik mengatur interaksi antar-Node agar seluruh komponen dapat bekerja sama secara efektif dan konsisten.

Consensus sering menjadi salah satu komponen penting dalam Coordination.

**Contoh penerapan:**

1. **Database Leader Election**

   Dalam Cluster Database yang menggunakan Replikasi, diperlukan pemilihan satu Node sebagai Leader untuk menangani operasi penulisan (_Write_). Algoritma konsensus seperti Raft dapat digunakan.

2. **Cloud Storage File Updates**

   Pada layanan penyimpanan Cloud, perubahan file perlu disepakati dan di-Commit oleh mayoritas server sebelum dianggap final. Selanjutnya, perubahan direplikasi ke server lainnya.

3. **Cryptocurrency dan Blockchain**

   Teknologi Blockchain menggunakan mekanisme konsensus untuk melakukan validasi dan persetujuan transaksi.

Kesimpulannya, Consensus membantu menjaga kesepakatan antar-Node, sedangkan Coordination membantu mengatur kerja sama antar-komponen sistem.

## 8. Actor Model untuk Supervisi Proses

Actor Model merupakan model komputasi yang digunakan dalam sistem konkuren dan terdistribusi. Materi perkuliahan memasukkan Actor Model sebagai salah satu pendekatan untuk melakukan supervisi proses.

Secara konseptual, Actor Model menggunakan unit yang disebut _Actor_ untuk menjalankan pekerjaan dan berkomunikasi melalui pengiriman pesan (_Message Passing_).

Dalam penerapan supervisi proses, dikenal pola **Supervisor-Worker**:

- **Supervisor:** Bertugas memantau dan mengawasi proses Worker.
- **Worker:** Bertugas menjalankan pekerjaan tertentu.
- **Failure Handling:** Ketika Worker mengalami kegagalan, Supervisor dapat menjalankan mekanisme penanganan atau memulai ulang proses sesuai kebijakan supervisi.

Pendekatan ini membantu mengisolasi kegagalan agar masalah pada satu proses tidak langsung memengaruhi keseluruhan sistem.

## 9. Implementasi Fault Tolerance pada Berbagai Bahasa Pemrograman

Materi menjelaskan bahwa berbagai bahasa pemrograman memiliki pendekatan yang berbeda dalam menerapkan Fault Tolerance.

| Bahasa | Library / Teknologi                        | Kegunaan                                  |
| ------ | ------------------------------------------ | ----------------------------------------- |
| Erlang | Built-in Actor Model dan Supervisor-Worker | Supervisi proses dan penanganan kegagalan |
| Elixir | Built-in Actor Model dan Supervisor-Worker | Supervisi proses dan penanganan kegagalan |
| Pony   | Actor Model                                | Pemrograman berbasis Actor                |
| Python | Xoscar                                     | Actor Model                               |
| Python | Tenacity                                   | Retry                                     |
| Python | Circuit Breaker / PyBreaker                | Pengelolaan kegagalan layanan             |
| Java   | Apache Pekko                               | Actor Model dan Supervisor-Worker         |
| Java   | Resilience4j                               | Fault Tolerance                           |

Selain itu, pengembang juga dapat mencari library tambahan melalui repositori paket masing-masing bahasa, seperti npm untuk JavaScript dan crates.io untuk Rust.

## 10. Praktik Load Balancing Aplikasi Menggunakan Nginx

Sebagai implementasi praktis Fault Tolerance, materi pendamping memberikan demonstrasi penggunaan aplikasi web Python menggunakan framework Blacksheep, Docker, Docker Compose, dan Nginx.

### 10.1 Komponen yang Digunakan

1. **Blacksheep:** Framework untuk membuat aplikasi web ASGI berbasis Python.
2. **Docker:** Menjalankan aplikasi dan Nginx di dalam Container.
3. **Docker Compose:** Mengelola beberapa Service atau Container.
4. **Nginx:** Bertindak sebagai Reverse Proxy dan Load Balancer.
5. **Dua Instance Aplikasi:** Aplikasi di-Scale menjadi dua Instance.

### 10.2 Konfigurasi Nginx

Nginx dikonfigurasi untuk meneruskan permintaan ke Backend aplikasi melalui konfigurasi `upstream` dan `proxy_pass`.

Contoh konfigurasi `nginx.conf`:

```nginx
events {
    worker_connections 4096;
}

http {
    upstream backend {
        server bs_app:80;
    }

    server {
        listen 80;

        location / {
            proxy_pass http://backend;
        }
    }
}
```

Bagian `upstream` mendefinisikan grup Backend dengan nama `backend`. Nginx kemudian meneruskan permintaan dari lokasi `/` ke grup tersebut melalui `proxy_pass`.

### 10.3 Konfigurasi Docker Compose

File `docker-compose.yml` digunakan untuk mengatur Service aplikasi dan Nginx.

Contoh konfigurasi:

```yaml
services:
  bs_app:
    build: ./blacksheep_lb

  nginx:
    container_name: nginx
    build: ./nginx
    ports:
      - 80:80
    depends_on:
      - bs_app
```

Service `bs_app` membangun aplikasi dari direktori `blacksheep_lb`, sedangkan Service `nginx` membangun Proxy dari direktori `nginx` dan memetakan port 80 Host ke port 80 Container.

### 10.4 Menjalankan Dua Instance Aplikasi

Perintah yang digunakan untuk menjalankan aplikasi dengan dua Instance adalah:

```bash
docker compose up --build -d --scale bs_app=2
```

Keterangan:

- `up`: Menjalankan Service.
- `--build`: Membangun Image sebelum menjalankan Container.
- `-d`: Menjalankan Container di latar belakang.
- `--scale bs_app=2`: Menjalankan dua Instance Service `bs_app`.

Untuk menghentikan dan menghapus Container yang dibuat oleh Compose:

```bash
docker compose down
```

### 10.5 Memeriksa Hasil Load Balancing

Untuk memeriksa Container yang berjalan, gunakan perintah:

```bash
docker ps
```

Materi menunjukkan dua Instance aplikasi, yaitu:

- `load-balancing-bs_app-1`
- `load-balancing-bs_app-2`

Nama awalan dapat mengikuti nama direktori atau proyek Compose.

Aplikasi diakses melalui:

```text
http://localhost
```

Port yang digunakan sekarang adalah port 80 karena Nginx memetakan port `80:80`. Hal ini berbeda dari port pengembangan aplikasi Blacksheep sebelumnya, yaitu `44777`.

Untuk melihat Log Nginx:

```bash
docker logs nginx
```

Materi memperlihatkan permintaan yang diterima oleh kedua Instance melalui Log. Distribusi akses pada contoh tersebut menunjukkan bahwa Nginx meneruskan Request ke Instance aplikasi.

**Inti dari praktik ini:** Aplikasi dijalankan dalam lebih dari satu Instance, kemudian Nginx menjadi pintu masuk yang meneruskan permintaan ke Backend. Dengan demikian, beban tidak hanya ditangani oleh satu proses aplikasi.

Catatan: Praktik tersebut merupakan demonstrasi Load Balancing. Materi tidak menunjukkan konfigurasi Health Check Backend secara eksplisit. Oleh karena itu, keberadaan dua Instance dan Load Balancing tidak otomatis menjamin bahwa Instance yang gagal selalu terdeteksi dan dikeluarkan dari Backend.

## 11. Kesimpulan

Fault Tolerance merupakan kemampuan sistem untuk tetap beroperasi ketika satu atau beberapa komponennya mengalami kegagalan. Kemampuan ini sangat penting dalam sistem terdistribusi dan terdesentralisasi karena sistem terdiri dari banyak komponen yang saling berkomunikasi dan masing-masing memiliki potensi gangguan.

Modul ini membahas jenis Fault berupa Transient, Intermittent, Permanent, dan Byzantine Fault, serta klasifikasi berdasarkan sumbernya, yaitu Hardware Faults, Software Faults, dan Communication Faults.

Untuk meningkatkan ketahanan sistem, beberapa teknik yang dipelajari adalah redundansi dan replikasi, Load Balancing, Checkpointing dan Rollback Recovery, Heartbeat dan Failure Detection, Retry, Circuit Breaker, Consensus dan Coordination, serta Actor Model untuk supervisi proses.

Praktik menggunakan Python, Docker, Docker Compose, dan Nginx memperlihatkan bagaimana aplikasi dapat dijalankan dalam beberapa Instance dan permintaannya diteruskan melalui Load Balancer.

Secara keseluruhan, penerapan Fault Tolerance membantu mengurangi dampak kegagalan, meningkatkan ketersediaan, dan menjaga kontinuitas layanan.

## 12. Referensi Materi

1. Dr. Bambang Purnomosidi D. P., **Fault Tolerance**, Modul 05, Mata Kuliah Sistem Terdistribusi dan Terdesentralisasi, Fakultas Teknologi Informasi, Universitas Teknologi Digital Indonesia.
2. Dr. Bambang Purnomosidi D. P., **Load Balancing Aplikasi Menggunakan Nginx**, materi pendamping Modul 05, Fakultas Teknologi Informasi, Universitas Teknologi Digital Indonesia.
3. Berkas kode praktik `src-05`, khususnya direktori `failure-detection` dan `load-balancing`, yang menyertai materi perkuliahan.
