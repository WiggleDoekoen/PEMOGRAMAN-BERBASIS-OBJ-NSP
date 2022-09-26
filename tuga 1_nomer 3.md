Nama  Wigi Januar Rahman
Nim   20210040092
Kelas TI21E
JDK 19: Fitur-fitur baru di Java 19

Sekarang tersedia untuk penggunaan produksi, Java 19 memiliki fitur konkurensi terstruktur, utas virtual, pencocokan pola untuk ekspresi sakelar, API vektor, dan port Linux/RISC-V.
Java Development Kit 19, rilis standar Java non-LTS (dukungan jangka panjang), tiba hari ini sebagai rilis produksi. Tujuh fitur menargetkan rilis termasuk konkurensi terstruktur, pola rekaman, pratinjau fungsi asing dan API memori, dan dukungan untuk arsitektur set instruksi Linux/RISC-V open source (ISA). Semua fitur kecuali kemampuan Linux/RISC-V sedang dalam fase pratinjau atau inkubator. JDK 19 mengikuti kedatangan JDK 18 pada 22 Maret . Standard Java telah berada pada irama rilis enam bulan selama lima tahun, dengan JDK 19 menjadi rilis enam bulan kesepuluh. JDK 19 tersedia di oracle.com . Rilis produksi mengikuti dua kandidat rilis dan dua fase rampdown, sejak Juni. Fitur JDK 19 meliputi:
•	Konkurensi terstruktur , dalam fase inkubator, dimaksudkan untuk menyederhanakan pemrograman multithread melalui API konkurensi terstruktur. Konkurensi ini memperlakukan beberapa tugas yang berjalan di utas yang berbeda sebagai satu unit kerja, untuk merampingkan penanganan dan pembatalan kesalahan. Keandalan dan observabilitas ditingkatkan. Fitur ini berasal dari Project Loom , yang memperkenalkan model konkurensi ringan baru.
•	Pratinjau pola rekaman , untuk mendekonstruksi nilai rekaman. Pola rekaman dan pola tipe dapat disarangkan untuk mengaktifkan bentuk navigasi dan pemrosesan data yang deklaratif, kuat, dan dapat disusun. Sasaran proposal mencakup perluasan pencocokan pola untuk mengekspresikan kueri data yang lebih canggih dan dapat dikomposisi tanpa mengubah sintaks atau semantik pola tipe. Proposal ini dibuat berdasarkan pencocokan pola untuk instanceof, yang dikirimkan dalam JDK 16  pada Maret 2021. Rencana di masa mendatang mungkin meminta agar pola rekaman diperluas dengan kemampuan seperti pola dan pola larik vararg. Pola rekaman adalah bagian dari Project Amber , upaya untuk mengeksplorasi dan menginkubasi fitur Java yang lebih kecil dan berorientasi pada produktivitas.
•	Pratinjau fungsi asing dan API memori , yang akan memperkenalkan API di mana program Java dapat beroperasi dengan kode dan data di luar runtime Java. Dengan menjalankan fungsi asing secara efisien (yaitu, kode di luar JVM) dan mengakses memori asing dengan aman (yaitu, memori yang tidak dikelola oleh JVM), API memungkinkan program Java untuk memanggil pustaka asli dan memproses data asli tanpa bahaya dan kerapuhan Java Native Antarmuka (JNI). Fungsi asing dan API memori menggabungkan dua API inkubasi sebelumnya: API akses memori asing dan API tautan asing. Fungsi asing dan API memori sebelumnya diinkubasi di JDK 17 dan diinkubasi ulang di JDK 18 . Tujuan proposal mencakup kemudahan penggunaan, kinerja, umum, dan keamanan.
•	Pratinjau utas virtual , yang merupakan utas ringan yang secara dramatis mengurangi upaya penulisan, pemeliharaan, dan pengamatan throughput tinggi, aplikasi bersamaan. Sasaran termasuk mengaktifkan aplikasi server yang ditulis dalam gaya thread-per-request sederhana untuk diskalakan dengan pemanfaatan perangkat keras yang hampir optimal, memungkinkan kode yang ada yang menggunakanjava.langThread API untuk mengadopsi utas virtual dengan perubahan minimal, dan mengaktifkan pemecahan masalah, debugging, dan pembuatan profil utas virtual dengan alat JDK yang ada. Proposal ini bukan bertujuan untuk mengubah model konkurensi dasar di Java atau menawarkan konstruksi paralelisme data baru dalam bahasa Java atau pustaka Java. Juga bukan tujuan untuk menghapus implementasi tradisional dari utas atau memigrasikan aplikasi yang ada secara diam-diam untuk menggunakan utas virtual. Fitur ini juga merupakan bagian dari Project Loom .
•	Pratinjau ketiga pencocokan pola untuk ekspresi dan pernyataan beralih , memperluas pencocokan pola ke switch, untuk memungkinkan ekspresi diuji terhadap sejumlah pola, masing-masing dengan tindakan tertentu, sehingga kueri berorientasi data yang kompleks dapat diekspresikan secara ringkas dan aman. Kemampuan ini sebelumnya telah dipratinjau di JDK 17 dan JDK 18. Pratinjau ketiga akan menambahkan penyempurnaan termasuk penggantian pola yang dijaga dengan whenklausa dalam switchblok. Juga, semantik runtime dari sakelar pola ketika nilai ekspresi pemilih adalah nol lebih selaras dengan switchsemantik warisan. Tujuan rencana tersebut termasuk memperluas ekspresi dan penerapan dariswitchekspresi dan pernyataan dengan membiarkan pola muncul dalam label kasus. Tujuan lainnya termasuk memungkinkan pengembang untuk melonggarkan permusuhan nol historis switchsaat diinginkan, meningkatkan keamanan switchpernyataan dan memastikan bahwa switchekspresi dan pernyataan yang ada terus dikompilasi tanpa perubahan dan dieksekusi dengan semantik yang identik. Harapannya adalah untuk akhirnya mendukung pencocokan pola di seluruh Jawa, menambahkannya ke tempat-tempat di mana ekspresi digunakan. Fitur ini juga merupakan bagian dari proyek Amber.
•	Inkubasi keempat dari API vektor yang akan mengekspresikan komputasi vektor yang dikompilasi secara andal saat runtime ke instruksi vektor yang optimal pada arsitektur CPU yang didukung, sehingga mencapai kinerja yang lebih unggul daripada komputasi skalar yang setara. Pengembang yang menggunakan API memperoleh cara untuk menulis algoritme vektor kompleks di Java, menggunakan vektorisasi otomatis HotSpot tetapi dengan model pengguna yang membuat vektorisasi lebih dapat diprediksi dan kuat. API vektor sebelumnya telah diinkubasi ke dalam JDK 16, JDK 17, dan JDK 19.
Penyempurnaan pada API yang diusulkan untuk JDK 19 mencakup peningkatan untuk memuat dan menyimpan vektor ke dan dariMemorySegments, seperti yang ditentukan oleh pratinjau Foreign Function dan Memory API. JDK 19 juga akan menambahkan dua operasi vektor lintas jalur, kompres dan ekspansi, bersama dengan operasi kompres topeng vektor komplementer. Operasi vektor kompres memetakan jalur dari vektor sumber, yang dipilih oleh topeng, ke vektor tujuan dalam urutan jalur, sedangkan operasi perluasan melakukan kebalikannya. Operasi kompres berguna dalam memfilter hasil kueri.
Sebagai tambahan lain untuk API vektor, operasi lajur integral bitwise akan diperluas, termasuk operasi seperti menghitung jumlah satu bit, membalikkan urutan bit, dan mengompresi dan memperluas bit. Sasaran API termasuk menjadi jelas dan ringkas, platform-agnostik, memiliki runtime yang andal dan kinerja kompilasi pada arsitektur x64 dan AArch64, dan memungkinkan degradasi "anggun", untuk situasi di mana komputasi vektor tidak dapat sepenuhnya diekspresikan saat runtime sebagai urutan operasi vektor. API vektor berasal dari Project Panama, yang bertujuan untuk memungkinkan komunikasi yang lebih sederhana antara kode asli dan JVM.
•	Dengan port Linux/RISC-V , Java akan mendapatkan dukungan untuk set instruksi perangkat keras yang sudah didukung oleh berbagai rantai alat bahasa. RISC-V sebenarnya adalah keluarga ISA terkait. Port Linux/RISC-V hanya akan mendukung konfigurasi RV64GV dari RISC-V, ISA 64-bit tujuan umum yang menyertakan instruksi vektor. Pengembang Java dapat mempertimbangkan konfigurasi RISC-V lainnya di masa mendatang.