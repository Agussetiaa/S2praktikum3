# BASISDATA

### Restrict and Cascade
# Praktikum 3
#### 1. Lakukan penambahan data pada tabel mahasiswa dengan mengisi kd_ds yang belum ada pada data dosen.
#### 2. Hapus satu record dat pada tabel dosen yang telah dirjuk pada tabel mahasiswa.
#### 3. Ubah mode menjadi ON UPDATE CASCADE ON DELETE RESTRICT.
#### 4. Lakukan perubahan data pada tabel dosen (kd_ds).
#### 5. Lakukan penghapusan data pada tabel dosen,
#### 6. Ubah mode menjadi ON UPDATE CASCADE ON DELETE SET NULL
#### 7. Lakukan penghapusan data pada tabel dosen.

Langkah Dan Perintah Tugas praktikum.
1. UPDATE mahasiswa SET kd_ds = ‘kd01’ WHERE nim = ‘11223344’;
![image](https://github.com/Agussetiaa/S2praktikum3/assets/115542822/4046cb64-377e-4cdd-acce-21748fba2e68)
2. UPDATE mahasiswa SET kd_ds = NULL WHERE nim = ‘11223344’;
![image](https://github.com/Agussetiaa/S2praktikum3/assets/115542822/d73f8b26-d5cf-448d-8d71-522beb3f888b)
3. ALTER TABLE  mahasiswa ADD CONSTRAINT FK_mhs FOREIGN KEY (kd_ds) REFERENCE dosen(kd_ds) ON UPDATE CASCADE ON DELETE RESTRICT;
![image](https://github.com/Agussetiaa/S2praktikum3/assets/115542822/f7b9b9e1-9471-4c4e-b6e8-7bb4a8420724)
4. UPDATE  dosen SET kd_ds =’kd02’ WHERE kd_ds =’kd01’;
![image](https://github.com/Agussetiaa/S2praktikum3/assets/115542822/967764a4-2328-4c8c-8753-881030999338)
5. DELETE FROM dosen WHERE kd_ds =’kd02’;
![image](https://github.com/Agussetiaa/S2praktikum3/assets/115542822/33dd196f-98ef-4a4f-be04-2e90da914256)
6. ALTER TABLE mahasiswa ADD CONSTRAINT FK_mhs FOREIGN KEY (kd_ds) REFERENCE dosen(kd_ds) ON UPDATE CASCADE ON DELETE SET NULL;
![image](https://github.com/Agussetiaa/S2praktikum3/assets/115542822/f169e8d4-73df-4650-ad9f-13053e61fd5d)
7. DELETE FROM dosen WHERE kd_ds =’kd02’;
![image](https://github.com/Agussetiaa/S2praktikum3/assets/115542822/5023ea0c-eb2b-4129-b1b1-3b1463a8de23)

Evaluasi dan pertanyaan.
1. Apa bedanya pengguna RESTRICT dan CASCADE.?
Penggunaan RESTRICT dan CASCADE adalah dua jenis aturan referential integrity (keutuhan referensial) yang dapat diterapkan pada kunci asing (foreign key) di basis data relasional. 
RESTRICT berarti bahwa ketika ada sebuah baris data di tabel induk (parent table) yang ingin dihapus atau diubah, maka sistem basis data akan memeriksa apakah ada baris data di tabel anak (child table) yang masih merujuk ke baris data tersebut. Jika ada, maka sistem basis data akan mencegah penghapusan atau perubahan data pada baris data di tabel induk yang berdampak pada baris data di tabel anak yang masih merujuk ke baris data tersebut.
Sementara itu, CASCADE adalah sebuah baris data di tabel induk dihapus atau diubah, maka sistem basis data akan secara otomatis menghapus atau mengubah baris data di tabel anak yang merujuk ke baris data yang dihapus atau diubah tersebut.
2. Berikan kesimpulan 
RESTRICT dan CASCADE adalah aturan refential intrgrity Yang dapat diterapkan pada kunci asing yang basis data relasional. RESTRICT mencegah penghapusan atau perubahan data pada tabel induk yang berdampak pada tabel anak yang masih merujuk ke data yang di hapus atau di ubah. Sementara CASCADE dengan secara otomatis menghapus atau mengubah data pada tabel anak yang merujuk ke data yang di apus atau di ubah pada tabel induk. Kedua aturan tersebut memiliki kelebihan dan kekurangan msing-masing dan harus dipilih secara bijak sesuai dengan kebutuhan dan konteks penggunaannya agar dapat memastikan keutuhan data didalam system basis data


