# smart-waste-classification-kelompok-1
Project Monitoring kepenuhan TPS menggunakan Yolov5, IoT &amp; Mobile App

Kelompok 1:
- Nyataku Ibnu Rosada (2310614021)
- Natasya Anggraeny (2319614020)
- Robby Saeful Alamin (2310614071)

**Deskripsi Projek**
Konsep solusi yang kami usulkan adalah sistem pendeteksi kepenuhan sampah berbasis Artificial Intelligence menggunakan teknologi Object Detection secara real-time dan juga menggunakan bantuan IoT melalui kamera ESP Cam. Sistem ini dirancang untuk membantu monitoring tempat sampah secara otomatis  untuk mendukung lingkungan yang lebih bersih dan smart environment dan juga untuk meningkatkan efisiensi pengangkutan sampah di tps.

**instalasi/run**
Untuk Cara kerja dari sistem yang kami buat adalah, kamera yang sudah ditanam AI mendeteksi apakah tempat sampah penuh atau tidak, semua data itu akan terkirim ke database lalu terkirim ke aplikasi mobile. namun, apabila tempat sampah terdeteksi penuh maka akan memunculkan foto hasil tangkapan kamera di aplikasi mobile. untuk cara lihat foto nya masuk kedalam aplikasi terlebih dahulu cari tempat sampah yang sudah ada icon tempat sampah penuh nya di maps aplikasi lalu klik icon tempat sampah itu maka muncul foto tempat sampah penuh itu. untuk keberlanjutan sistem ini dapat dibuat sistem jalur armada pengangkutan yang efisien contohnya tempat sampah A jarak nya 3km dan tempat sampah B jarak nya 1km maka sistem akan otomatis merekomendasikan jalur ke yang terdekat terlebih dahulu.

**hasil performa model**
Berdasarkan hasil pelatihan menggunakan arsitektur YOLOv5m, model menunjukkan performa yang cukup baik dalam mendeteksi objek sampah. Nilai box loss dan objectness loss mengalami penurunan selama proses training, yang menandakan bahwa model mampu mempelajari lokasi dan keberadaan objek dengan lebih akurat.
Selain itu, nilai precision meningkat hingga sekitar 77%, yang berarti sebagian besar prediksi model sudah sesuai dengan objek sebenarnya. Nilai recall mencapai sekitar 60%+, sehingga model mampu mendeteksi sebagian besar objek pada dataset.
Hasil evaluasi menunjukkan nilai mAP@0.5 mencapai sekitar 68%, yang menandakan kemampuan deteksi objek sudah cukup baik untuk digunakan pada sistem monitoring sampah. Namun, pada epoch akhir terlihat adanya sedikit peningkatan pada validation loss yang menunjukkan indikasi overfitting ringan. Hal ini disebabkan oleh variasi bentuk sampah yang kompleks dan kondisi objek yang saling bertumpuk.
Secara keseluruhan, model yang dikembangkan telah berhasil melakukan deteksi sampah dengan performa yang cukup baik dan dapat digunakan sebagai dasar implementasi sistem monitoring tempat sampah berbasis AI. (analisis ini dibantu oleh AI)

**Perbandingan Arsitektur YOLOv5**
Didalam sistem/training ini dilakukan beberapa kali training yang bertujuan untuk membandingkan arsitektur yolov5 dan juga untuk menentukan model mana yang paling cocok dengan projek ini dan spesifikasi kapasitas device ataupun yang lainnya. Perbandingan dilakukan berdasarkan ukuran model, kecepatan proses, kebutuhan komputasi, dan tingkat akurasi. berdasarkan hasil pengujian kami, kami memustukan untuk menggunakan yolov5l karena tingkat akurasi nya lebih tinggi dibandingkan dengan yolov5s dan yolov5m, model yolo ini dapat mendeteksi objek dengan lebih stabil. meskipun YOLOv5s dan YOLOv5m memiliki proses train yang lebih cepat dan lebih ringan, tingkat akurasinya masih di bawah YOLOv5l. Sementara itu, YOLOv5x memang lebih bagus dibandingkan dengan ke 3 model lainnya itu, namun yolov5x membutuhkan gpu dan memori lebih besar sehingga kurang cocok dengan sumber daya yang kita miliki. Oleh karena itu, yolov5l dipilih sebagai arsitektur model karena tidak terlalu rendah spek nya dan juga tidak terlalu tinggi spek nya sesuai dengan device yang ada. Berikut tabel yang dihasilkan oleh AI

Model	  Ukuran  Model	 Kecepatan Akurasi	Kelebihan	                                          Kekurangan

YOLOv5s	Kecil	  Sangat Cepat	   Sedang	  Ringan dan cocok untuk perangkat rendah spesifikasi	Akurasi lebih rendah

YOLOv5m	Sedang	Cepat	 Baik	     Seimbang antara kecepatan dan akurasi	                      Membutuhkan GPU menengah

YOLOv5l	Besar	  Lebih  Lambat	   Sangat   Baik	Akurasi lebih tinggi	                        Membutuhkan memori besar

YOLOv5x	Sangat  Besar	 Lambat	   Sangat   Tinggi	Performa deteksi terbaik	                  Sangat berat untuk perangkat biasa
