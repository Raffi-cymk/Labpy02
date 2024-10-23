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

Jika tipe_tiket adalah 'reguler', maka harga_tiket akan menjadi Rp 50.000, sebaliknya jika 'vip', maka harga_tiket adalah Rp 100.000.

Kemudian program mengecek apakah pengguna memiliki kartu member:

total_harga = harga_tiket * 0.8 if kartu_member else harga_tiket

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

Contoh Output:

Hasil Evaluasi:
Nama        :   Budi
Tipe Tiket  :   Vip
Harga Diskon:   Ya

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
