## NAMA   = ADINDA AULIA NABILA PUTRI
## KELAS  = TI.24.A.4
## NIM    = 312410309


# Daftar kontak 

```PYTHON
kontak = {
    "Ari": "081267888",
    "Dina": "087677776"
}

print(f"Kontak Ari: {kontak['Ari']}")

kontak["Riko"] = "087654544"

kontak["Dina"] = "088999776"

print("Semua Nama:")
for nama in kontak:
    print(nama)

print("Semua Nomor:")
for nomor in kontak.values():
    print(nomor)

print("Daftar Nama dan Nomor:")
for nama, nomor in kontak.items():
    print(f"{nama}: {nomor}")

del kontak["Dina"]

print("Daftar Kontak setelah menghapus Dina:")
for nama, nomor in kontak.items():
    print(f"{nama}: {nomor}")
````

Berikut code program tersebut 

   ![program 1 ](https://github.com/user-attachments/assets/c77c2c03-c856-4daf-9292-516bf5c5e35e)


Berikut hasil program tersebut 

  ![Screenshot (75)](https://github.com/user-attachments/assets/2ce96c1b-81b1-49b5-b800-4ca83f469660)


# Nilai Input 

```PYTON
# Program Input Nilai
data_nilai = []

def lihat_data():
    if not data_nilai:
        print("Daftar Nilai")
        print("=" * 50)
        print("| NO |    NIM    |    NAMA    | TUGAS | UTS | UAS | AKHIR |")
        print("=" * 50)
        print("|                 TIDAK ADA DATA                   |")
        print("=" * 50)
    else:
        print("Daftar Nilai")
        print("=" * 50)
        print("| NO |    NIM    |    NAMA    | TUGAS | UTS | UAS | AKHIR |")
        print("=" * 50)
        for idx, data in enumerate(data_nilai, start=1):
            print(f"| {idx:2} | {data['nim']:8} | {data['nama']:10} | {data['tugas']:5} | {data['uts']:3} | {data['uas']:3} | {data['akhir']:5.2f} |")
        print("=" * 50)

def tambah_data():
    nim = input("NIM         : ")
    nama = input("Nama        : ")
    tugas = int(input("Nilai Tugas : "))
    uts = int(input("Nilai UTS   : "))
    uas = int(input("Nilai UAS   : "))
    akhir = (tugas + uts + uas) / 3
    data_nilai.append({"nim": nim, "nama": nama, "tugas": tugas, "uts": uts, "uas": uas, "akhir": akhir})

def ubah_data():
    nim = input("Masukkan NIM mahasiswa yang akan diubah: ")
    for data in data_nilai:
        if data['nim'] == nim:
            print("Data ditemukan. Silakan masukkan data baru.")
            data['nama'] = input("Nama        : ")
            data['tugas'] = int(input("Nilai Tugas : "))
            data['uts'] = int(input("Nilai UTS   : "))
            data['uas'] = int(input("Nilai UAS   : "))
            data['akhir'] = (data['tugas'] + data['uts'] + data['uas']) / 3
            print("Data berhasil diubah.")
            return
    print("Data tidak ditemukan.")

def hapus_data():
    nim = input("Masukkan NIM mahasiswa yang akan dihapus: ")
    for i, data in enumerate(data_nilai):
        if data['nim'] == nim:
            del data_nilai[i]
            print("Data berhasil dihapus.")
            return
    print("Data tidak ditemukan.")

def cari_data():
    nim = input("Masukkan NIM mahasiswa yang dicari: ")
    for data in data_nilai:
        if data['nim'] == nim:
            print("Data ditemukan:")
            print(f"NIM       : {data['nim']}")
            print(f"Nama      : {data['nama']}")
            print(f"Nilai Tugas : {data['tugas']}")
            print(f"Nilai UTS   : {data['uts']}")
            print(f"Nilai UAS   : {data['uas']}")
            print(f"Nilai Akhir : {data['akhir']:.2f}")
            return
    print("Data tidak ditemukan.")

while True:
    print("\nProgram Input Nilai")
    print("===================")
    print("(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar")
    pilihan = input("Pilih menu: ").lower()

    if pilihan == 'l':
        lihat_data()
    elif pilihan == 't':
        tambah_data()
    elif pilihan == 'u':
        ubah_data()
    elif pilihan == 'h':
        hapus_data()
    elif pilihan == 'c':
        cari_data()
    elif pilihan == 'k':
        print("Keluar dari program.")
        break
    else:
        print("Pilihan tidak valid. Silakan coba lagi.")
