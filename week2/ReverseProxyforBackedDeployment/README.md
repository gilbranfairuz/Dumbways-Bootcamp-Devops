# Dumbways Bootcamp DevOps
## Week 2
### Reverse Proxy for Backend Application


1. Buat file reverse proxy untuk backend, tambahkan script berikut.
   
   ![2](https://github.com/gilbranfairuz/Dumbways-Bootcamp-Devops/blob/master/week2/ReverseProxyforBackedDeployment/img/2.png)

2. Lalu pada nginx.conf tambahkan directory dari file reverse proxy backend.
   
   ![3](https://github.com/gilbranfairuz/Dumbways-Bootcamp-Devops/blob/master/week2/ReverseProxyforBackedDeployment/img/3.png)

3. Buat file reverse proxy untuk frontend pada nginx seperti berikut. Karena akan diterapkan Load Balancing pada Nginx, sehingga ada penambahan script upstream. Metode Load Balancing yang digunakan yaitu Round Robin. Pada gambar dibawah sudah terlihat ada SSL yang terapkan, hal ini dapat diabaikan terlebih dahulu karena step yang dilakukan pada saat pengerjaan sedikit berbeda.
   
   ![5](https://github.com/gilbranfairuz/Dumbways-Bootcamp-Devops/blob/master/week2/ReverseProxyforBackedDeployment/img/5.png)
