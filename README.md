# Jarkom_modul3_Lapres_E07
Praktikum Modul 3 Jarkom 2020<br/>
05111840000051 Juwita Kartika Rani<br/>
05111840000115 Muhammad Rafi Yudhistira<br/>
05111840007004 Siti Munawaroh<br/>
## Soal 1
#### Nano topologi.sh
<br/>![1](https://user-images.githubusercontent.com/56763570/100590149-ddae1500-32a8-11eb-86ef-c5f701a8a787.JPG)<br/>
#### Mensetting uml sesuai deskripsi soal
Di UML Surabaya<br/>
nano /etc/sysctl.conf<br/>
net.ipv4.ip_forward=1<br/>
sysctl -p<br/>

<br/>![Screenshot (23)](https://user-images.githubusercontent.com/58022238/100530185-49e53600-3221-11eb-82b6-de50f8ed356c.png)<br/>

#### Melakukan setting IP dengan nano /etc/network/interfaces
<br/>![Screenshot (24)](https://user-images.githubusercontent.com/58022238/100530216-b52f0800-3221-11eb-9dab-c65873b9c96f.png)<br/>
<br/>![1 4](https://user-images.githubusercontent.com/56763570/100535252-16c48780-31cc-11eb-9b57-79625563d0f5.png)<br/>
<br/>![1 5](https://user-images.githubusercontent.com/56763570/100535254-19bf7800-31cc-11eb-9bff-131991c9ccee.png)<br/>
<br/>![1 6](https://user-images.githubusercontent.com/56763570/100535255-1cba6880-31cc-11eb-8176-9baa25cb9276.png)<br/>
<br/>![1 7](https://user-images.githubusercontent.com/56763570/100535256-1d52ff00-31cc-11eb-9085-075b881e6218.png)<br/>
<br/>![1 8](https://user-images.githubusercontent.com/56763570/100535257-1f1cc280-31cc-11eb-9778-35fd2eb8beee.png)<br/>
<br/>![1 9](https://user-images.githubusercontent.com/56763570/100535260-23e17680-31cc-11eb-8027-9da4ba6d39f5.png)<br/>
<br/>![1 10](https://user-images.githubusercontent.com/56763570/100535261-23e17680-31cc-11eb-91e9-a9729f7f6ee6.png)<br/>

#### Melakukan iptables
<br/>![1 11](https://user-images.githubusercontent.com/56763570/100535355-019c2880-31cd-11eb-8006-08880dba0245.png)<br/>
<br/>![1 12](https://user-images.githubusercontent.com/56763570/100535361-0b259080-31cd-11eb-90d7-3e30e074e15b.png)<br/>
<br/>![1 13](https://user-images.githubusercontent.com/56763570/100535362-0c56bd80-31cd-11eb-982b-b57f2cee63c3.png)<br/>

## soal 2 
#### Install dhcp relay di UML Surabaya
<br/>apt-get install isc-dhcp-relay
<br/>![Screenshot (35)](https://user-images.githubusercontent.com/58022238/100530530-cf6ae500-3225-11eb-92f1-4d2da1552156.png)

#### Kemudian memasukkan IP Tuban dan mengatur nilai interfaces “eth1, eth2, eth3”
<br/>nano /etc/default/isc-dhcp-relay
<br/>![Screenshot (36)](https://user-images.githubusercontent.com/58022238/100530531-d265d580-3225-11eb-80f3-af73e210dec8.png)

#### Install DHCP di UML Tuban
<br/>apt-get install isc-dhcp-server
<br/>![Screenshot (37)](https://user-images.githubusercontent.com/58022238/100530534-d560c600-3225-11eb-876d-7ee5b22c6152.png)

#### Kemudian tambahkan subnet NID_DMZ di UML Tuban agar dhcp relay bisa berjalan
<br/>subnet 10.151.71.64 netmask 255.255.255.248{
	<br/>option routers 10.151.79.65;
<br/>}
<br/>![Screenshot (38)](https://user-images.githubusercontent.com/58022238/100530535-d85bb680-3225-11eb-826f-bc7bf20e59c4.png)
<br/>!

#### Kemudian mengubah semua client yang awalnya static menjadi dhcp dengan membuka
<br/>nano /etc/network/interfaces
<br/>menambakan
<br/>auto eth0
<br/>iface eth0 inet dhcp
<br/>![Screenshot (39)](https://user-images.githubusercontent.com/58022238/100530538-dc87d400-3225-11eb-9c3f-aec430cd9b38.png) 

## Soal 3 
#### Menambahkan subnet pada range 1
<br/>IP dari 192.168.0.10 sampai 192.168.0.100 dan 192.168.0.110 sampai 192.168.0.200.
<br/>![Screenshot (40)](https://user-images.githubusercontent.com/58022238/100535639-49fb2b00-324d-11eb-9369-4d63ea4ace1f.png)

## Soal 4 
#### Menambahkan range pada subnet 3
<br/>Client pada subnet 3 mendapatkan range IP dari 192.168.1.50 sampai 192.168.1.70.
<br/>
<br/>![Screenshot (43)](https://user-images.githubusercontent.com/58022238/100535652-68f9bd00-324d-11eb-84ef-8db9c94d8ea0.png)

## soal 5 
### DNS Malang dan DNS 202.46.129.2 dari DHCP
<br/>menambahkan
<br/>option domain-name-servers 10.151.71.66, 202.46.129.2
<br/>![Screenshot (43)](https://user-images.githubusercontent.com/58022238/100535819-c4787a80-324e-11eb-9377-72aa6c53949e.png)
<br/>![Screenshot (44)](https://user-images.githubusercontent.com/58022238/100535653-6ac38080-324d-11eb-96d4-c66ac4371b44.png)

## soal 6 
### Disubnet 1 mendapat pinjaman alamat IP selama 5 menit, sedangkan pada subnet 3 mendapatkan peminjaman IP selama 10 menit.
<br/>menabahkan:
<br/>default-lease-time 600;
<br/>max-lease-time 600;
<br/>pada kedua subnet yang ada di UML Tuban
<br/>![Screenshot (45)](https://user-images.githubusercontent.com/58022238/100535654-6c8d4400-324d-11eb-88bb-25f9914502bb.png)
<br/>![Screenshot (46)](https://user-images.githubusercontent.com/58022238/100535655-6d25da80-324d-11eb-9653-1972d5e48684.png)
<br/>![Screenshot (47)](https://user-images.githubusercontent.com/58022238/100536155-2934d480-3251-11eb-9b92-63b8dc1f203a.png)

## no 7
### install squid dan apache-utils di UML Mojokerto
<br/>apt-get install squid
<br/>apt-get install apache2-utils
<br/>edit konfigurasi seperti berikut nano /etc/squid/squid.conf
<br/>acl all src 0.0.0.0/0.0.0.0
<br/>http_port 8080
<br/>visible_hostname mojokerto
 
<br/>auth_param basic program /usr/lib/squid/ncsa_auth /etc/squid/passwd
<br/>auth_param basic children 5
<br/>auth_param basic realm Proxy
<br/>auth_param basic credentialsttl 2 hours
<br/>auth_param basic casesensitive on
<br/>acl USERS proxy_auth REQUIRED
<br/>http_access allow USERS
<br/>![Screenshot (48)](https://user-images.githubusercontent.com/58022238/100536158-2c2fc500-3251-11eb-9f81-f5b2cd1a4001.png)
<br/>lalu set password dengan htpasswd -c /etc/squid/passwd userta_e07
<br/>pass : inipassw0rdta_e07
<br/>![Screenshot (49)](https://user-images.githubusercontent.com/58022238/100536163-30f47900-3251-11eb-8c09-9a2b3bd27d01.png)

## soal 8
### tambahkan file acl.conf
<br/>nano /etc/squid/acl.conf dan tambahkan acl NGULITA time TW 13:00-18:00
<br/>![Screenshot (54)](https://user-images.githubusercontent.com/58022238/100536605-5a62d400-3254-11eb-9043-43afd0e303d3.png)
### lalu buka /etc/squid/squid.conf dan tambahkan

<br/>include /etc/squid/acl.conf
<br/>http_access allow USERS KULITA
<br/>http_access deny all
<br/>![Screenshot (55)](https://user-images.githubusercontent.com/58022238/100536613-63ec3c00-3254-11eb-9983-211c6b146c5f.png)

## soal 9
### nano /etc/squid/acl.conf dan tambahkan setting untuk hari selasa rabu kamis jumat, tambahkan juga settingan pada squid.conf
<br/>/etc/squid/ACL.conf
<br/>acl BIMBINGAN1 time TWH 21:00-23:59
<br/>acl BIMBINGAN2 time WHF 00:00-09:00

<br/>/etc/squid/squid.conf
<br/>http_access allow USERS BIMBINGAN1
<br/>http_access allow USERS BIMBINGAN2
<br/>![Screenshot (56)](https://user-images.githubusercontent.com/58022238/100536616-66e72c80-3254-11eb-830a-b5ce314621ab.png)
<br/>![Screenshot (57)](https://user-images.githubusercontent.com/58022238/100536617-68b0f000-3254-11eb-8248-89e112851ebe.png)

## soal 10
### nano /etc/squid/squid.conf dan tambahkan

<br/>Acl REDIRSITE dstdomain .google.com
<br/>deny_info 301:http://monta.if.its.ac.id REDIRSITE
<br/>http_access deny REDIRSITE
<br/>![Screenshot (58)](https://user-images.githubusercontent.com/58022238/100536620-6a7ab380-3254-11eb-8451-d997590f7fe0.png)

## soal 11
### cd /usr/share/squid/errors/English
<br/>replace ERR_ACCESS_DENIED dengan mendownload wget -N 10.151.36.202/ERR_ACCESS_DENIED
<br/>![Screenshot (59)](https://user-images.githubusercontent.com/58022238/100536624-6cdd0d80-3254-11eb-8283-d8dba8515efa.png)

## soal 12
### pada uml Malang, install bind9
<br/>apt-get install bind9
<br/>nano /etc/bind/named.conf.local dan konfiguraasikan seperti dibawah
<br/>![Screenshot (60)](https://user-images.githubusercontent.com/58022238/100536626-6ea6d100-3254-11eb-9d0c-d47e01a078be.png)
<br/>serta cp /etc/bind/db.local janganlupa-ta.e07.pw dan konfigurasikan seperti gambar dibawah
<br/>![Screenshot (61)](https://user-images.githubusercontent.com/58022238/100536628-70709480-3254-11eb-81d6-db6b2fa7f86d.png)
<br/>setelah itu baru proxy pada firefox bisa diganti menjadi janganlupa-ta.eo7.pw
<br/>![Screenshot (62)](https://user-images.githubusercontent.com/58022238/100536630-723a5800-3254-11eb-80ce-a86dbf057630.png)
<br/>![Screenshot (63)](https://user-images.githubusercontent.com/58022238/100536631-74041b80-3254-11eb-8019-75fae68470f3.png)










