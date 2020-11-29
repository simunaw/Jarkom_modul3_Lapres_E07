# Jarkom_modul3_Lapres_E07



1. 
a.) Di UML Surabaya
nano /etc/sysctl.conf 
uncomment net.ipv4.ip_forward=1
sysctl -p

![Screenshot (23)](https://user-images.githubusercontent.com/58022238/100530185-49e53600-3221-11eb-82b6-de50f8ed356c.png)

Melakukan setting IP dengan nano /etc/network/interfaces 

![Screenshot (24)](https://user-images.githubusercontent.com/58022238/100530216-b52f0800-3221-11eb-9dab-c65873b9c96f.png)

![Screenshot (25)](https://user-images.githubusercontent.com/58022238/100530292-c7f60c80-3222-11eb-80f8-e1aabd01bdd8.png)

![Screenshot (26)](https://user-images.githubusercontent.com/58022238/100530294-cdebed80-3222-11eb-919c-983a2b729a9c.png)

![Screenshot (27)](https://user-images.githubusercontent.com/58022238/100530295-d2180b00-3222-11eb-999f-6d9b17b32712.png)

![Screenshot (28)](https://user-images.githubusercontent.com/58022238/100530297-d6dcbf00-3222-11eb-992b-8f9cd13b26bc.png)

![Screenshot (29)](https://user-images.githubusercontent.com/58022238/100530298-dd6b3680-3222-11eb-8014-93f2a7498a02.png)

![Screenshot (30)](https://user-images.githubusercontent.com/58022238/100530304-e4924480-3222-11eb-8f53-9d8cb3e32e97.png)

![Screenshot (31)](https://user-images.githubusercontent.com/58022238/100530309-eb20bc00-3222-11eb-8de4-806a86f64bc4.png)

Melakukan iptables

![Screenshot (32)](https://user-images.githubusercontent.com/58022238/100530311-efe57000-3222-11eb-89c1-458f2c25d849.png)

![Screenshot (33)](https://user-images.githubusercontent.com/58022238/100530312-f378f700-3222-11eb-9dd4-799d4360daa2.png)

![Screenshot (34)](https://user-images.githubusercontent.com/58022238/100530315-f7a51480-3222-11eb-9d51-8e54ce9bbb5f.png)

2. Install dhcp relay di UML Surabaya
   apt-get install isc-dhcp-relay
   
   
a.) Kemudian memasukkan IP Tuban dan mengatur nilai interfaces “eth1, eth2, eth3”
nano /etc/default/isc-dhcp-relay



b.) Install DHCP di UML Tuban
apt-get install isc-dhcp-server



c.) Kemudian tambahkan subnet NID_DMZ di UML Tuban agar dhcp relay bisa berjalan
subnet 10.151.71.64 netmask 255.255.255.248{
	option routers 10.151.79.65;
}




d.) Kemudian mengubah semua client yang awalnya static menjadi dhcp dengan membuka
nano /etc/network/interfaces
menambakan
auto eth0
iface eth0 inet dhcp





