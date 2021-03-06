# Dumbways Bootcamp DevOps
## Week 4
### Setup Server with Ansible

Pada kegiatan ini akan dilakukan setup server menggunakan Ansible. Terdapat 6 server yang akan di setup, 1 server public untuk nginx, 1 server private untuk database, 4 server private untuk docker (Jenkins, Monitoring, Frontend dan Backend). Dan ditambah 1 server private khusus untuk Ansible.

1. Pastikan server sudah diinstall dan dapat terhubung ke internet. Dan pastikan juga ansible dapat melakukan remote ke setiap server yang bersangkutan. Untuk memudahkan remote masukan id_rsa .pub dari ansible ke setiap server di authorized_keys agar remote tidak memerlukan password.
    
2. Yang pertama dilakukan melakukan update, lalu menginstall Ansible.
   
   ![6](/week4/SetupServerwithAnsible/img/6.png)

   ![7](/week4/SetupServerwithAnsible/img/7.png)

   ![8](/week4/SetupServerwithAnsible/img/8.png)

3. Selanjutnya membuat file Inventory. File ini berisi seluruh host yang akan di setup oleh ansible. File ini disimpan di folder /home/$USER/ansible/ agar lebih ter-management. User sebelumnya sudah dibuat di setiap server, sehingga pada inventory langsung dimasukkan.
   
   ![9](/week4/SetupServerwithAnsible/img/9.png)

4. Melakukan pengujian ping menggunakn Ansible.
   
   ![10](/week4/SetupServerwithAnsible/img/10.png)

5. Lalu buat file config ansible.cfg di direktori yang sama. dan memasukan line inventory, agar memudahkan ketika eksekusi ansible.
   
   ![11](/week4/SetupServerwithAnsible/img/11.png)

6. Lakukan pengujian ping menggunakan ansible tanpa argumen -i
   
   ![12](/week4/SetupServerwithAnsible/img/12.png)

7. Untuk melakukan test pada setup server, dilakukan update denan command seperti gambar dibawah.
   
   ![13](/week4/SetupServerwithAnsible/img/13.png)

8. Setelah berhasil selanjutnya adalah menginstall packages. Untuk yang pertama akan dilakukan instalasi nginx dan certbot. buat file nginx.yml, setelah itu eksekusi file tersebut dengan command:
   ```
   ansible-playbook nginx.yml -bK
   ```
   
   ![14](/week4/SetupServerwithAnsible/img/14.png)

   ![15](/week4/SetupServerwithAnsible/img/15.png)

9.  Selanjutnya membuat file cloneRepo.yml untuk mengclone project backend dan frontend, dan juga disini mengclone monitoring (Node Exporter, Prometheus, Grafana) dan Jenkins. Karena sebelumnya sudah dibuat file docker-compose yang disimpan di repo pribadi. Lalu eksekusi file tersebut.
    
    ![16](/week4/SetupServerwithAnsible/img/16.png)

    ![17](/week4/SetupServerwithAnsible/img/17.png)

10. Selanjutnya menginstall docker. Sama seperti yang lainnya membuat file docker.yml dan menyesuaikan apa yang harus dilakukan. Pada step docker akan menambahkan user yang sudah dibuat ke group docker, dan menginstall docker-compose.
    
    ![18](/week4/SetupServerwithAnsible/img/18.png)

    ![19](/week4/SetupServerwithAnsible/img/19.png)

    ![20](/week4/SetupServerwithAnsible/img/20.png)

    ![21](/week4/SetupServerwithAnsible/img/21.png)

11. Selanjutnya menginstall database server,membuat user remote, membuat database, dan bindIP yang akan digunakan.
    
    ![22](/week4/SetupServerwithAnsible/img/22.png)

    ![23](/week4/SetupServerwithAnsible/img/23.png)

12. Selanjutnya menginstall mysql client.
    
    ![24](/week4/SetupServerwithAnsible/img/24.png)

    ![25](/week4/SetupServerwithAnsible/img/25.png)

13. Selanjutnya menjalankan service docker untuk jenkins, monitoring, backend dan frontend.

    ![26](/week4/SetupServerwithAnsible/img/26.png) 

    ![27](/week4/SetupServerwithAnsible/img/27.png)

14. Hasil pengujian

    ![33](/week4/SetupServerwithAnsible/img/33.png)

    ![34](/week4/SetupServerwithAnsible/img/34.png)

    ![35](/week4/SetupServerwithAnsible/img/35.png)

    ![36](/week4/SetupServerwithAnsible/img/36.png)

    ![37](/week4/SetupServerwithAnsible/img/37.png)

    ![38](/week4/SetupServerwithAnsible/img/38.png)