````

```PYTHON
data_nilai = []
````

list kosong yang akan digunakan untuk menyimpan data mahasiswa seperti NIM, Nama, nilai tugas, uts, uas dan nilai akhir.

```PYTHON
def lihat_data():
    if not data_nilai:
        print("Daftar Nilai")
        print("=" * 50)
        print("| NO |    NIM    |    NAMA    | TUGAS | UTS | UAS | AKHIR |")
        print("=" * 50)
        print("|                 TIDAK ADA DATA                   |")
        print("=" * 50)
    else:
        print("Daftar Nilai")
        print("=" * 50)
        print("| NO |    NIM    |    NAMA    | TUGAS | UTS | UAS | AKHIR |")
        print("=" * 50)
        for idx, data in enumerate(data_nilai, start=1):
            print(f"| {idx:2} | {data['nim']:8} | {data['nama']:10} | {data['tugas']:5} | {data['uts']:3} | {data['uas']:3} | {data['akhir']:5.2f} |")
        print("=" * 50)
````

Jika list kosong, maka akan ditampilkan pesan tidak ada. jika ada data maka program akan menampilkan daftar mahasiswa dalam format tabel dengan nomor urut, NIM, Nama, Nilai tugas, uts, uas, dan nilai akhir.

```PYTHON
def tambah_data():
    nim = input("NIM         : ")
    nama = input("Nama        : ")
    tugas = int(input("Nilai Tugas : "))
    uts = int(input("Nilai UTS   : "))
    uas = int(input("Nilai UAS   : "))
    akhir = (tugas + uts + uas) / 3
    data_nilai.append({"nim": nim, "nama": nama, "tugas": tugas, "uts": uts, "uas": uas, "akhir": akhir})
````

def tambah_data digunakan untuk memasukkan nim, nama, nilai tugas, uts, dan uas. Nilai akhir dihitung sebagai rata-rata dari ketiga nilai tersebut.

```PYTHON
def hapus_data():
    nim = input("Masukkan NIM mahasiswa yang akan dihapus: ")
    for i, data in enumerate(data_nilai):
        if data['nim'] == nim:
            del data_nilai[i]
            print("Data berhasil dihapus.")
            return
    print("Data tidak ditemukan.")
````

def hapus_data, jika NIM ditemukan data mahasiswa tersebut akan dihapus dari data_nilai dan sebaliknya jika NIM tidak ditemukan maka akan menampilkan pesan bahwa data tidak ditemukan.

```PYTHON
def cari_data():
    nim = input("Masukkan NIM mahasiswa yang dicari: ")
    for data in data_nilai:
        if data['nim'] == nim:
            print("Data ditemukan:")
            print(f"NIM       : {data['nim']}")
            print(f"Nama      : {data['nama']}")
            print(f"Nilai Tugas : {data['tugas']}")
            print(f"Nilai UTS   : {data['uts']}")
            print(f"Nilai UAS   : {data['uas']}")
            print(f"Nilai Akhir : {data['akhir']:.2f}")
            return
    print("Data tidak ditemukan.")
````

def cari_data, akan menampilkan data mahasiswa seperti NIM, nama, nilai tugas, UTS, UAS dan nilai akhir.

```PYTHON
while True:
    print("\nProgram Input Nilai")
    print("===================")
    print("(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar")
    pilihan = input("Pilih menu: ").lower()

    if pilihan == 'l':
        lihat_data()
    elif pilihan == 't':
        tambah_data()
    elif pilihan == 'u':
        ubah_data()
    elif pilihan == 'h':
        hapus_data()
    elif pilihan == 'c':
        cari_data()
    elif pilihan == 'k':
        print("Keluar dari program.")
        break
    else:
        print("Pilihan tidak valid. Silakan coba lagi.")
````

While True untuk bagian utama dari program yang menyediakan menu interaktif : (L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar


Berikut code dari program tersebut 

   ![programan 2](https://github.com/user-attachments/assets/45472a68-98d2-41f3-8748-ce44de6c7577)

Berikut hasil dari program tersebut 

   ![Screenshot (76)](https://github.com/user-attachments/assets/cbb263e3-f711-48da-b1e3-a54c018f53b0)


Berikut flowchart nya 

   ![Untitled Diagram drawio (4)](https://github.com/user-attachments/assets/98a90622-5b70-4475-9bbf-30fe6b315d62)






