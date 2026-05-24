Sistem Manajemen Kamar Hotel Berbasis Nomor Kamar



didasarkan pada kesederhanaan logikanya yang sangat mudah dibayangkan dalam kehidupan nyata. Nomor kamar hotel secara alami sudah berupa angka integer terurut (seperti 202,105,310) yang sangat ideal digunakan sebagai kunci pengurutan (key) tanpa perlu konversi yang rumit,sehingga aturan dasar BST—di mana angka yang lebih kecil belok ke kiri dan angka yang lebih besar belok ke kanan—bisa langsung dipraktikkan dengan jelas.




Source Code

Input


![image alt](https://github.com/muhammaddarma2006-coder/PSD-TAP5-2515061003/blob/f96e80a05e60495a7a2d33cc6b01af34f5a09b96/Screenshot%20(2492).png)

[Gambar 1] sebuah kontainer atau kotak memori yang dibagi menjadi tiga bagian utama:  
Data Identitas (Key): Baris self.nomor_kamar = nomor_kamar berfungsi menyimpan angka nomor kamar. Angka inilah yang menjadi acuan utama bagi algoritma BST untuk menentukan arah navigasi data.
Data Pendukung (Value): Baris self.tipe_kamar dan self.status berfungsi menyimpan informasi detail logistik dari kamar tersebut (seperti tipe Deluxe dan status Kosong). Data ini hanya bersifat membonceng atau disimpan di dalam nomor kamar tersebut.
Navigasi/Penunjuk (Pointer): Baris self.left = None dan self.right = None adalah kaki atau tangan dari node tersebut. Bagian ini berfungsi sebagai percabangan untuk mengikat atau menghubungkan node kamar ini dengan node-node kamar lainnya di tingkat bawahnya (kiri untuk nomor lebih kecil, kanan untuk nomor lebih besar).

![image alt](https://github.com/muhammaddarma2006-coder/PSD-TAP5-2515061003/blob/36caf418d8ff644eaa9fed91d2101c76d20aa84f/Screenshot%20(2493).png)

[Gambar 2] Fungsi def _insert_kamar(self, root, nomor_kamar, tipe_kamar, status): adalah fungsi internal rekursif yang menjadi otak utama dari aturan penempatan BST.
setiap kali mengetikkan data kamar baru, data tersebut akan berjalan menyusuri pohon dan otomatis terpasang di lokasi yang tepat sesuai aturan baku Binary Search Tree.


![image alt](https://github.com/muhammaddarma2006-coder/PSD-TAP5-2515061003/blob/36caf418d8ff644eaa9fed91d2101c76d20aa84f/Screenshot%20(2494).png)

[Gambar 3]Fungsi def cari_kamar(self, nomor_kamar): adalah fungsi yang akan dipanggil ketika kamu memilih Menu 2 di terminal.
Fungsi def _search_kamar(self, root, nomor_kamar): adalah fungsi internal yang bekerja secara rekursif (memanggil dirinya sendiri) untuk menyusuri ranting-ranting pohon.


![image alt](https://github.com/muhammaddarma2006-coder/PSD-TAP5-2515061003/blob/30735dc8d2cfb4b727f479078f2f2f96cff04325/Screenshot%20(2496).png)

[Gambar 4]Fungsi _inorder_display adalah fungsi internal rekursif yang menggunakan metode Inorder Traversal. Fungsi ini memiliki keunikan karena secara otomatis bisa mengurutkan data dari nomor kamar terkecil hingga terbesar tanpa perlu algoritma sorting tambahan. Fungsi def main(): di bagian bawah bertindak sebagai pusat kendali interaktif bagi pengguna saat program dijalankan. Di dalam fungsi ini terdapat perulangan tanpa batas (while True) yang terus-menerus menampilkan 4 pilihan menu utama (Daftar Kamar, Cari Kamar, Tampilkan Semua, dan Keluar).


![image alt](https://github.com/muhammaddarma2006-coder/PSD-TAP5-2515061003/blob/30735dc8d2cfb4b727f479078f2f2f96cff04325/Screenshot%20(2497).png)

[Gambar 5] Bagian ini memastikan bahwa semua fitur hebat yang sudah dibangun di kelas SistemHotelBST (mulai dari membuat node, melakukan insert data secara rekursif, melacak kamar, hingga mengurutkan nomor otomatis) dapat diakses dengan mudah, interaktif, dan aman dari crash oleh pengguna melalui antarmuka terminal.


![image alt](https://github.com/muhammaddarma2006-coder/PSD-TAP5-2515061003/blob/30735dc8d2cfb4b727f479078f2f2f96cff04325/Screenshot%20(2498).png)

[Gambar 6] Bagian gambar input ini ada menu pilihan, penanganan error untuk input menu, serta struktur standar Python untuk mengeksekusi program.


Output

![image alt](https://github.com/muhammaddarma2006-coder/PSD-TAP5-2515061003/blob/9906969a67454d1866445b3230db7e90db410bb1/Screenshot%20(2499).png)

[Gambar 1] output tersebut menampilkan tampilan menu utama interaktif ketika program pertama kali dijalankan di terminal, diikuti dengan simulasi proses Menu 1 (Mendaftarkan Kamar Baru) untuk kamar pertama kali. Setelah masukan Menu 1, program secara berurutan meminta pengguna mengisi tiga data penting yang akan disimpan ke dalam memori.


![image alt](https://github.com/muhammaddarma2006-coder/PSD-TAP5-2515061003/blob/9906969a67454d1866445b3230db7e90db410bb1/Screenshot%20(2500).png)

[Gambar 2]Di Terminal: disitu milih menu 2 lalu mengetikkan nomor kamar yang dicari: 310.

Di Latar Belakang: Angka 310 ditangkap oleh program dan dikirim ke fungsi pelacak (_search_kamar(self.root, 310)).

Langkah 1 (Mengecek Root): Komputer mendarat di Kamar 202. Komputer bertanya: "Apakah 310 sama dengan 202?" Jawabannya Tidak.
Langkah 2 (Menentukan Arah): Komputer membandingkan nilainya: "Apakah 310 lebih kecil atau lebih besar dari 202?". Karena 310 lebih besar (> 202), sesuai aturan emas BST, komputer memutuskan untuk belok ke cabang KANAN.
Langkah 3 (Menabrak Jalan Buntu): Komputer melihat ke cabang kanan Kamar 202. Karena kamu tidak memasukkan Kamar 310 (cabang kanan kosong atau bernilai None), komputer langsung menabrak jalan buntu. komputer hanya melakukan satu kali perbandingan di Root (202), lalu saat mau belok kanan ternyata kosong, dia langsung menyerah dan langsung memberikan informasi bahwa Kamar 310 tidak ditemukan.

![image alt](https://github.com/muhammaddarma2006-coder/PSD-TAP5-2515061003/blob/9906969a67454d1866445b3230db7e90db410bb1/Screenshot%20(2501).png)

[Gambar 3] memilih menu 3, fungsi Inorder Traversal (_inorder_display) berjalan menyisir dari cabang paling kiri ke kanan ({Kiri} > {Root} > {Kanan}).
Hasilnya, meskipun kamu memasukkan data secara acak (202, lalu 105, baru 310), terminal menampilkan tabel data yang otomatis terurut sempurna dari angka terkecil

memilih menu 4. Perintah break di dalam kode langsung memotong perulangan menu, memunculkan pesan penutup "Program selesai. Terima kasih!", dan menutup aplikasi dengan bersih dan aman.



ini ada link video demonstrasinya :







