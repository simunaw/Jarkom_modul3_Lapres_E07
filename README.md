# Jarkom_modul3_Lapres_E07
Praktikum Modul 3 Jarkom 2020<br/>
05111840000051 Juwita Kartika Rani<br/>
05111840000115 Muhammad Rafi Yudhistira<br/>
05111840007004 Siti Munawaroh<br/>
## Soal 1 Mensetting uml sesuai deskripsi soal<br/>
### Di UML Surabaya<br/>
nano /etc/sysctl.conf<br/>
net.ipv4.ip_forward=1<br/>
sysctl -p<br/>

<br/>![Screenshot (23)](https://user-images.githubusercontent.com/58022238/100530185-49e53600-3221-11eb-82b6-de50f8ed356c.png)<br/>

### <br/>Melakukan setting IP dengan nano /etc/network/interfaces
<br/>![Screenshot (24)](https://user-images.githubusercontent.com/58022238/100530216-b52f0800-3221-11eb-9dab-c65873b9c96f.png)<br/>
<br/>![1 4](https://user-images.githubusercontent.com/56763570/100535252-16c48780-31cc-11eb-9b57-79625563d0f5.png)<br/>
<br/>![1 5](https://user-images.githubusercontent.com/56763570/100535254-19bf7800-31cc-11eb-9bff-131991c9ccee.png)<br/>
<br/>![1 6](https://user-images.githubusercontent.com/56763570/100535255-1cba6880-31cc-11eb-8176-9baa25cb9276.png)<br/>
<br/>![1 7](https://user-images.githubusercontent.com/56763570/100535256-1d52ff00-31cc-11eb-9085-075b881e6218.png)<br/>
<br/>![1 8](https://user-images.githubusercontent.com/56763570/100535257-1f1cc280-31cc-11eb-9778-35fd2eb8beee.png)<br/>
<br/>![1 9](https://user-images.githubusercontent.com/56763570/100535260-23e17680-31cc-11eb-8027-9da4ba6d39f5.png)<br/>
<br/>![1 10](https://user-images.githubusercontent.com/56763570/100535261-23e17680-31cc-11eb-91e9-a9729f7f6ee6.png)<br/>

### <br/>Melakukan iptables<br/>
<br/>![1 11](https://user-images.githubusercontent.com/56763570/100535355-019c2880-31cd-11eb-8006-08880dba0245.png)<br/>
<br/>![1 12](https://user-images.githubusercontent.com/56763570/100535361-0b259080-31cd-11eb-90d7-3e30e074e15b.png)<br/>
<br/>![1 13](https://user-images.githubusercontent.com/56763570/100535362-0c56bd80-31cd-11eb-982b-b57f2cee63c3.png)<br/>



2. Install dhcp relay di UML Surabaya

   apt-get install isc-dhcp-relay
   
   ![Screenshot (35)](https://user-images.githubusercontent.com/58022238/100530530-cf6ae500-3225-11eb-92f1-4d2da1552156.png)

a.) Kemudian memasukkan IP Tuban dan mengatur nilai interfaces “eth1, eth2, eth3”

nano /etc/default/isc-dhcp-relay

![Screenshot (36)](https://user-images.githubusercontent.com/58022238/100530531-d265d580-3225-11eb-80f3-af73e210dec8.png)

b.) Install DHCP di UML Tuban

apt-get install isc-dhcp-server

![Screenshot (37)](https://user-images.githubusercontent.com/58022238/100530534-d560c600-3225-11eb-876d-7ee5b22c6152.png)


c.) Kemudian tambahkan subnet NID_DMZ di UML Tuban agar dhcp relay bisa berjalan

subnet 10.151.71.64 netmask 255.255.255.248{

	option routers 10.151.79.65;
}

![Screenshot (38)](https://user-images.githubusercontent.com/58022238/100530535-d85bb680-3225-11eb-826f-bc7bf20e59c4.png)
!

d.) Kemudian mengubah semua client yang awalnya static menjadi dhcp dengan membuka

nano /etc/network/interfaces

menambakan

auto eth0

iface eth0 inet dhcp

![Screenshot (39)](https://user-images.githubusercontent.com/58022238/100530538-dc87d400-3225-11eb-9c3f-aec430cd9b38.png)




