# CoreStress  

## Deskripsi  
Repositori ini berisi skrip Python untuk memproses data dari file Excel. Skrip ini dirancang untuk membantu dalam pengolahan data faktur dan barang. 
Automatisasi File Raw `source_file.xlsx` ke `FP.xlsx` siap convert jadi xml
  
## Skrip yang Tersedia  
- `cust.py`: Skrip untuk memproses data faktur.  
- `goods.py`: Skrip untuk memproses data barang.  
- `setupcore.py`: Skrip untuk menyiapkan lingkungan kerja.  
- `requirements.txt`: Daftar dependensi yang diperlukan.  
- `FP.xlsx`: Contoh hasil output dari `setupcore.py` yang digunakan saat menjalankan `cust.py` dan `goods.py`.  
- `source_file.xlsx`: Contoh file sumber yang digunakan.  
  
## Instalasi  
Ikuti langkah-langkah berikut untuk menginstal Python dan menjalankan skrip:  
  
1. **Instalasi Python**  
   - Unduh dan instal Python dari [python.org](https://www.python.org/downloads/).  
   - Pastikan untuk mencentang opsi "Add Python to PATH" saat instalasi.  
  
2. **Cek Versi Python**  
   - Buka Command Prompt dan jalankan:  
     ```python --version```
     
3. **Instalasi pip**  
   - Pip biasanya sudah terinstal dengan Python. Untuk memeriksa, jalankan:  
     ```pip --version```
     
4. **Menyiapkan Lingkungan Kerja**  
   - Buat folder baru untuk proyek Anda dan navigasikan ke folder tersebut.  
   - Buat virtual environment:  
     ```python -m venv venv```
   - Aktifkan virtual environment:  
     ```venv\Scripts\activate```
     
5. **Instalasi Dependensi**  
   - Instal dependensi yang diperlukan dengan menjalankan:  
     ```pip install -r requirements.txt```

6. **Menjalankan Skrip**  
   - Setelah semua langkah di atas selesai, Anda dapat menjalankan skrip dengan perintah berikut:  
     ```python setupcore.py```
     
     ```python cust.py "source_file.xlsx" "FP.xlsx" --use_referensi --location "(Nama Perusahaanmu)"```
     
     ```python goods.py "source_file.xlsx" "FP.xlsx"```

## Format File Sumber  
Sebelum menjalankan `cust.py` & `goods.py`, pastikan format file sumber Anda adalah sebagai berikut:

### Formula Excel  
- Di sel A2, gunakan formula berikut: 
  ```=IF(COUNTIFS(B$2:B2, B2, C$2:C2, C2, E$2:E2, E2, D$2:D2,D2 )=1, MAX(A$1:A1)+1, A1)```

  Lalu sesuaikan, hapus yang tidak perlu (Contohnya warna Merah)

- Saya Menyebutnya ini ```source_file.xlsx```
    ![image](https://github.com/user-attachments/assets/e36af949-60ea-4fed-9aa4-4ff856c6d2a1)

- Sampai jadi seperti ini, jangan lupa pindahkan dari kolom A ke kolom J
    ![image](https://github.com/user-attachments/assets/28b99137-0f28-42b8-b419-6be4bc55737e)
  
## Contoh Output  
1. **Menjalankan `setupcore.py`:**
   
     ```python setupcore.py```

     Output: File FP.xlsx berhasil dibuat. (isi Nama Bebas, Sbg Contoh saya isi pakai "FP")

     Dibagian ini bisa disesuaikan Cabang mana yang sedang bertanskaski
   
3. **Menjalankan `cust.py`:**
   
     ```python cust.py "source_file.xlsx" "FP.xlsx" --use_referensi --location "(Nama Perusahaanmu)"```

     Output: Data berhasil dipindahkan ke sheet 'Faktur'. Total Baris: X

     Bagian ini boleh tidak pakai ```--use_referensi```
   
3. **Menjalankan `goods.py`:**
   
     ```python cust.py "source_file.xlsx" "FP.xlsx"```

## Kontribusi  
Jika Anda ingin berkontribusi pada proyek ini, silakan fork repositori ini dan buat pull request.  
  
## Lisensi  
Proyek ini dilisensikan di bawah [MIT License](LICENSE).  
