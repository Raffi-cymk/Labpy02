# Labpy02
# Program Pemesanan Tiket Bioskop



Penjelasan:
Berikut adalah penjelasan lengkap dari program Pemesanan Tiket Bioskop:

1. Fungsi hitung_harga_tiket(tipe_tiket, kartu_member)

Fungsi ini bertugas untuk menghitung total harga tiket berdasarkan jenis tiket yang dipilih oleh pengguna, dan apakah pengguna memiliki kartu member atau tidak.

Penjelasan fungsi:

Parameter tipe_tiket: Menerima input apakah pengguna memilih tiket 'reguler' atau 'vip'.

Jika tipe tiket adalah 'reguler', maka harga tiket yang digunakan adalah Rp 50.000.

Jika tipe tiket adalah 'vip', maka harga tiket yang digunakan adalah Rp 100.000.


Parameter kartu_member: Menerima input apakah pengguna memiliki kartu member. Jika pengguna memiliki kartu member, maka ia akan mendapatkan diskon sebesar 20% (atau 80% dari harga asli).

Jika kartu_member bernilai True, harga tiket akan dikalikan dengan 0.8 untuk menerapkan diskon.

Jika kartu_member bernilai False, harga tiket tetap sesuai dengan harga normal.



Logika fungsi:

Pertama, program mengecek apakah tipe tiket adalah 'reguler' atau 'vip' dengan operator ternary, yaitu:

harga_tiket = harga_reguler if tipe_tiket == 'reguler' else harga_vip

Python code ↑

Jika tipe_tiket adalah 'reguler', maka harga_tiket akan menjadi Rp 50.000, sebaliknya jika 'vip', maka harga_tiket adalah Rp 100.000.

Kemudian program mengecek apakah pengguna memiliki kartu member:

total_harga = harga_tiket * 0.8 if kartu_member else harga_tiket

Python code ↑

Jika kartu_member bernilai True, maka harga tiket akan dikalikan 0.8 untuk menerapkan diskon. Jika tidak, harga tetap.


2. Input Data Pengguna

Bagian ini bertugas untuk meminta data dari pengguna:

nama_user: Mengambil input nama pengguna.

tipe_tiket: Meminta pengguna untuk memilih antara tiket 'reguler' atau 'vip', kemudian input ini diubah ke huruf kecil menggunakan .lower() agar lebih mudah diproses.

kartu_member: Menanyakan apakah pengguna memiliki kartu member. Input ini diubah menjadi boolean (True jika pengguna menjawab 'yes', dan False jika tidak).


3. Memanggil Fungsi hitung_harga_tiket

Setelah data input diperoleh, program memanggil fungsi hitung_harga_tiket dengan parameter tipe_tiket dan kartu_member. Hasil dari perhitungan ini disimpan dalam variabel total_harga.

4. Menampilkan Output

Program menampilkan hasil sebagai berikut:

Nama: Menampilkan nama pengguna.

Tipe Tiket: Menampilkan tipe tiket yang dipilih, dengan huruf pertama dikapitalisasi menggunakan .capitalize().

Harga Diskon: Menampilkan apakah pengguna mendapatkan diskon (karena memiliki kartu member) atau tidak.

Total Harga: Menampilkan total harga tiket yang harus dibayar oleh pengguna, dikonversi menjadi bilangan bulat menggunakan int(total_harga) untuk menghilangkan desimal.


5. Contoh Eksekusi Program

Contoh Input:

Masukkan Nama Anda: Budi
Masukkan Jenis Tiket ('reguler'/'vip'): vip
Apakah Anda memiliki Kartu Member? (yes/no): yes

Python code ↑

Contoh Output:

Hasil Evaluasi:
Nama        :   Budi
Tipe Tiket  :   Vip
Harga Diskon:   Ya

Python code ↑

Total Harga :   rp.80000

