# Responsi-TeknologiCloud-Indah

# 1. Persiapan 
Dalam tahap persiapan, dua direktori, website-utama dan website-profil, perlu dibuat. Di dalam direktori website-utama, buat file index.html yang berisi konten HTML dasar untuk halaman utama, dengan tautan ke halaman profil. Konten index.html di website-utama adalah sebagai berikut:

![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/feb6f903-9a14-4ca1-b6a9-da3ac9aa538e)
![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/44de6bce-d5ca-4d46-9d2e-3bca5a1c437c)


Di dalam direktori website-profil, buat file index.html yang akan menampilkan gambar profil dari URL yang diberikan. Konten index.html di website-profil adalah sebagai berikut:

![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/891f1757-c524-471c-9639-8f6095858960)

![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/e222ddc7-91c2-4cd0-83e1-cdffe1674264)


# 2. Docker Network (Modul 13) 
Untuk menghubungkan container yang akan dibuat, buat jaringan Docker dengan nama my-nama-mahasiswa-network. Perintah untuk membuat jaringan Docker adalah sebagai berikut:
docker network create my-nama-mahasiswa-network
![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/8bc8fffd-9443-4b97-b22e-bac09b1f42fe)

# 3. Dockerfile dan Image (Module 11 dan 12) 
      3.1 Dockerfile untuk Website Utama (direktori website-utama)
  
      Di dalam direktori website-utama, buat file Dockerfile yang berisi instruksi untuk mengonfigurasi server Nginx dan menyalin konten direktori ke dalam container. Isi Dockerfile adalah sebagai berikut:

      FROM nginx:latest
      COPY . /usr/share/nginx/html
      EXPOSE 80

  3.2 Dockerfile untuk Website Profil (direktori website-profil)
  
      Di dalam direktori website-profil, buat file Dockerfile dengan instruksi yang sama untuk mengonfigurasi server Nginx dan menyalin konten direktori. Isi Dockerfile adalah sebagai berikut:

      FROM nginx:latest
      COPY . /usr/share/nginx/html
      EXPOSE 80


# 4. Build Image 


# 5. Docker Volume (Modul 14)


# 6. Menjalankan Container (Modul 9 & 10)
