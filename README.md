# Responsi-TeknologiCloud-Indah

# 1. Persiapan 
Dalam tahap persiapan, dua direktori, website-utama dan website-profil, perlu dibuat. Di dalam direktori website-utama, buat file index.html yang berisi konten HTML dasar untuk halaman utama, dengan tautan ke halaman profil. Konten index.html di website-utama adalah sebagai berikut:

![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/feb6f903-9a14-4ca1-b6a9-da3ac9aa538e)

_nano website-profil/index.html_
![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/44de6bce-d5ca-4d46-9d2e-3bca5a1c437c)


Di dalam direktori website-profil, buat file index.html yang akan menampilkan gambar profil dari URL yang diberikan. Konten index.html di website-profil adalah sebagai berikut:

![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/891f1757-c524-471c-9639-8f6095858960)

_nano website-profil/index.html_

![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/e222ddc7-91c2-4cd0-83e1-cdffe1674264)


# 2. Docker Network (Modul 13) 
Untuk menghubungkan container yang akan dibuat, buat jaringan Docker dengan nama my-nama-mahasiswa-network. Perintah untuk membuat jaringan Docker adalah sebagai berikut:
docker network create my-nama-mahasiswa-network
![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/8bc8fffd-9443-4b97-b22e-bac09b1f42fe)

# 3. Dockerfile dan Image (Module 11 dan 12) 
3.1 Dockerfile untuk Website Utama (direktori website-utama)
  
Di dalam direktori website-utama, buat file Dockerfile yang berisi instruksi untuk mengonfigurasi server Nginx dan menyalin konten direktori ke dalam container. Isi Dockerfile adalah sebagai berikut:

![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/47cf3249-4098-40e6-a896-90d2e2166d51)


      FROM nginx:latest
      COPY . /usr/share/nginx/html
      EXPOSE 80

![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/1f5755d4-c623-478a-b6a9-d91ea946f3d6)

3.2 Dockerfile untuk Website Profil (direktori website-profil)
  
Di dalam direktori website-profil, buat file Dockerfile dengan instruksi yang sama untuk mengonfigurasi server Nginx dan menyalin konten direktori. Isi Dockerfile adalah sebagai berikut:

![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/a8199311-293f-45b7-b22e-8d4624d47a48)



      FROM nginx:latest
      COPY . /usr/share/nginx/html
      EXPOSE 80

![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/069174a5-28ac-482e-b6f6-f9433b47d424)


# 4. Build Image 
Build Image untuk Website Utama
Untuk membangun image Docker dari Dockerfile di dalam direktori website-utama, gunakan perintah berikut:

      cd website-utama
      docker build -t website-utama .

![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/f999ff7c-022a-4719-ae85-5763870c071c)


Build Image untuk Website Profil
Untuk membangun image Docker dari Dockerfile di dalam direktori website-profil, gunakan perintah berikut:

      cd ../website-profil
      docker build -t website-profil .

![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/887c7ace-3df4-4b9c-8552-8336e9067808)


# 5. Docker Volume (Modul 14) 
Buat volume bernama profile-images
Jika Anda ingin menggunakan volume untuk menyimpan gambar profil, buat volume dengan nama profile-images menggunakan perintah berikut:

      docker volume create profile-images

![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/73322e21-8831-46f9-a336-ef3d8e7f7237)

Konfigurasikan agar container website-utama dan website-profil mengakses gambar profil melalui volume ini
Untuk mengkonfigurasi container agar menggunakan volume profile-images, jalankan container dengan perintah berikut (opsional):
![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/7c2088ed-57dc-464e-8f9f-2553a6643c50)


# 6. Menjalankan Container (Modul 9 & 10)
1. Jalankan Container Website Utama

Untuk menjalankan container dari image website-utama yang telah dibuat, gunakan perintah berikut:
      docker run -d --name website-utama --network my-nama-mahasiswa-network -p 80:80 website-utama

![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/a2655d96-1436-4e61-8278-38661523756e)


2. Jalankan Container Website Profil

Untuk menjalankan container dari image website-profil yang telah dibuat, gunakan perintah berikut:
      docker run -d --name website-profil --network my-nama-mahasiswa-network -p 81:80 website-profil

![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/96551f2e-54c3-4345-b06b-61eb0e05fbfa)

# Pengujian
1. Akses website
   
![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/88eaf32c-6c22-4513-9125-bbabd4a2a903)

![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/72e85038-6e80-4bb8-88bb-de89a5922be0)

![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/489f2319-ab6c-4abc-8e99-959e1a7b9eb9)

   
3. Klik link "profil". Apakah link tersebut mengarah dan menampilkan gambar profil Anda?

![image](https://github.com/dwiindahh/Responsi-TeknologiCloud-Indah/assets/126337792/04123827-aed4-441a-89de-75db90aad72b)