Dalam contoh ini, pengguna bernama Budi memilih tiket VIP seharga Rp 100.000, dan ia memiliki kartu member, sehingga mendapatkan diskon 20%. Total harga yang harus dibayarkan adalah Rp 80.000.

Kesimpulan

Program ini sederhana dan intuitif untuk digunakan. Ini memungkinkan pengguna untuk memilih jenis tiket bioskop dan menentukan apakah mereka memiliki kartu member untuk mendapatkan diskon. Logika diskon dan tipe tiket diimplementasikan dengan operator ternary yang efisien.

---

def hitung_harga_tiket(tipe_tiket, kartu_member):
    # Harga tiket
    harga_reguler = 50000
    harga_vip = 100000
    
    # Menentukan harga tiket berdasarkan tipe tiket
    harga_tiket = harga_reguler if tipe_tiket == 'reguler' else harga_vip
    
    # Menghitung total harga dengan diskon jika member
    total_harga = harga_tiket * 0.8 if kartu_member else harga_tiket
    
    return total_harga

# Input data user
nama_user = input("Masukkan Nama Anda: ")
tipe_tiket = input("Masukkan Jenis Tiket ('reguler'/'vip'): ").lower()
kartu_member = input("Apakah Anda memiliki Kartu Member? (yes/no): ").casefold() == "yes"

# Fungsi hitung_harga_tiket digunakan untuk menghitung total harga tiket
total_harga = hitung_harga_tiket(tipe_tiket, bool(kartu_member))

print("\nHasil Evaluasi:")
print(f"Nama\t:\t{nama_user}")
print(f"Tipe Tiket\t:\t{tipe_tiket.capitalize()}")
print(f"Harga Diskon\t:\t{'Ya' if kartu_member else 'Tidak'}")

# Menampilkan output
print(f"\nTotal Harga\t:\trp.{int(total_harga)}")

---

# Program Kalkulator Sederhana

def kalkulator(angka_pertama, angka_kedua, operator):
    if operator == "+":
        return angka_pertama + angka_kedua
    elif operator == "-":
        return angka_pertama - angka_kedua
    elif operator == "*":
        return angka_pertama * angka_kedua
    elif operator == "/":
        if angka_kedua != 0:
            return angka_pertama / angka_kedua
        else:
            return "Error: Pembagian dengan nol!"
    else:
        return "Error: Operator tidak dikenali!"

# Input data user  
nama_user = input("Masukkan Nama Anda:")  

# Operasi aritmatika   
operasi_aritmatika = input("Operasi Arimatika (+,- ,*,/) ?: ").lower()   

# Angka pertama dan kedua    
try :
     angka_pertama=int(input("Angka Pertama ?: "))     
     angka_kedua= int(input("Angka Kedua ?: "))
except ValueError :
      print ('Mohon Masukkan Bilangan Bulat')
      
# Fungsi kalkulator digunakan untuk menghitung hasil operasi aritmatika   
hasil_operasi=kalkulator(angka_pertama ,angka_kedua ,operasi_aritmatika )    

print('\n Hasil Evaluasi:')    
print(f'Nama\t:\t{nama_user}')    
    
if isinstance(hasil_operasi, str):       
       print(f' Error: {hasil_operasi} ')
else :          
      print(f'\n {hasil_operasi}')   
---

Berikut adalah penjelasan lengkap dari Program Kalkulator Sederhana yang Anda buat:

1. Fungsi kalkulator(angka_pertama, angka_kedua, operator)

Fungsi ini bertugas untuk menghitung operasi aritmatika berdasarkan dua angka yang diberikan dan operator yang dipilih.

Penjelasan fungsi:

Parameter angka_pertama: Input berupa bilangan bulat dari pengguna.

Parameter angka_kedua: Input berupa bilangan bulat dari pengguna.

Parameter operator: Input berupa operator aritmatika yang akan digunakan dalam operasi, seperti penjumlahan (+), pengurangan (-), perkalian (*), atau pembagian (/).


