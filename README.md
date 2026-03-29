# Database sederhana menggunakan list of dictionaries
stok_makanan = [
    {"id": 1, "nama": "Nasi Goreng", "harga": 15000, "stok": 10},
    {"id": 2, "nama": "Mie Ayam", "harga": 12000, "stok": 15}
]

def tampilkan_menu():
    print("\n=== SISTEM PENGELOLAAN MAKANAN ===")
    print("1. Lihat Daftar Makanan")
    print("2. Tambah Makanan Baru")
    print("3. Hapus Makanan")
    print("4. Keluar")

def lihat_makanan():
    print("\nDaftar Stok Makanan:")
    print(f"{'ID':<5} {'Nama Makanan':<20} {'Harga':<10} {'Stok':<5}")
    print("-" * 45)
    for mkn in stok_makanan:
        print(f"{mkn['id']:<5} {mkn['nama']:<20} {mkn['harga']:<10} {mkn['stok']:<5}")

def tambah_makanan():
    id_baru = len(stok_makanan) + 1
    nama = input("Masukkan nama makanan: ")
    harga = int(input("Masukkan harga: "))
    stok = int(input("Masukkan jumlah stok: "))
    
    makanan_baru = {"id": id_baru, "nama": nama, "harga": harga, "stok": stok}
    stok_makanan.append(makanan_baru)
    print(f"Berhasil menambahkan {nama}!")

# Loop Utama Program
while True:
    tampilkan_menu()
    pilihan = input("Pilih menu (1-4): ")

    if pilihan == '1':
        lihat_makanan()
    elif pilihan == '2':
        tambah_makanan()
    elif pilihan == '3':
        id_hapus = int(input("Masukkan ID makanan yang ingin dihapus: "))
        # Mencari dan menghapus berdasarkan ID
        stok_makanan = [m for m in stok_makanan if m['id'] != id_hapus]
        print("Data berhasil diperbarui.")
    elif pilihan == '4':
        print("Terima kasih!")
        break
    else:
        print("Pilihan tidak valid.")