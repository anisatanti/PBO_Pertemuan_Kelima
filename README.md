# **TUGAS PBO TM 5 (SWING JDBC)**
___
## **_Deskripsi_**
Proyek ini merupakan Tugas Pertemuan Kelima Mata Kuliah Pemrograman Berorientasi Objek. Membuat Aplikasi CRUD pada Netbeans Java yang terhubung dengan Aplikasi basis data PostgreSQL. Dalam proyek ini mengimplementasikan operasi CRUD (Create, Read, Update, Delete) pada database yang berisi tabel DataPaspor. Untuk dapat menjalankan Aplikasi pastikan Aplikasi terhubung ke database menggunakan JDBC, dengan library PostgreSQL.
___
## **Tampilan Antarmuka GUI DataPaspor menggunakan Java Swing**
Pada tampilan ini berisi ID Paspor, Nama, dan Kewarganegaraan (yang diisi menggunakan _JtextField_), Tanggal lahir yang diisi menggunakan _JDataChooser_, serta jenis kelamin (Laki-laki dan Perempuan) yang diisi menggunakan _radioButton_. Terdapat 5 tombol untuk mengoperasikan Gui Data Paspor menggunakan _JButton_ yakni btnInsert, btnUpdate, btnDelete, btnClear, dan btnExit. Dalam gui ini juga menampilkan tabel sebagai hasil dari inputan yang diberikan menggunakan _JTable_. 
___
### **Deskripsi Program**
-	Dalam program ini diawali dengan mendeklarasikan beberapa import untuk menangani koneksi database, operasi SQL, dan interaksi dengan pengguna di Java. Inisialisasi nama database yang akan digunakan beserta password PostgreSQL.
-	Method koneksi() untuk menampilkan koneksi database dengan gui apakah berhasil atau error.
-	Membuat method tampil dengan perintah sql “SELECT * FROM DataPaspor;” untuk menampilkan data yang di inputkan.
-	Public FramePaspor merupakan constructor dari kelas FramePaspor berisi method initComponents() untuk menginisialisasi komponen GUI, method koneksi yang merupakan method untuk mengatur koneksi ke database, dan method tampil untuk menampilkan data ke dalam tabel dari database.

#### **btnInsertActionPerformed**
berfungsi untuk menambahkan data ke dalam database. Berisi perintah sql "INSERT INTO DataPaspor (id_Paspor, nama_pemilik, kewarganegaraan, tanggal_lahir, jenis_kelamin) VALUES (?, ?, ?, ?, ?)". Pastikan dalam menginput data semua data tidak ada yang kosong. Jika data ada yang belum terisi maka akan menampilkan peringatan untuk melengkapi data yang belum terisi.
    
#### **btnUpdateActionPerformed**
berfungsi untuk mengupdate data yang telah di input. Berisi perintah sql "UPDATE DataPaspor SET nama_pemilik=?, kewarganegaraan=?, tanggal_lahir=?, jenis_kelamin=? WHERE id_Paspor=?". Pastikan dalam mengupdate data semua data tidak ada yang kosong. Jika data ada yang belum terisi maka akan menampilkan peringatan untuk melengkapi data yang belum terisi.

#### **btnDeleteActionPerformed**
berfungsi untuk menghapus data dalam tabel database. Berisi perintah sql “DELETE FROM DataPaspor WHERE id_Paspor = ?”. MEnghapus data dilakukan dengan menginputkan IDPaspor yang dituju kemudia klik button Delete dan data berhasil dihapus.
       
#### **btnClearActionPerformed**
berfungsi menghapus inputan yang dimasukkan dalam Frame GUI secara otomatis.
       
#### **tblPasporMouseClicked**
berfungsi untuk menampilkan data dalam bentuk tabel dan memungkinkan pengguna untuk mengeditnya
        
#### **btnExitActionPerformed**
berfungsi untuk menutup atau keluar dari aplikasi ketika pengguna mengklik tombol tersebut
___
### **Kelas DbUtils**
Kelas DbUtils dibuat untuk menyederhanakan pengolahan data dari ResultSet agar bisa langsung digunakan dalam komponen GUI, khususnya JTable. Fungsinya adalah mengonversi data hasil query SQL (yang ada dalam ResultSet) menjadi TableModel, yang kemudian dapat digunakan untuk menampilkan data di JTable dengan cepat dan efisien.