Logika dalam fungsi:

Jika operator adalah +, maka akan melakukan penjumlahan antara angka_pertama dan angka_kedua.

Jika operator adalah -, maka akan melakukan pengurangan.

Jika operator adalah *, maka akan melakukan perkalian.

Jika operator adalah /, program memeriksa apakah angka_kedua tidak sama dengan nol untuk menghindari kesalahan pembagian dengan nol. Jika angka_kedua == 0, program mengembalikan pesan error, "Error: Pembagian dengan nol!".

Jika operator yang dimasukkan tidak dikenali (selain +, -, *, atau /), program mengembalikan pesan "Error: Operator tidak dikenali!".


2. Input Data Pengguna

Bagian ini bertugas untuk mengambil input dari pengguna:

Nama pengguna (nama_user): Mengambil nama pengguna yang dimasukkan melalui fungsi input().

Operator aritmatika (operasi_aritmatika): Meminta pengguna memasukkan operasi aritmatika yang ingin dilakukan. Input ini diubah menjadi huruf kecil dengan .lower() untuk memastikan input konsisten dalam proses pengecekan.

Angka pertama dan angka kedua (angka_pertama, angka_kedua): Meminta pengguna untuk memasukkan dua angka yang akan digunakan dalam operasi aritmatika. Input ini dicoba dikonversi menjadi bilangan bulat menggunakan int().


Penanganan Error:

Bagian ini menggunakan blok try-except untuk menangani kesalahan apabila pengguna memasukkan nilai yang bukan bilangan bulat:

Jika pengguna memasukkan nilai yang tidak bisa dikonversi menjadi integer, program akan menampilkan pesan "Mohon Masukkan Bilangan Bulat" dan mencegah program berhenti dengan error.


3. Pemanggilan Fungsi kalkulator()

Setelah input dari pengguna diperoleh dan divalidasi, program memanggil fungsi kalkulator() dengan parameter:

angka_pertama: angka pertama yang dimasukkan oleh pengguna.

angka_kedua: angka kedua yang dimasukkan oleh pengguna.

operasi_aritmatika: operator yang dipilih oleh pengguna.


Hasil dari operasi ini disimpan dalam variabel hasil_operasi.

4. Menampilkan Output

Program kemudian menampilkan hasil evaluasi dengan format sebagai berikut:

Nama pengguna: Menampilkan nama yang dimasukkan oleh pengguna.

Hasil operasi: Program mengecek tipe dari hasil_operasi. Jika tipe data adalah string, ini berarti ada kesalahan (seperti pembagian dengan nol atau operator yang tidak dikenali), sehingga akan mencetak pesan kesalahan yang telah disiapkan di fungsi kalkulator().


Jika tidak ada kesalahan (hasil operasi berupa angka), maka program akan menampilkan hasil perhitungan operasi aritmatika.

5. Contoh Eksekusi Program

Contoh Input:

Masukkan Nama Anda: Raffi
Operasi Arimatika (+,- ,*,/) ?: *
Angka Pertama ?: 5
Angka Kedua ?: 4

Python code ↑

Contoh Output:

Hasil Evaluasi:
Nama    :   Raffi

20

Python code ↑

6. Penanganan Kesalahan (Error Handling)

Jika pengguna memasukkan operator yang tidak valid (misalnya %), program akan mengembalikan error:

Error: Operator tidak dikenali!

Python code ↑

Jika pengguna mencoba membagi dengan nol:

Error: Pembagian dengan nol!

Python code ↑

Jika pengguna memasukkan angka yang bukan bilangan bulat:

Mohon Masukkan Bilangan Bulat

Python code ↑

Kesimpulan:

Program kalkulator ini memudahkan pengguna untuk melakukan operasi aritmatika dasar (penjumlahan, pengurangan, perkalian, dan pembagian) dengan penanganan kesalahan yang cukup baik.
