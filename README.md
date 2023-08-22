# Pre-Test Bootcamp DevOps

## knowledge base

1. Apa yang anda ketahui tentang DevOps?
2. Apa yang anda ketahui tentang Infrastructure?
3. Apa yang anda ketahui tentang server, sebutkan implementasi berserta contohnya?
4. Mengapa server dibutuhkan dalam pengembangan/development suatu software?
5. Apa yang anda ketahui mengenai Virtualisasi dan Container?
6. Mengapa teknology container saat ini sangat populer?
7. Apa yang anda ketahui tentang Orchestration Container System?

Cara pengerjaan, silahkan update file ini tulis jawabanya di bawah ini

## Jawaban knowledge base

1. DevOps yaitu sebuah prinsip untuk mengotomatisikan serta mengintegrasi proses antara Developer dan Operational. Tujuan DevOps antara lain menjaga stabilitas dan keandalan sistem, mempercepat waktu peluncuran produk, dan meningkatkan mean time to recovery (MTTR).
2. Infrastructure dalam konteks Teknologi Informasi dan Sistem Komputer merupakan kerangka dasar atau pondasi yang mendukung operasi dan fungsionalitas sistem IT. Juga merupakan kombinasi dari hardware, software, network, dan sumber daya lain yang diperlukan untuk menjalankan aplikasi, layanan, dan operasi teknologi informasi dalam suatu organisasi.
3. Server merupakan hardware khusus yang dirancang untuk memberikan layanan, sumber daya, atau data kepada komputer  yang dikenal sebagai klien atau jaringan. Server berperan sebagai pusat data atau sumber data yang dapat diakses oleh pengguna atau aplikasi lain.
    - Web Server
      - Web server digunakan untuk menyimpan dan mengirimkan halaman web kepada user melalui internet. Contohnya Apache HTP Server, Nginx, dll.
    - Database Server
      - Database server digunakan untuk menyimpan, mengelola, dan mengambil data dari basis data. Contohnya MySQL, PostgreSQL, Microsoft SQL Server, Oracle Database.
    - Application Server
      - Application server digunakan untuk menjalankan aplikasi bisnis dan menyediakan layanan seperti pemrosesan transaksi dan komunikasi antar aplikasi. Contohnya Apache Tomcat, Microsoft.NET Application Server.
4. Karena dalam pengembangan software diperlukan sebagai infrastruktur yang mendukung pengujian, kolaborasi tim, dan pengiriman aplikasi.
5. Virtualisasi dan Container merupakan dua konsep penting dalam dunia Cloud Computing yang memungkinkan pengelolaan dan penggunaan sumber daya Cloud dengan lebih efisien.
    - Virtualisasi
      - Merupakan teknologi yang memungkinkan satu fisik server untuk menjalankan beberapa mesin virtual (VM) atau sistem operasi yang terisolasi secara bersamaan. Seperti Contohnya Oracle VirtualBox, dan VMware vSphere/ESXi.
    - Container
      - Merupakan teknologi yang memungkinkan aplikasi dan semua dependensinya dikemas bersama dalam unit yang disebut Container.  Container ini berjalan di atas sistem operasi host yang sama, tetapi terisolasi satu sama lain. Seperti Contohnya Docker, Kubernetes, dan Podman.
6. Karena memiliki efesiensi sumber daya yang tinggi, memastikan portabilitas lintas platform, penyediaan yang cepat, serta kemampuannya untuk mengelola aplikasi dan layanan secara skalabel. 
7. Orchestration Container System mengotomatisasi deployment, management, scalling, dan jaringan kontainer. Orchestration Container digunakan untuk:
    - Provisioning and deployment
    - Configuration and scheduling
    - Resource allocation
    - Container availability
    - Load balancing and traffic routing 
    - Monitoring container health

## Task 1 (Virtualization)

- Buatlah sebuah VM dengan kententuan
  - username: `<github_user>` contoh `dimasm93`
  - hostname: `<email_without_at>` contoh `dimas.tabeldata.com`
  - OS: `ubuntu-20.04` atau `centos-7`
- Install webserver `nginx`
- Buatlah web profile temen-temen kemudian deploy ke webserver nginx tersebut yang telah di deploy
  
(kirimkan hasil screenshotnya simpan dalam folder `screenshot` dengan nama `task1.png`)

## Task 2 (Container)

Jika saya memiliki architecture seperti berikut:

![container-apps](docs/images/01-container.png)

Dimana berikut adalah configurasi docker image:

1. Backend container
  - image: `dimmaryanto93/udemy-springboot-app:latest`
  - port: `8080`
  - env: 
    - `DATABASE_HOST`: `<ip-domain-db>`
    - `DATABASE_PORT`: `5432` 
    - `DATABASE_NAME`: `<db-name>`
    - `DATABASE_PASSWORD`: `<db-password>`
    - `APPLICATION_PORT`: `8080`
  need:
    - Database PostgreSQL v14.2
2. Frontend container
  - image: `dimmaryanto93/udemy-angular-app:latest`
  - port: `80`
  - env:
    - `APPLICATION_PORT`: `80`
    - `NGINX_ROOT_DOCUMENT`: `/var/www/html`
    - `BACKEND_HOST`: `<ip-backend-apps>`
    - `BACKEND_PORT`: `<port-backend-apps>`
    - `BACKEND_CONTEXT_PATH`: `/`
  - need:
    - Backend container

Silahkan buat docker-compose filenya, kemudian simpan dalam folder `tasks` dengan nama `docker-compose.yaml`

