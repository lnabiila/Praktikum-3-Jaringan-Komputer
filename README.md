[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/1zoHyFGp)
| Name           | NRP        | Kelas     |
| ---            | ---        | ----------|
| Hilmi Fawwaz Sa'ad | 5025221103 | Jaringan Komputer (A) |
| Lathiifah Nabiila Bakhtiar | 5025221130 | Jaringan Komputer (A) |

## Put your topology config image here!

![image](https://github.com/user-attachments/assets/2cc0e5c3-e6f7-4b04-b81d-85b859a314c5)

<br>

> Template testing report: https://docs.google.com/document/d/17T0fsnh_4zZTrG-lELDJ88intrc9mkwCzZ_s-23JLCc/edit?usp=sharing

## Put your testing report here! 
> The report is sent in PDF format, uploaded to Drive, and set to public view.

> Link report: https://drive.google.com/drive/folders/1Ym2sZ0mG50Uaqj2Fu8hVuZs6ZH3xrUSW?usp=sharing

## Soal 0

> Pada perlombaan akhir tahun kali ini, semua worker dan client ikut serta di dalamnya sebagai perwakilan dari masing-masing asrama. Persiapan yang dilakukan untuk perlombaan ini adalah dengan setup semua network configuration yang sesuai dengan tabel peran diatas. Khusus untuk client menggunakan konfigurasi dari DHCP Server.

> _For the end-of-year competition, all the workers and clients participate, representing their respective houses. The preparation includes setting up the network configuration as per the table above, with clients using DHCP Server configuration_

**Answer**

- Dumbledore:

  ```
  auto eth0
  iface eth0 inet dhcp
  
  auto eth1
  iface eth1 inet static
  	address 10.14.1.1
  	netmask 255.255.255.0
  
  auto eth2
  iface eth2 inet static
  	address 10.14.2.1
  	netmask 255.255.255.0
  
  auto eth3
  iface eth3 inet static
  	address 10.14.3.1
  	netmask 255.255.255.0
  
  auto eth4
  iface eth4 inet static
  	address 10.14.4.1
  	netmask 255.255.255.0
  
  auto eth5
  iface eth5 inet static
  	address 10.14.5.1
  	netmask 255.255.255.0
  
  auto eth6
  iface eth6 inet static
  	address 10.14.6.1
  	netmask 255.255.255.0
  
  up iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 10.14.0.0/16
  ```

- SeverusSnape:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.3.2
  	netmask 255.255.255.0
    gateway 10.14.3.1
    
  up echo 'nameserver 192.168.122.1' > /etc/resolv.conf
  ```

- McGonagall:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.3.3
  	netmask 255.255.255.0
    gateway 10.14.3.1
    
  up echo 'nameserver 192.168.122.1' > /etc/resolv.conf
  ```

- Hagrid:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.4.2
  	netmask 255.255.255.0
    gateway 10.14.4.1
    
  up echo 'nameserver 192.168.122.1' > /etc/resolv.conf
  ```

- Voldemort:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.4.3
  	netmask 255.255.255.0
    gateway 10.14.4.1
    
  up echo 'nameserver 192.168.122.1' > /etc/resolv.conf
  ```

- Dementor:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.4.4
  	netmask 255.255.255.0
    gateway 10.14.4.1
    
  up echo 'nameserver 192.168.122.1' > /etc/resolv.conf
  ```

- HarryPotter:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.1.2
  	netmask 255.255.255.0
    gateway 10.14.1.1
  
  up echo 'nameserver 192.168.122.1' > /etc/resolv.conf
  ```

- RonWeasley:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.1.3
  	netmask 255.255.255.0
    gateway 10.14.1.1
  
  up echo 'nameserver 192.168.122.1' > /etc/resolv.conf
  ```

- HermioneGranger:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.1.4
  	netmask 255.255.255.0
    gateway 10.14.1.1
  
  up echo 'nameserver 192.168.122.1' > /etc/resolv.conf
  ```

- LunaLovegood:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.6.2
  	netmask 255.255.255.0
    gateway 10.14.6.1
    
  up echo 'nameserver 192.168.122.1' > /etc/resolv.conf
  ```

- FiliusFlitwick:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.6.3
  	netmask 255.255.255.0
    gateway 10.14.6.1
    
  up echo 'nameserver 192.168.122.1' > /etc/resolv.conf
  ```

- ChoChang:

  ```
  auto eth0
  iface eth0 inet static
  	address 10.14.6.4
  	netmask 255.255.255.0
    gateway 10.14.6.1
    
  up echo 'nameserver 192.168.122.1' > /etc/resolv.conf
  ```

- DracoMalfoy:

  ```
  auto eth0
  iface eth0 inet dhcp
  ```

- AstoriaGreengrass:

  ```
  auto eth0
  iface eth0 inet dhcp
  ```

- SusanBones:

  ```
  auto eth0
  iface eth0 inet dhcp
  ```

- HannahAbbott:

  ```
  auto eth0
  iface eth0 inet dhcp
  ```

## Soal 1

> Melakukan registrasi subdomain untuk PHP worker bernama gryffindor.hogwarts.yyy.com yang mengarah ke alamat IP load balancer Voldemort dan untuk laravel worker bernama ravenclaw.hogwarts.yyy.com yang mengarah ke alamat IP load balancer Dementor. Seluruh domain ini berkumpul dalam suatu ruang atau folder bernama hogwarts

> _Registering subdomains for the PHP workers named gryffindor.hogwarts.yyy.com, pointing to the IP Voldemort load balancer, and for the Laravel workers named ravenclaw.hogwarts.yyy.com, pointing to the IP Dementor load balancer. All domains are gathered in a folder named "hogwarts."_

**Answer:**

- Screenshot

  ![image](https://github.com/user-attachments/assets/6108ecca-33d0-41c2-bf81-1a5b646c4507)

- Configuration
  #### McGonagall
  - Konfigurasi /etc/bind/named.conf.local
    ```
    zone "hogwarts.A13.com" {
        type master;
        file "/etc/bind/hogwarts/hogwarts.A13.com";
    };
    ```
  - Konfigurasi /etc/bind/hogwarts/hogwarts.A13.com
    ```
    $TTL 604800
    @   IN  SOA hogwarts.A13.com. root.hogwarts.A13.com. (
                    2          ; Serial
                    604800     ; Refresh
                    86400      ; Retry
                    2419200    ; Expire
                    604800 )   ; Negative Cache TTL
    @   IN  NS      hogwarts.A13.com.
    gryffindor IN   A       10.14.4.3
    ravenclaw IN    A       10.14.4.4
    @   IN  AAAA    ::1
    ```
- Explanation
  #### McGonagall
  - Pertama, lakukan instalasi bind9
    ```
    apt-get update
    apt-get install bind9 -y
    ```
  - Buat folder hogwarts dan copy db.local
    ```
    mkdir /etc/bind/hogwarts
    cp /etc/bind/db.local /etc/bind/hogwarts/hogwarts.A13.com
    ```
  - Membuat zone untuk hogwarts.A13.com dengan melakukan konfigurasi pada /etc/bind/named.conf.local
  - Set subdomain gryffindor agar gryffindor.hogwarts.A13.com mengarah ke alamat IP load balancer Voldemort `10.14.4.3` dan ravenclaw.hogwarts.A13.com mengarah ke alamat IP load balancer Dementor `10.14.4.4` dengan melakukan konfigurasi pada /etc/bind/hogwarts/hogwarts.A13.com
  - Lalu, `service named restart`
  #### Client
  Set nameserver ke IP DNS Server lalu tes ping
  ```
  echo 'nameserver 10.14.3.3' > /etc/resolv.conf
  
  ping gryffindor.hogwarts.A13.com -c 3
  ping ravenclaw.hogwarts.A13.com -c 3
  ```
  
<br>

## Soal 2

> Memberikan ketentuan khusus untuk DracoMalfoy dan AstoriaGreengrass yang mendapat range IP dari [Prefix IP].2.64 - [Prefix IP].2.65 dan [Prefix IP].2.100 - [Prefix IP].2.101

> Selain itu, untuk HannahAbbott dan SusanBones mendapat range IP dari [Prefix IP].5.50 - [Prefix IP].5.51 dan [Prefix IP].5.155 - [Prefix IP].5.156.


> _Special provisions are given to DracoMalfoy and AstoriaGreengrass, who are assigned the IP range from [Prefix IP].2.64 - [Prefix IP].2.65 and [Prefix IP].2.100 - [Prefix IP].2.101._

> _Additionally, HannahAbbott and SusanBones are assigned the IP range from [Prefix IP].5.50 - [Prefix IP].5.51 and [Prefix IP].5.155 - [Prefix IP].5.156._

**Answer:**

- Screenshot

  ![image](https://github.com/user-attachments/assets/66046212-556e-4b24-9a01-ed1459d76d46)
  ![image](https://github.com/user-attachments/assets/864e3e85-c008-4ed6-8c62-44078f1f645a)
  ![image](https://github.com/user-attachments/assets/bfc436d5-0e1c-45c5-8a44-69b49c0e4d5a)
  ![image](https://github.com/user-attachments/assets/33b1a25e-4d6f-4831-882a-8f1530a33a07)

- Configuration
  #### Dumbledore
  - Konfigurasi /etc/default/isc-dhcp-relay
    ```
    SERVERS="10.14.3.2"
    INTERFACES="eth1 eth2 eth3 eth4 eth5 eth6"
    OPTIONS=””
    ```
  - Konfigurasi /etc/sysctl.conf
    ```
    net.ipv4.ip_forward=1
    ```
  #### SeverusSnape
  - Konfigurasi /etc/default/isc-dhcp-server
    ```
    INTERFACESv4="eth0"
    INTERFACESv6=""
    ```
  - Konfigurasi /etc/dhcp/dhcpd.conf
    ```
    subnet 10.14.1.0 netmask 255.255.255.0 {
    }
    
    subnet 10.14.2.0 netmask 255.255.255.0 {
        range 10.14.2.64 10.14.2.65;
        range 10.14.2.100 10.14.2.101;
        option routers 10.14.2.1;
        option broadcast-address 10.14.2.255;
        option domain-name-servers 10.14.3.3;
    }
    
    subnet 10.14.3.0 netmask 255.255.255.0 {
    }
    
    subnet 10.14.4.0 netmask 255.255.255.0 {
    }
    
    subnet 10.14.5.0 netmask 255.255.255.0 {
        range 10.14.5.50 10.14.5.51;
        range 10.14.5.155 10.14.5.156;
        option routers 10.14.5.1;
        option broadcast-address 10.14.5.255;
        option domain-name-servers 10.14.3.3;
    }
    
    subnet 10.14.6.0 netmask 255.255.255.0 {
    }
    ```

- Explanation
  #### Dumbledore
  - Lakukan instalasi isc-dhcp-relay
    ```
    apt-get update
    apt-get install isc-dhcp-relay -y
    service isc-dhcp-relay start
    ```
  - Set konfigurasi /etc/default/isc-dhcp-relay dengan SERVERS mengarah ke IP DHCP Server dan INTERFACES berisi daftar interface output yang terhubung ke node lain
  - Aktifkan IP Forwarding dengan melakukan konfigurasi pada /etc/sysctl.conf
  - Lalu, `service isc-dhcp-relay restart`
  #### SeverusSnape
  - Lakukan instalasi isc-dhcp-server
    ```
    apt-get update
    apt-get install isc-dhcp-server -y
    ```
  - Atur eth0 sebagai interface jaringan yang mendukung IPv4 pada konfigurasi /etc/default/isc-dhcp-server
  - Atur konfigurasi range IP sesuai soal untuk client yang melalui switch 2 dan 5 pada konfigurasi /etc/dhcp/dhcpd.conf
    ```
    subnet 10.14.2.0 netmask 255.255.255.0 {
        range 10.14.2.64 10.14.2.65;
        range 10.14.2.100 10.14.2.101;
        option routers 10.14.2.1;
        option broadcast-address 10.14.2.255;
        option domain-name-servers 10.14.3.3;
    }
    ```
    - subnet 10.14.2.0 adalah subnet yang digunakan untuk client yang melalui switch 2.
    - 10.14.2.64 10.14.2.65 dan 10.14.2.100 10.14.2.101 adalah rentang IP Address yang akan didistribusikan dan digunakan secara dinamis.
    - 10.14.2.1 adalah IP gateway dari router menuju client yang melalui switch 2.
    - 10.14.2.255 adalah IP broadcast yang digunakan untuk client yang melalui switch 2.
    - 10.14.3.3 adalah IP dari DNS server yang digunakan untuk client yang melalui switch 2.
  - Lalu, `service isc-dhcp-server restart`
  #### Client
  - Untuk pengecekan, ketik `ip a`, kemudian lihat `inet eth0`nya
  
<br>

## Soal 3

> Khusus untuk HermioneGranger yang berada di switch 1 mendapat range IP dari
[Prefix IP].1.10 - [Prefix IP].1.15 dan [Prefix IP].1.20 - [Prefix IP].1.25

> Khusus untuk ChoChang yang berada di switch 6 mendapat range IP dari 
[Prefix IP].6.10 - [Prefix IP].6.15 dan [Prefix IP].6.20 - [Prefix IP].6.25


> _HermioneGranger, who is on switch 1, is assigned the IP range from [Prefix IP].1.10 - [Prefix IP].1.15 and [Prefix IP].1.20 - [Prefix IP].1.25._

> _ChoChang, who is on switch 6, is assigned the IP range from [Prefix IP].6.10 - [Prefix IP].6.15 and [Prefix IP].6.20 - [Prefix IP].6.25._

**Answer:**

- Screenshot

  ![image](https://github.com/user-attachments/assets/8dd47162-814c-4923-82de-807bab2d26af)
  ![image](https://github.com/user-attachments/assets/5311a96e-2b2e-48da-b9b1-f607e9807f20)

- Configuration
  #### HermioneGranger dan ChoChang
  - Konfigurasi /etc/network/interfaces
    ```
    auto eth0
    iface eth0 inet dhcp
    ```
  #### SeverusSnape
  - Konfigurasi /etc/dhcp/dhcpd.conf
    ```
    subnet 10.14.1.0 netmask 255.255.255.0 {
    range 10.14.1.10 10.14.1.15;
    range 10.14.1.20 10.14.1.25;
    option routers 10.14.1.1;
    option broadcast-address 10.14.1.255;
    option domain-name-servers 10.14.3.3;
    }
    
    subnet 10.14.2.0 netmask 255.255.255.0 {
        range 10.14.2.64 10.14.2.65;
        range 10.14.2.100 10.14.2.101;
        option routers 10.14.2.1;
        option broadcast-address 10.14.2.255;
        option domain-name-servers 10.14.3.3;
    }
    
    subnet 10.14.3.0 netmask 255.255.255.0 {
    }
    
    subnet 10.14.4.0 netmask 255.255.255.0 {
    }
    
    subnet 10.14.5.0 netmask 255.255.255.0 {
        range 10.14.5.50 10.14.5.51;
        range 10.14.5.155 10.14.5.156;
        option routers 10.14.5.1;
        option broadcast-address 10.14.5.255;
        option domain-name-servers 10.14.3.3;
    }
    
    subnet 10.14.6.0 netmask 255.255.255.0 {
        range 10.14.6.10 10.14.6.15;
        range 10.14.6.20 10.14.6.25;
        option routers 10.14.6.1;
        option broadcast-address 10.14.6.255;
        option domain-name-servers 10.14.3.3;
    }
    ```
- Explanation
  #### HermioneGranger dan ChoChang
  - Buat konfigurasi IP menjadi dinamis dengan mengatur konfigurasi /etc/network/interfaces
  - Lalu, restart node
  #### SeverusSnape
  - Atur konfigurasi range IP sesuai soal untuk HermioneGranger dan ChoChang pada konfigurasi /etc/dhcp/dhcpd.conf
  - Lalu, `service isc-dhcp-server restart`
  #### HermioneGranger dan ChoChang
  - Untuk pengecekan, ketik `ip a`, kemudian lihat `inet eth0`nya

<br>

## Soal 4

> Menetapkan batasan waktu untuk DHCP server dalam peminjaman alamat IP untuk client melalui switch 2 selama 5 menit sedangkan client yang melalui switch 5 selama 20 menit. Untuk switch 1 dan switch 6 memiliki batas waktu 10 menit. Alokasi waktu maksimal peminjaman alamat IP selama 100 menit. 

> _The DHCP server's lease time for IP addresses is set as follows: Clients connected through switch 2 have a lease time of 5 minutes, Clients connected through switch 5 have a lease time of 20 minutes, Switches 1 and 6 have a lease time of 10 minutes, The maximum lease time for IP addresses is set at 100 minutes._

**Answer:**

- Screenshot

  ![image](https://github.com/user-attachments/assets/23a7818e-b738-4081-b088-dcf68b9520aa)
  ![image](https://github.com/user-attachments/assets/b41ea0d3-c99c-4134-864e-6ce680248b86)
  ![image](https://github.com/user-attachments/assets/b3df5a23-a3ce-461f-950e-f64c228d9690)
  ![image](https://github.com/user-attachments/assets/e1fc852a-fce6-496e-b380-c8264b76024a)
  ![image](https://github.com/user-attachments/assets/37473f5d-f998-448a-b852-7f3f1f573e06)
  ![image](https://github.com/user-attachments/assets/0b600056-5823-4414-add8-a0a999e4ca6f)

- Configuration
  #### SeverusSnape
  - Konfigurasi /etc/dhcp/dhcpd.conf
    ```
    subnet 10.14.1.0 netmask 255.255.255.0 {
    range 10.14.1.10 10.14.1.15;
    range 10.14.1.20 10.14.1.25;
    option routers 10.14.1.1;
    option broadcast-address 10.14.1.255;
    option domain-name-servers 10.14.3.3;
    default-lease-time 600;
    max-lease-time 6000;
    }
    
    subnet 10.14.2.0 netmask 255.255.255.0 {
        range 10.14.2.64 10.14.2.65;
        range 10.14.2.100 10.14.2.101;
        option routers 10.14.2.1;
        option broadcast-address 10.14.2.255;
        option domain-name-servers 10.14.3.3;
        default-lease-time 300;
        max-lease-time 6000;
    }
    
    subnet 10.14.3.0 netmask 255.255.255.0 {
    }
    
    subnet 10.14.4.0 netmask 255.255.255.0 {
    }
    
    subnet 10.14.5.0 netmask 255.255.255.0 {
        range 10.14.5.50 10.14.5.51;
        range 10.14.5.155 10.14.5.156;
        option routers 10.14.5.1;
        option broadcast-address 10.14.5.255;
        option domain-name-servers 10.14.3.3;
        default-lease-time 1200;
        max-lease-time 6000;
    }
    
    subnet 10.14.6.0 netmask 255.255.255.0 {
        range 10.14.6.10 10.14.6.15;
        range 10.14.6.20 10.14.6.25;
        option routers 10.14.6.1;
        option broadcast-address 10.14.6.255;
        option domain-name-servers 10.14.3.3;
        default-lease-time 600;
        max-lease-time 6000;
    }
    ```

- Explanation
  #### SeverusSnape
  - Atur lease time sesuai soal untuk tiap node yang melalui switch pada konfigurasi /etc/dhcp/dhcpd.conf
    ```
    Switch 2 -> 5 menit = 300 detik
    Switch 5 -> 20 menit = 1200 detik
    Switch 1 dan 6 -> 10 menit = 600 detik
    Waktu maksimal peminjaman alamat IP -> 100 menit = 6000 detik
    ```
    ```
    default-lease-time 600;
    max-lease-time 6000;
    ```
    - default-lease-time adalah lama waktu DHCP server meminjamkan IP Address dalam satuan detik.
    - max-lease-time adalah waktu maksimal yang di alokasikan untuk peminjaman IP oleh DHCP server dalam satuan detik.
  - Lalu, `service isc-dhcp-server restart`
  #### Node yang dinamis
  - Untuk pengecekan, buka web console baru tiap node yang dinamis

<br>

## Soal 5

> Memastikan bahwa semua CLIENT, HermioneGranger, dan ChoChang harus menggunakan konfigurasi dari DHCP server, menerima DNS dari Professor McGonagall dan dapat akses internet. Khusus untuk HermioneGranger dan ChoChang mendapatkan IP Statis dari DHCP dengan [Prefix IP].x.14. hint: fixed address


> _Ensure that all CLIENT, HermioneGranger, and ChoChang use DHCP server configurations, receive DNS from Professor McGonagall, and can access the internet. HermioneGranger and ChoChang must receive static IPs from DHCP with the address [Prefix IP].x.14 (hint: fixed address)._

**Answer:**

- Screenshot

  ![image](https://github.com/user-attachments/assets/db0657be-f242-4449-a437-311b033ee07d)
  ![image](https://github.com/user-attachments/assets/6e770f53-84f7-4afe-a604-dde23c563cb6)
  ![image](https://github.com/user-attachments/assets/52ee64b9-4f35-4892-9900-b3768ce48eff)
  ![image](https://github.com/user-attachments/assets/4c428a45-a4e8-44f6-b2e4-9f83356f3aba)
  ![image](https://github.com/user-attachments/assets/56aa2793-ab64-49a7-aafd-4063a3248324)
  ![image](https://github.com/user-attachments/assets/4bb61a46-519d-413a-a746-f2b279e5fc1b)

- Configuration
  #### HermioneGranger
  - Konfigurasi /etc/network/interfaces
    ```
    auto eth0
    iface eth0 inet dhcp
    hwaddress ether 8a:31:02:b5:99:e1
    ```
  #### ChoChang
  - Konfigurasi /etc/network/interfaces
    ```
    auto eth0
    iface eth0 inet dhcp
    hwaddress ether ba:08:1b:85:6f:20
    ```
  #### McGonagall
  - Konfigurasi /etc/bind/named.conf.options
    ```
    options {
            directory "/var/cache/bind";
    
            forwarders {
                    192.168.122.1;
            };
      
            // dnssec-validation auto;
            allow-query{ any; };
            auth-nxdomain no;
            listen-on-v6 { any; };
    };
    ```
  #### SeverusSnape
  - Konfigurasi /etc/dhcp/dhcpd.conf
    ```
    subnet 10.14.1.0 netmask 255.255.255.0 {
        range 10.14.1.10 10.14.1.15;
        range 10.14.1.20 10.14.1.25;
        option routers 10.14.1.1;
        option broadcast-address 10.14.1.255;
        option domain-name-servers 10.14.3.3;
        default-lease-time 600;
        max-lease-time 6000;
    }

    subnet 10.14.2.0 netmask 255.255.255.0 {
        range 10.14.2.64 10.14.2.65;
        range 10.14.2.100 10.14.2.101;
        option routers 10.14.2.1;
        option broadcast-address 10.14.2.255;
        option domain-name-servers 10.14.3.3;
        default-lease-time 300;
        max-lease-time 6000;
    }
    
    subnet 10.14.3.0 netmask 255.255.255.0 {
    }
    
    subnet 10.14.4.0 netmask 255.255.255.0 {
    }
    
    subnet 10.14.5.0 netmask 255.255.255.0 {
        range 10.14.5.50 10.14.5.51;
        range 10.14.5.155 10.14.5.156;
        option routers 10.14.5.1;
        option broadcast-address 10.14.5.255;
        option domain-name-servers 10.14.3.3;
        default-lease-time 1200;
        max-lease-time 6000;
    }
    
    subnet 10.14.6.0 netmask 255.255.255.0 {
        range 10.14.6.10 10.14.6.15;
        range 10.14.6.20 10.14.6.25;
        option routers 10.14.6.1;
        option broadcast-address 10.14.6.255;
        option domain-name-servers 10.14.3.3;
        default-lease-time 600;
        max-lease-time 6000;
    }

    host HermioneGranger {
        hardware ethernet 8a:31:02:b5:99:e1;
        fixed-address 10.14.1.14;
    }
      
    host ChoChang {
        hardware ethernet ba:08:1b:85:6f:20;
        fixed-address 10.14.6.14;
    }
    ```
- Explanation
  #### HermioneGranger & ChoChang
  - Set hwaddress agar tidak berubah-ubah dengan melakukan konfigurasi /etc/network/interfaces
   #### Mcgonagall
  - Atur konfigurasi agar semua node yang dinamis bisa terhubung ke internet dengan melakukan konfigurasi pada /etc/bind/named.conf.options
  - Lalu, `service named restart`
  #### SeverusSnape
  - Menambahkan konfigurasi berikut agar HermioneGranger dan ChoChang mendapatkan IP Statis pada /etc/dhcp/dhcpd.conf
    ```
    host HermioneGranger {
    hardware ethernet 8a:31:02:b5:99:e1;
    fixed-address 10.14.1.14;
    }
    
    host ChoChang {
        hardware ethernet ba:08:1b:85:6f:20;
        fixed-address 10.14.6.14;
    }
    ```
  - Lalu, service isc-dhcp-server restart
  #### HermioneGranger & ChoChang
  - Restart node
  #### Client, HermioneGranger, dan ChoChang
  - Untuk melakukan pengecekan, ping google.com

<br>

## Soal 6

> Dimulai dari asrama Gryffindor yang menjadi PHP worker, mereka harus melakukan deployment untuk website berikut menggunakan PHP 7.4.

> _The Gryffindor house, represented by the PHP workers, must deploy the following website using PHP 7.4._

**Answer:**

- Screenshot

  ![image](https://github.com/user-attachments/assets/35824019-4d55-4e73-8516-703b9d7f779a)

- Configuration
  #### PHP Worker
  - Konfigurasi /etc/nginx/sites-available/gryffindor.hogwarts.A13.com
    ```
      server {
    	listen 80;
    	root /var/www/jarkom;
    
    	index index.php;
    	server_name gryffindor.hogwarts.A13.com;
    
    	location / {
    		try_files $uri $uri/ /index.php?$query_string;
    	}
    	
    	location ~ \.php$ {
    		include snippets/fastcgi-php.conf;
    		fastcgi_pass unix:/var/run/php/php7.4-fpm.sock;
    	}
    
    	error_log /var/log/nginx/error.log;
    	access_log /var/log/nginx/access.log;
    }
    ```
- Explanation
  #### PHP Worker
  - Lakukan instalasi nginx, php, dan unzip
    ```
    apt-get update
    apt-get install lynx
    apt-get install nginx -y
    service nginx start
    apt-get install php php-fpm -y
    apt install unzip -y
    ```
  - Buat direktori jarkom dan download file yang diperlukan
    ```
    mkdir /var/www/jarkom
    URL_ZIP="https://drive.google.com/uc?export=download&id=17R4Zcxm3emHq21WdMJzSfCxO8FHqvATM"
    wget --no-check-certificate -O web-modul-3.zip $URL_ZIP
    unzip web-modul-3.zip -d web
    cp -r web/* /var/www/jarkom
    rm -rf web-modul-3.zip web
    ```
  - Set konfigurasi untuk deployment website di /etc/nginx/sites-available/gryffindor.hogwarts.A13.com
  - konfigurasi nginx dan pastikan konfigurasi nginx valid
    ```
    ln -s /etc/nginx/sites-available/gryffindor.hogwarts.A13.com /etc/nginx/sites-enabled
    rm -f /etc/nginx/sites-enabled/default
    
    service php7.4-fpm start
    service nginx reload
    service nginx restart
    
    nginx -t
    ```
  #### Client
  - Lakukan instalasi-instalasi
    ```
    apt-get update
    apt-get install lynx -y
    apt-get install htop -y
    apt-get install apache2-utils -y
    apt-get install nginx -y
    ```
  - Untuk melakukan pengecekan, `lynx gryffindor.hogwarts.A13.com`
    
<br>

## Soal 7

> Khusus perlombaan ini, Voldemort sudah jinak dan dia menjadi load balancer untuk para penghuni asrama Gryffindor yang menjadi worker PHP. Aturlah agar Voldemort dapat membagi pekerjaan kepada worker PHP secara optimal. Sebagai pengetesan awal, terapkan algoritma round robin dan lakukan test index.php menggunakan apache benchmark dengan 1000 request dan 100 request/second. Lakukan test sebanyak 3 kali lalu hitung rata-rata dan standar deviasi dari time/request

> _Voldemort, who is now reformed, becomes the load balancer for the Gryffindor PHP workers. Optimize Voldemort to distribute tasks to the PHP workers. For the initial test, apply the round-robin algorithm and test it to the index.php page using Apache Benchmark with 1,000 requests and 100 requests/second. Do the test 3 times and calculate the mean and standard deviation of time/request._

**Answer:**

- Screenshot

  ![f2d34503-7c81-4ba7-94e4-7857f501ed52](https://github.com/user-attachments/assets/61d91a56-0b21-4a63-8676-04792ef4bc43)
  ![94e2a677-c93d-4b80-844c-7f509fa4c0a0](https://github.com/user-attachments/assets/2fc4c607-bea2-4205-b5b2-bcd255081601)
  ![2997c797-813f-4636-93f2-3c5f9c6c82a7](https://github.com/user-attachments/assets/12b65e1a-a5bc-41bf-b473-8146ebfa2dfe)

- Configuration
  #### Voldemort
  - Konfigurasi /etc/resolv.conf
    ```
    nameserver 10.14.3.3
    ```
  - Konfigurasi /etc/nginx/sites-available/gryffindor.hogwarts.A13.com
    ```
    upstream worker {
    server 10.14.1.2;
    server 10.14.1.3;
    server 10.14.1.14;
    }
    
    server {
        listen 80;
        server_name gryffindor.hogwarts.A13.com;
        location / {
            proxy_pass http://worker;
        }
    }
    ```
  
- Explanation
  #### Voldemort
  - Set nameserver menuju IP DNS Server pada konfigurasi /etc/resolv.conf
  - Lakukan instalasi nginx
    ```
    apt-get update
    apt-get install nginx -y
    service nginx start
    ```
  - Set konfigurasi untuk Load Balancer di /etc/nginx/sites-available/gryffindor.hogwarts.A13.com
  - Konfigurasi nginx
    ```
    ln -s /etc/nginx/sites-available/gryffindor.hogwarts.A13.com /etc/nginx/sites-enabled/
    rm /etc/nginx/sites-enabled/default
    
    service nginx restart
    ```
   - Lakukan instalasi untuk pengecekan htop
    ```
    apt-get install apache2-utils htop
    ```
  - Lalu, jalankan htop, `htop`
  #### Client
  - Lakukan instalasi untuk pengecekan menggunakan apache benchmark
    ```
    apt-get install apache2-utils -y
    ```
  - Lakukan testing dengan apache benchmark sebanyak tiga kali
    ```
    ab -n 1000 -c 100 -r http://gryffindor.hogwarts.A13.com/
    ```
  #### Perhitungan rata-rata dan standar deviasi terdapat pada laporan.

<br>

## Soal 8

> Dalam penilaian akhir tahun ini, dibutuhkan algoritma terbaik, cobalah tes 3 algoritma load balancer dengan menggunakan jmeter. Jmeter perlu melakukan login, akses home, dan terakhir logout. Lakukan test dengan 300 thread dan 3 sec ramp up period. Lakukan test sebanyak 3 kali per algoritma, lalu hitung rata-rata dan standar deviasi dari response time. (username: wingardium, password: leviosa)


> _For the final assessment, try three different load-balancing algorithms using JMeter with 300 threads and a 3-second ramp-up period. Jmeter have to be able to login, access homepage, and logout. Do the test 3 times for each algorithm, then calculate the mean and standard deviation of response time. (username: wingardium, password: leviosa)_

**Answer:**

- Screenshot
  ![Screenshot (2058)](https://github.com/user-attachments/assets/207fa89e-13ce-4f5a-949e-6152edf2c249)
  ![Screenshot 2024-10-25 212538](https://github.com/user-attachments/assets/cd256031-13e3-416a-8f98-76c0b0e70731)

  **Gambar Lengkap ada pada laporan testing**

- Configuration
  #### Jmeter
  - Set up jmeter mengikuti modul [jmeter](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/tree/master/Modul-3/Jmeter)
  - Buat testplan untuk login (HTTP Request-POST), home (HTTP Request-GET), dan logout (HTTP Request-GET) pada jmeter
  - Jika sudah selesai set up testplan, simpan testplan dalam format .jmx
  - Gambar di bawah ini set up Jmeter di bawah ini 
  ![image](https://github.com/user-attachments/assets/6b3f9b15-0fe5-4b86-a0b8-6dd7d72ce565)
  ![image](https://github.com/user-attachments/assets/a63e6730-b5a3-453c-9c9c-f340eb652c6f)
  ![image](https://github.com/user-attachments/assets/7cc7171a-2b3a-44da-b8fa-6e3c29fe8184)
  ![image](https://github.com/user-attachments/assets/b0088c9b-af73-4e09-ad0f-834c2b2e3305)


  #### Voldemort
  - Konfigurasi pada `/etc/resolv.conf`
    ```
    nameserver 10.14.3.3
    ```
  - Konfigurasi pada `/etc/nginx/sites-available/gryffindor.hogwarts.A13.com` untuk Least-connection Algorithm
    ```
    upstream worker {
          least_conn;
          server 10.14.1.2;
          server 10.14.1.3;
          server 10.14.1.14;
  	}	
  
    server {
      listen 80;
      server_name gryffindor.hogwarts.A13.com;
      location / {
          proxy_pass http://worker;
      }
    }
    ```
  - Konfigurasi pada `/etc/nginx/sites-available/gryffindor.hogwarts.A13.com` untuk IP Hash Algorithm
    ```
    upstream worker {
    ip_hash;
    server 10.14.1.2;
    server 10.14.1.3;
    server 10.14.1.14;
    }	
    
    server {
        listen 80;
        server_name gryffindor.hogwarts.A13.com;
        location / {
            proxy_pass http://worker;
        }
    }
    ```
  - Konfigurasi pada `/etc/nginx/sites-available/gryffindor.hogwarts.A13.com` untuk Generic Hash Algorithm
    ```
    upstream worker {
      hash $request_uri consistent;
      server 10.14.1.2;
    server 10.14.1.3;
    server 10.14.1.14;
    }
    
    server {
        listen 80;
        server_name gryffindor.hogwarts.A13.com;
        location / {
            proxy_pass http://worker;
        }
    }
    ```
  - Konfigurasi .jmx pada `apache-jmeter-5.6.3/bin`
    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <jmeterTestPlan version="1.2" properties="5.0" jmeter="5.6.3">
      <hashTree>
        <TestPlan guiclass="TestPlanGui" testclass="TestPlan" testname="Test Plan">
          <elementProp name="TestPlan.user_defined_variables" elementType="Arguments" guiclass="ArgumentsPanel" testclass="Arguments" testname="User Defined Variables">
            <collectionProp name="Arguments.arguments"/>
          </elementProp>
        </TestPlan>
        <hashTree>
          <ThreadGroup guiclass="ThreadGroupGui" testclass="ThreadGroup" testname="Thread Group">
            <intProp name="ThreadGroup.num_threads">300</intProp>
            <intProp name="ThreadGroup.ramp_time">3</intProp>
            <boolProp name="ThreadGroup.same_user_on_next_iteration">true</boolProp>
            <stringProp name="ThreadGroup.on_sample_error">continue</stringProp>
            <elementProp name="ThreadGroup.main_controller" elementType="LoopController" guiclass="LoopControlPanel" testclass="LoopController" testname="Loop Controller">
              <stringProp name="LoopController.loops">1</stringProp>
              <boolProp name="LoopController.continue_forever">false</boolProp>
            </elementProp>
          </ThreadGroup>
          <hashTree>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="HTTP Request">
              <stringProp name="HTTPSampler.domain">gryffindor.hogwarts.A13.com</stringProp>
              <stringProp name="HTTPSampler.protocol">http</stringProp>
              <stringProp name="HTTPSampler.path">/php/login.php</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <stringProp name="HTTPSampler.method">POST</stringProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.postBodyRaw">false</boolProp>
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" testname="User Defined Variables">
                <collectionProp name="Arguments.arguments">
                  <elementProp name="username" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.value">wingardium</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                    <stringProp name="Argument.name">username</stringProp>
                  </elementProp>
                  <elementProp name="password" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.value">leviosa</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                    <stringProp name="Argument.name">password</stringProp>
                  </elementProp>
                </collectionProp>
              </elementProp>
            </HTTPSamplerProxy>
            <hashTree/>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="HTTP Request">
              <stringProp name="HTTPSampler.domain">gryffindor.hogwarts.A13.com</stringProp>
              <stringProp name="HTTPSampler.protocol">http</stringProp>
              <stringProp name="HTTPSampler.path">/php/home.php</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.postBodyRaw">false</boolProp>
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" testname="User Defined Variables">
                <collectionProp name="Arguments.arguments"/>
              </elementProp>
            </HTTPSamplerProxy>
            <hashTree/>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="HTTP Request">
              <stringProp name="HTTPSampler.domain">gryffindor.hogwarts.A13.com</stringProp>
              <stringProp name="HTTPSampler.protocol">http</stringProp>
              <stringProp name="HTTPSampler.path">/php/logout.php</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.postBodyRaw">false</boolProp>
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" testname="User Defined Variables">
                <collectionProp name="Arguments.arguments"/>
              </elementProp>
            </HTTPSamplerProxy>
            <hashTree/>
          </hashTree>
        </hashTree>
      </hashTree>
    </jmeterTestPlan>
    ```

- Explanation
  #### Client
  - Lakukan instalasi jmeter dengan mengawali mendownload java
    ```
    apt-get install openjdk-11-jre
    ```
  - Cek, apakah java berhasil diinstall
    ```
    java -version
    ```
  - Jika berhasil, selanjutnya melakukan instalasi (download dan unzip) jmeter
    ```
    apt install unzip -y

    wget https://dlcdn.apache.org//jmeter/binaries/apache-jmeter-5.6.3.zip

    unzip apache-jmeter-5.6.3.zip
    rm -f apache-jmeter-5.6.3.zip
    ```
  - Masuk ke directory `apache-jmeter-5.6.3/bin`
  - Buat file baru dengan format .jmx untuk menyimpan testplan yang dibuat pada aplikasi jmeter
    ```
    nano jmeterno8.jmx
    ```
  - Copy dan simpan isi testplan ke dalam file tersebut
  #### Voldemort
  - Set nameserver menuju IP DNS Server pada konfigurasi `/etc/resolv.conf`
  - Instalasi nginx
    ```
    apt-get update
    apt-get install nginx -y
    service nginx start
    ```
  - Konfigurasi nginx
    ```
    ln -s /etc/nginx/sites-available/gryffindor.hogwarts.A13.com /etc/nginx/sites-enabled/
    rm /etc/nginx/sites-enabled/default
    
    service nginx restart
    ```
  #### Client
  - Masuk ke directory `apache-jmeter-5.6.3/bin/`
  - Jalankan perintah berikut pada terminal
    ```
    ./jmeter -n -t jmeterno8.jmx -l result-no8.csv -e -o ../../jmeter_no_8
    ```
  - Setelah perintah dijalankan, otomatis pada root akan ada folder bernama `jmeter_no_8`. Karena masih berbentuk folder, kita harus melakukan zip agar bisa didownload dan dilihat isi dari hasil testing jmeter tersebut
    ```
    apt-get install zip
    zip -r jmeter_no_8.zip jmeter_no_8/
    rm -r jmeter_no_8/
    ```
  - Maka akan terbentuk file zip `jmeter_no_8.zip`
  - Masuk ke website [webhook.site](https://webhook.site/). Copy link yang ada pada `Your Unique URL`
  - Kembali ke terminal, dan jalankan perintah berikut untuk melakukan download file zip tersebut
    ```
    curl -X POST -F "file=@jmeter_no_8.zip" [Your Unique URL]
    ```
  - Maka otomatis file akan terdownload dan masuk pada website webhook.
  - Download file zip, kemudian ekstrak, dan jalankan `index.html`
  - Semua statistik akan terlihat pada browser
   #### Client 
  - Lakukan instalasi untuk pengecekan menggunakan apache benchmark
    ```
    apt-get install apache2-utils -y
    ```
  - Lakukan testing dengan apache benchmark sebanyak tiga kali
    ```
    ab -n 300 -c 3 -r http://gryffindor.hogwarts.A13.com/
    ```
  
<br>

## Soal 9

> Tidak semua IP dapat akses asrama Gryffindor melalui IP Load balancer Voldemort. Untuk itu, berikan akses pada load balancer Voldemort. Autentikasi akan memerlukan username: “jarkom” dan password: “modul3”. Simpan file autentikasi pada  /etc/nginx/secretchamber 

> _Not all IPs can access Gryffindor's house through Voldemort’s load balancer. Grant access to the Voldemort load balancer. Authentication will require username: “jarkom” and password: “modul3”. Save the authentication file in /etc/nginx/secretchamber._

**Answer:**

- Screenshot

  ![image](https://github.com/user-attachments/assets/bd3ac1d2-93ed-4976-87e2-03460f4a4900)
  ![image](https://github.com/user-attachments/assets/3bebe3f2-d626-49fe-901c-a1d8d250487a)
  ![image](https://github.com/user-attachments/assets/6a59386c-32a9-47e3-9662-8791acacb669)
  ![image](https://github.com/user-attachments/assets/f3ba1e05-e5da-49d9-96be-a536bc2f475e)

- Configuration
  #### Voldemort
  - Konfigurasi /etc/nginx/sites-available/gryffindor.hogwarts.A13.com
    ```
    upstream worker {
      server 10.14.1.2;
      server 10.14.1.3;
      server 10.14.1.14;
    }
    
    server {
        listen 80;
        server_name gryffindor.hogwarts.A13.com;
    
    location / {
      	satisfy any;
        allow 10.14.4.3; 
      
        deny all; 
        
        auth_basic "Restricted"; 
        auth_basic_user_file /etc/nginx/secretchamber/.htpasswd;

        proxy_pass http://worker;
        }
    }
    ```
- Explanation
  #### Voldemort
  - Lakukan instalasi yang diperlukan
    ```
    apt-get update
    apt-get install lynx
    apt-get install apache2-utils -y
    ```
  - Buat direktori secretchamber dan atur uname password pada .htpasswd
    ```
    mkdir /etc/nginx/secretchamber
    htpasswd -c -b /etc/nginx/secretchamber/.htpasswd jarkom modul3
    ```
  - Menambahkan konfigurasi untuk autentikasi pada /etc/nginx/sites-available/gryffindor.hogwarts.A13.com
    ```
    auth_basic "Restricted"; 
    auth_basic_user_file /etc/nginx/secretchamber/.htpasswd;
    ```
  - Lalu, `service nginx restart`
  #### Client
  - Lakukan pengecekan dengan lynx gryffindor.hogwarts.A13.com

<br>

## Soal 10

> Setelah menambahkan autentikasi ke Gryffindor, coba testing ulang dengan menggunakan JMeter (algoritma round robin) serta skenario, thread, dan ramp up period yang sama seperti no 8 (300 thread, 3 sec ramp up period, login-home-logout). Kali ini, coba juga jumlah worker yang berbeda: 3 worker, 2 worker, dan 1 worker. 

> _After adding authentication to Gryffindor, retest using JMeter (round-robin algorithm) with the same scenario, thread, and ramp up period as number 8 (300 thread, 3 sec ramp up period, login-home-logout). This time, test with different numbers of workers: 3 workers, 2 workers, and 1 worker._

**Answer:**

- Screenshot
  ![Screenshot (2085)](https://github.com/user-attachments/assets/4ec68732-b60a-4544-9aca-2c15828c4bcc)
  ![Screenshot (2082)](https://github.com/user-attachments/assets/fb71a3b2-be9e-406c-9378-cb9bc7323a52)

  **Gambar Lengkap ada pada laporan testing**

- Configuration
  #### Jmeter
  - Set up jmeter mengikuti modul [jmeter](https://github.com/arsitektur-jaringan-komputer/Modul-Jarkom/tree/master/Modul-3/Jmeter)
  - Buat testplan untuk autentikasi (HTTP Authorization Manager) , login (HTTP Request-POST), home (HTTP Request-GET), dan logout (HTTP Request-GET) pada jmeter
  - Jika sudah selesai set up testplan, simpan testplan dalam format .jmx
  - Set up hampir sama dengan nomor 8, hanya menambahkan HTTP Authorization Manager
  ![image](https://github.com/user-attachments/assets/60479ca4-c4a5-4b89-8ec1-3efb5ce8efaf)

  #### Voldemort
  - Konfigurasi pada `/etc/resolv.conf`
    ```
    nameserver 10.14.3.3
    ```
  - Konfigurasi pada `/etc/nginx/sites-available/gryffindor.hogwarts.A13.com` untuk Round Robin Algorithm. Catatan, untuk konfigurasi ini dijalankan sebanyak tiga kali dengan menghapus worker satu per satu hingga tersisa satu worker saja. Untuk worker yang dihapus dibebaskan
    ```
    upstream worker {
    # Hapus atau comment worker satu per saty
      server 10.14.1.2;
      server 10.14.1.3;
      server 10.14.1.14;
    }
    
    server {
        listen 80;
        server_name gryffindor.hogwarts.A13.com;
            location / {
                    satisfy any;
                    allow 10.14.4.3; 
    
                    deny all; 
    
                    auth_basic "Restricted"; 
                    auth_basic_user_file /etc/nginx/secretchamber/.htpasswd;
    
                    proxy_pass http://worker;
        }
    }
    ```
  - Konfigurasi .jmx pada `apache-jmeter-5.6.3/bin`
    ```
    <?xml version="1.0" encoding="UTF-8"?>
    <jmeterTestPlan version="1.2" properties="5.0" jmeter="5.6.3">
      <hashTree>
        <TestPlan guiclass="TestPlanGui" testclass="TestPlan" testname="Test Plan">
          <elementProp name="TestPlan.user_defined_variables" elementType="Arguments" guiclass="ArgumentsPanel" testclass="Arguments" testname="User Defined Variables">
            <collectionProp name="Arguments.arguments"/>
          </elementProp>
          <boolProp name="TestPlan.functional_mode">false</boolProp>
          <boolProp name="TestPlan.serialize_threadgroups">false</boolProp>
        </TestPlan>
        <hashTree>
          <ThreadGroup guiclass="ThreadGroupGui" testclass="ThreadGroup" testname="Thread Group">
            <intProp name="ThreadGroup.num_threads">300</intProp>
            <intProp name="ThreadGroup.ramp_time">3</intProp>
            <boolProp name="ThreadGroup.same_user_on_next_iteration">true</boolProp>
            <stringProp name="ThreadGroup.on_sample_error">continue</stringProp>
            <elementProp name="ThreadGroup.main_controller" elementType="LoopController" guiclass="LoopControlPanel" testclass="LoopController" testname="Loop Controller">
              <stringProp name="LoopController.loops">1</stringProp>
              <boolProp name="LoopController.continue_forever">false</boolProp>
            </elementProp>
          </ThreadGroup>
          <hashTree>
            <AuthManager guiclass="AuthPanel" testclass="AuthManager" testname="HTTP Authorization Manager">
              <collectionProp name="AuthManager.auth_list">
                <elementProp name="" elementType="Authorization">
                  <stringProp name="Authorization.url">http://gryffindor.hogwarts.A13.com</stringProp>
                  <stringProp name="Authorization.username">jarkom</stringProp>
                  <stringProp name="Authorization.password">modul3</stringProp>
                  <stringProp name="Authorization.domain"></stringProp>
                  <stringProp name="Authorization.realm"></stringProp>
                </elementProp>
              </collectionProp>
              <boolProp name="AuthManager.controlledByThreadGroup">false</boolProp>
            </AuthManager>
            <hashTree/>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="HTTP Request">
              <stringProp name="HTTPSampler.domain">gryffindor.hogwarts.A13.com</stringProp>
              <stringProp name="HTTPSampler.protocol">http</stringProp>
              <stringProp name="HTTPSampler.path">/php/login.php</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <stringProp name="HTTPSampler.method">POST</stringProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.postBodyRaw">false</boolProp>
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" testname="User Defined Variables">
                <collectionProp name="Arguments.arguments">
                  <elementProp name="username" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.value">wingardium</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                    <stringProp name="Argument.name">username</stringProp>
                  </elementProp>
                  <elementProp name="password" elementType="HTTPArgument">
                    <boolProp name="HTTPArgument.always_encode">false</boolProp>
                    <stringProp name="Argument.value">leviosa</stringProp>
                    <stringProp name="Argument.metadata">=</stringProp>
                    <boolProp name="HTTPArgument.use_equals">true</boolProp>
                    <stringProp name="Argument.name">password</stringProp>
                  </elementProp>
                </collectionProp>
              </elementProp>
            </HTTPSamplerProxy>
            <hashTree/>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="HTTP Request">
              <stringProp name="HTTPSampler.domain">gryffindor.hogwarts.A13.com</stringProp>
              <stringProp name="HTTPSampler.protocol">http</stringProp>
              <stringProp name="HTTPSampler.path">/php/home.php</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.postBodyRaw">false</boolProp>
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" testname="User Defined Variables">
                <collectionProp name="Arguments.arguments"/>
              </elementProp>
            </HTTPSamplerProxy>
            <hashTree/>
            <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="HTTP Request">
              <stringProp name="HTTPSampler.domain">gryffindor.hogwarts.A13.com</stringProp>
              <stringProp name="HTTPSampler.protocol">http</stringProp>
              <stringProp name="HTTPSampler.path">/php/logout.php</stringProp>
              <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
              <stringProp name="HTTPSampler.method">GET</stringProp>
              <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
              <boolProp name="HTTPSampler.postBodyRaw">false</boolProp>
              <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" testname="User Defined Variables">
                <collectionProp name="Arguments.arguments"/>
              </elementProp>
            </HTTPSamplerProxy>
            <hashTree/>
          </hashTree>
        </hashTree>
      </hashTree>
    </jmeterTestPlan>
    ```

- Explanation
  #### Client
  - Karena pada nomor 8 kita telah melakukan instalasi Jmeter, kita tinggal menambahkan saja file .jmx pada `apache-jmeter-5.6.3/bin`
  - Kemudian, simpan file .jmx pada `apache-jmeter-5.6.3/bin`
  #### Voldemort
  - Set nameserver menuju IP DNS Server pada konfigurasi `/etc/resolv.conf`
  - Instalasi nginx
    ```
    apt-get update
    apt-get install nginx -y
    service nginx start
    ```
  - Konfigurasi nginx
    ```
    ln -s /etc/nginx/sites-available/gryffindor.hogwarts.A13.com /etc/nginx/sites-enabled/
    rm /etc/nginx/sites-enabled/default
    
    service nginx restart
    ```
  #### Client
  - Masuk ke directory `apache-jmeter-5.6.3/bin/`
  - Jalankan perintah berikut pada terminal
    ```
    ./jmeter -n -t jmeterno10.jmx -l result-no8.csv -e -o ../../jmeter_no_10
    ```
  - Setelah perintah dijalankan, otomatis pada root akan ada folder bernama `jmeter_no_10`. Karena masih berbentuk folder, kita harus melakukan zip agar bisa didownload dan dilihat isi dari hasil testing jmeter tersebut
    ```
    apt-get install zip
    zip -r jmeter_no_10.zip jmeter_no_10/
    rm -r jmeter_no_10/
    ```
  - Maka akan terbentuk file zip `jmeter_no_10.zip`
  - Masuk ke website [webhook.site](https://webhook.site/). Copy link yang ada pada `Your Unique URL`
  - Kembali ke terminal, dan jalankan perintah berikut untuk melakukan download file zip tersebut
    ```
    curl -X POST -F "file=@jmeter_no_10.zip" [Your Unique URL]
    ```
  - Maka otomatis file akan terdownload dan masuk pada website webhook.
  - Download file zip, kemudian ekstrak, dan jalankan `index.html`
  - Semua statistik akan terlihat pada browser
  #### Client 
  - Lakukan instalasi untuk pengecekan menggunakan apache benchmark
    ```
    apt-get install apache2-utils -y
    ```
  - Lakukan testing dengan apache benchmark sebanyak tiga kali
    ```
    ab -A jarkom:modul3 -n 300 -c 3 http://gryffindor.hogwarts.A13.com/
    ```
  
<br>

## Soal 11

> Hogwarts juga bekerjasama dengan ITS dalam perlombaan ini. Untuk itu, setiap request pada Voldemort yang mengandung /informatika pada akhir url akan di proxy passing menuju halaman https://www.its.ac.id/informatika/id/beranda/ 

> _Hogwarts has also partnered with ITS for this competition. Any request to Voldemort containing /informatika at the end of the URL should be proxied to the page at https://www.its.ac.id/informatika/id/beranda/._


**Answer:**

- Screenshot

  ![image](https://github.com/user-attachments/assets/f03f607b-963b-4495-8632-64569c8b8b2b)

- Configuration
  #### Voldemort
  - Konfigurasi /etc/nginx/sites-available/gryffindor.hogwarts.A13.com
    ```
    upstream worker {
        server 10.14.1.2;
        server 10.14.1.3;
        server 10.14.1.14;
    }
    
    server {
        listen 80;
        server_name gryffindor.hogwarts.A13.com;
    
    	location /informatika {
            		proxy_pass https://www.its.ac.id/informatika/id/beranda/;
        	}
    
        location / {
    	satisfy any;
    allow 10.14.4.3; 
    
    deny all; 
    
    auth_basic "Restricted"; 
    auth_basic_user_file /etc/nginx/secretchamber/.htpasswd;
    
            proxy_pass http://worker;
        }
    }
    ```

- Explanation
  - Menambahkan konfigurasi untuk proxy passing pada /etc/nginx/sites-available/gryffindor.hogwarts.A13.com
    ```
    	location /informatika {
            		proxy_pass https://www.its.ac.id/informatika/id/beranda/;
        	}
    ```
  - Lalu, `service nginx restart`
  #### Client
  - Lakukan pengecekan dengan lynx gryffindor.hogwarts.A13.com/informatika
    
<br>

## Soal 12

> Selain butuh autentikasi dalam pengaksesan asrama Gryffindor melalui LB Voldemort, juga perlu dibatasi dengan pembatasan IP.  LB Voldemort hanya boleh diakses oleh client dengan IP [Prefix IP].2.64, [Prefix IP].2.100, [Prefix IP].5.50, dan [Prefix IP].5.155. hint: (fixed in dulu clientnya) 


> _In addition to requiring authentication for access to Gryffindor through Voldemort’s load balancer, IP restrictions also need to be enforced. Voldemort's load balancer can only be accessed by clients with IPs: [Prefix IP].2.64, [Prefix IP].2.100, [Prefix IP].5.50, and [Prefix IP].5.155. (hint: fixed client IPs first)._

**Answer:**

- Screenshot
  - Saat IP client masih dinamis (10.14.5.156)
    ![image](https://github.com/user-attachments/assets/88c024ea-2a84-4ce3-a89a-4b2a950ff9e5)
  - Saat IP client sudah diatur (10.14.5.155)
    ![image](https://github.com/user-attachments/assets/abd7d151-963d-45ff-a4b2-0aed33b38f61)

- Configuration
  #### Voldemort
  - Konfigurasi /etc/nginx/sites-available/gryffindor.hogwarts.A13.com
    ```
    upstream worker {
        server 10.14.1.2;
        server 10.14.1.3;
        server 10.14.1.14;
    }
    
    server {
        listen 80;
        server_name gryffindor.hogwarts.A13.com;
    
    	location /informatika {
            		proxy_pass https://www.its.ac.id/informatika/id/beranda/;
        	}
    
        location / {
    allow 10.14.4.3; 
    
    satisfy all;
    
    allow 10.14.2.64; 
    allow 10.14.2.100; 
    allow 10.14.5.50; 
    allow 10.14.5.155;
    deny all; 
    
    auth_basic "Restricted"; 
    auth_basic_user_file /etc/nginx/secretchamber/.htpasswd;
    
            proxy_pass http://worker;
        }
    }
    ```
  #### SeverusSnape
  - Konfigurasi /etc/dhcp/dhcpd.conf
    ```
        subnet 10.14.1.0 netmask 255.255.255.0 {
        range 10.14.1.10 10.14.1.15;
        range 10.14.1.20 10.14.1.25;
        option routers 10.14.1.1;
        option broadcast-address 10.14.1.255;
        option domain-name-servers 10.14.3.3;
        default-lease-time 600;
        max-lease-time 6000;
    }

    subnet 10.14.2.0 netmask 255.255.255.0 {
        range 10.14.2.64 10.14.2.65;
        range 10.14.2.100 10.14.2.101;
        option routers 10.14.2.1;
        option broadcast-address 10.14.2.255;
        option domain-name-servers 10.14.3.3;
        default-lease-time 300;
        max-lease-time 6000;
    }
    
    subnet 10.14.3.0 netmask 255.255.255.0 {
    }
    
    subnet 10.14.4.0 netmask 255.255.255.0 {
    }
    
    subnet 10.14.5.0 netmask 255.255.255.0 {
        range 10.14.5.50 10.14.5.51;
        range 10.14.5.155 10.14.5.156;
        option routers 10.14.5.1;
        option broadcast-address 10.14.5.255;
        option domain-name-servers 10.14.3.3;
        default-lease-time 1200;
        max-lease-time 6000;
    }
    
    subnet 10.14.6.0 netmask 255.255.255.0 {
        range 10.14.6.10 10.14.6.15;
        range 10.14.6.20 10.14.6.25;
        option routers 10.14.6.1;
        option broadcast-address 10.14.6.255;
        option domain-name-servers 10.14.3.3;
        default-lease-time 600;
        max-lease-time 6000;
    }

    host HermioneGranger {
        hardware ethernet 8a:31:02:b5:99:e1;
        fixed-address 10.14.1.14;
    }
      
    host ChoChang {
        hardware ethernet ba:08:1b:85:6f:20;
        fixed-address 10.14.6.14;
    }
    
    host DracoMalfoy {
        hardware ethernet 4a:ec:61:f2:ff:1d;
        fixed-address 10.14.2.64;
    }
    
    
    host AstoriaGreengrass {
        hardware ethernet da:6f:3a:9d:d8:e5;
        fixed-address 10.14.2.100;
    }
    
    
    host SusanBones{
        hardware ethernet 8e:50:4c:15:87:2f;
        fixed-address 10.14.5.50;
    }
    
    
    host HannahAbbott{
        hardware ethernet 56:63:60:9f:ad:4f;
        fixed-address 10.14.5.155;
    }
    ```

- Explanation
  #### Voldemort
  - Menambahkan konfigurasi untuk pembatasan IP pada /etc/nginx/sites-available/gryffindor.hogwarts.A13.com kolom location
    ```
    satisfy all;
    
    allow 10.14.2.64; 
    allow 10.14.2.100; 
    allow 10.14.5.50; 
    allow 10.14.5.155;
    deny all; 
    ```
  - Lalu, `service nginx restart`
  #### SeverusSnape
  - Menambahkan konfigurasi untuk mengatur IP client pada /etc/dhcp/dhcpd.conf
  - Lalu, `service isc-dhcp-server restart`
  #### Client
  - Restart node
  - Lakukan pengecekan dengan lynx gryffindor.hogwarts.A13.com

<br>

## Soal 13

> Pengaturan database yang dibutuhkan dalam perlombaan ini wajib diatur di Hagrid. Pastikan pengaturan database tersebut dapat diakses oleh Lunalovegood, FiliusFlitwick, dan ChoChang dengan menggunakan username: kelompokyyy dan password: passwordyyy 

> _Database setup for this competition is managed by Hagrid. Ensure that this database can be accessed by LunaLovegood, FiliusFlitwick, and ChoChang using the username: "kelompokyyy" and password: "passwordyyy”_

**Answer:**

- Screenshot

  ![image](https://github.com/user-attachments/assets/de459fc9-d6fb-4a83-8d7d-f837c9036fc8)
  ![image](https://github.com/user-attachments/assets/914b3061-6d12-444f-8687-5ba6e65e745b)

- Configuration
  #### Hagrid
  - Konfigurasi /etc/resolv.conf
    ```
    nameserver 10.14.3.3
    ```
  - Konfigurasi /run.sh
    ```
    #!/bin/bash
    # MySQL connection parameters
    MYSQL_USER="root"
    MYSQL_PASSWORD="1234"
    # MySQL commands
    mysql -u$MYSQL_USER -p$MYSQL_PASSWORD <<
    EOF
    CREATE USER '\''kelompokA13'\''@'\''10.14.6.%'\'' IDENTIFIED BY '\''passwordA13'\'';
    CREATE USER '\''kelompokA13'\''@'\''localhost'\'' IDENTIFIED BY '\''passwordA13'\'';
    CREATE DATABASE dbkelompokA13;
    GRANT ALL PRIVILEGES ON *.* TO '\''kelompokA13'\''@'\''10.14.6.%'\'';
    GRANT ALL PRIVILEGES ON *.* TO '\''kelompokA13'\''@'\''localhost'\'';
    FLUSH PRIVILEGES;
    EOF
    ```
  - Konfigurasi /etc/mysql/my.cnf
    ```
    [mysqld]
    skip-networking=0
    skip-bind-address
    ```
- Explanation
  #### Hagrid
  - Set nameserver menuju DNS Server
  - Lakukan instalasi dan jalankan MySql
    ```
    apt-get update
    apt-get install mariadb-server -y
    service mysql start
    ```
  - Atur konfigurasi untuk MySQL pada /run.sh
  - Jalankan run.sh
  - Tambahkan konfigurasi untuk MySQL pada /etc/mysql/my.cnf
  - Lalu, `service mysql restart `
  - Lakukan pengecekan dengan `mysql -u kelompokA13 -p`
  #### Laravel Worker
  - Lakukan instalasi MySQL
    ```
    apt-get update
    apt-get install mariadb-client -y
    ```
  - Lakukan pengecekan
    ```
    mariadb --host=10.14.4.2 --port=3306 --user=kelompokA13 --password=passwordA13 dbkelompokA13 -e "SHOW DATABASES;"
    ```

<br>

## Soal 14

> Selain itu, untuk Lunalovegood, FiliusFlitwick, dan ChoChang memiliki website sesuai dengan https://github.com/lodaogos/laravel-jarkom-modul-3/tree/main  berikut. Jangan lupa melakukan instalasi PHP8.0 dan Composer! Pastikan database di Hagrid sudah ada isinya sekarang dan server Laravel sudah running di localhost!

> _Additionally, LunaLovegood, FiliusFlitwick, and ChoChang have websites following this GitHub link: Laravel Jarkom Modul 3. Install PHP 8.0 and Composer! Make sure Hagrid's data storage is populated, and the Laravel servers are running on localhost!_

**Answer:**

- Screenshot

  ![image](https://github.com/user-attachments/assets/dbd6acf6-da12-4179-b390-2ba6a742bdf3)

- Configuration
  #### Laravel Worker
  - Konfigurasi /etc/nginx/sites-available/laravel-jarkom-modul-3
    ```
    server {
        listen 80;
        root /var/www/laravel-jarkom-modul-3/public;
    
        index index.php index.html index.htm;
        server_name ravenclaw.hogwarts.A13.com;
    
        location / {
                try_files $uri $uri/ /index.php?$query_string;
        }
    
        # pass PHP scripts to FastCGI server
        location ~ \.php$ {
                include snippets/fastcgi-php.conf;
                fastcgi_pass unix:/var/run/php/php8.0-fpm.sock;
        }
    
        location ~ /\.ht {
                deny all;
        }
    
        error_log /var/log/nginx/laravel-jarkom-modul-3_error.log;
        access_log /var/log/nginx/laravel-jarkom-modul-3_access.log;
    }
    ```

- Explanation 
  #### Laravel Worker
  - Lakukan instalasi yang diperlukan
    ```
    apt-get update
    apt-get install mariadb-server
    apt-get install git
    apt-get update 
    apt-get install lynx
    apt-get install nginx  -y
    apt-get update
    apt-get install software-properties-common
    add-apt-repository ppa:ondrej/php
    apt-get update
    apt-get install php8.0-mbstring php8.0-xml php8.0-cli php8.0-common php8.0-intl php8.0-opcache php8.0-readline php8.0-mysql php8.0-fpm php8.0-curl unzip wget -y
    ```
  - Clone github dari soal
    ```
    git clone https://github.com/lodaogos/laravel-jarkom-modul-3.git
    mv laravel-jarkom-modul-3 /var/www/laravel-jarkom-modul-3
    ```
  - Install composer
    ```
    wget https://getcomposer.org/download/2.0.13/composer.phar
    chmod +x composer.phar
    mv composer.phar /usr/bin/composer
    
    cd /var/www/laravel-jarkom-modul-3
    composer update
    composer install
    ```
  - Menyesuaikan konfigurasi database dengan mengedit file .env
    ```
    cp .env.example .env
    
    echo '
    APP_NAME=Laravel
    APP_ENV=local
    APP_KEY= 
    APP_DEBUG=true
    APP_URL=http://localhost
    
    LOG_CHANNEL=stack
    LOG_DEPRECATIONS_CHANNEL=null
    LOG_LEVEL=debug
    
    DB_CONNECTION=mysql
    DB_HOST=10.14.4.2
    DB_PORT=3306
    DB_DATABASE=dbkelompokA13
    DB_USERNAME=kelompokA13
    DB_PASSWORD=passwordA13
    
    BROADCAST_DRIVER=log
    CACHE_DRIVER=file
    FILESYSTEM_DISK=local
    QUEUE_CONNECTION=sync
    SESSION_DRIVER=file
    SESSION_LIFETIME=120
    
    MEMCACHED_HOST=127.0.0.1
    
    REDIS_HOST=127.0.0.1
    REDIS_PASSWORD=null
    REDIS_PORT=6379
    
    MAIL_MAILER=smtp
    MAIL_HOST=mailpit
    MAIL_PORT=1025
    MAIL_USERNAME=null
    MAIL_PASSWORD=null
    MAIL_ENCRYPTION=null
    MAIL_FROM_ADDRESS="hello@example.com"
    MAIL_FROM_NAME="${APP_NAME}"
    
    AWS_ACCESS_KEY_ID=
    AWS_SECRET_ACCESS_KEY=
    AWS_DEFAULT_REGION=us-east-1
    AWS_BUCKET=
    AWS_USE_PATH_STYLE_ENDPOINT=false
    
    PUSHER_APP_ID=
    PUSHER_APP_KEY=
    PUSHER_APP_SECRET=
    PUSHER_HOST=
    PUSHER_PORT=443
    PUSHER_SCHEME=https
    PUSHER_APP_CLUSTER=mt1
    
    VITE_PUSHER_APP_KEY="${PUSHER_APP_KEY}"
    VITE_PUSHER_HOST="${PUSHER_HOST}"
    VITE_PUSHER_PORT="${PUSHER_PORT}"
    VITE_PUSHER_SCHEME="${PUSHER_SCHEME}"
    VITE_PUSHER_APP_CLUSTER="${PUSHER_APP_CLUSTER}"
    ' > /var/www/laravel-jarkom-modul-3/.env
    ```
  - Migrate database
    ```
    php artisan migrate:fresh
    php artisan db:seed --class=MusicsTableSeeder
    php artisan key:generate
    php artisan jwt:secret
    ```
  - Edit konfigurasi untuk deployment pada /etc/nginx/sites-available/laravel-jarkom-modul-3
  - Konfigurasi nginx lalu jalankan nginx
    ```
    ln -s /etc/nginx/sites-available/laravel-jarkom-modul-3 /etc/nginx/sites-enabled/
    rm /etc/nginx/sites-enabled/default
    
    chown -R www-data.www-data /var/www/laravel-praktikum-jarkom/storage
    service nginx restart
    service php8.0-fpm restart
    ```
  #### Client
  - Lakukan pengecekan dengan lynx menuju ip laravel worker

<br>

## Soal 15

> Lakukan testing endpoint /register sebanyak 100 request dengan 10 request/second di salah satu worker menggunakan apache benchmark dari SusanBones! Kenapa failed 99x? Jelaskan! 

> _Test the /register endpoint with 100 requests and 10 requests per second on one of the workers using Apache Benchmark from SusanBones! Why did 99 tests fail? Explain!_

**Answer:**

- Screenshot

  ![image](https://github.com/user-attachments/assets/058d555a-f37e-4880-96b8-1bc49cd38f34)
  ![image](https://github.com/user-attachments/assets/175a261c-3cd2-4258-b9d1-9f9106ce2280)

- Configuration
  #### SusanBones
  - Konfigurasi register.json
    ```
    "username": "kelompokA13",
    "password": "passwordA13"
    ```

- Explanation
  #### SusanBones
  - Lakukan instalasi yang diperlukan
    ```
    apt-get update
    apt-get install apache2-utils -y
    ```
  - Menyimpan informasi untuk register pada register.json
  - Lakukan testing dengan apache benchmark
    ```
    ab -n 100 -c 10 -p register.json -T application/json http://10.14.6.14/api/auth/register
    ```
  Hasil testing menggunakan Apache Benchmark menunjukkan 99 failed requests. Hal ini terjadi karena untuk setiap pengujian digunakan username dan password yang sama sehingga pendaftaran tidak dapat dilakukan lebih dari satu kali.
  
<br>

## Soal 16

> Lakukan juga testing pada endpoint /login sebanyak 100 request dengan 10 request/second di salah satu worker menggunakan apache benchmark dari SusanBones! Dapatkan token melalui responsenya juga!

> _Test the /login endpoint with 100 requests and 10 requests per second on one of the workers using Apache Benchmark from SusanBones! Collect the token from the response!_

**Answer:**

- Screenshot

  ![Screenshot 2024-10-30 002900](https://github.com/user-attachments/assets/6757d51e-42f2-49cd-a3b0-7351bd2a9170)
  ![Screenshot 2024-10-30 002929](https://github.com/user-attachments/assets/233c0fae-050d-462a-929f-6f38843745c7)
  - response token = "eyJ0eXA ..."
    ![image](https://github.com/user-attachments/assets/6cc492d0-b97b-458b-ba79-2bb1913b7b0b)

- Configuration
  #### SusanBones
  - Konfigurasi login.json
    ```
    "username": "kelompokA13",
    "password": "passwordA13"
    ```

- Explanation
  #### SusanBones
  - Lakukan instalasi yang diperlukan
    ```
    apt-get update
    apt-get install jq
    ```
  - Mendapatkan token
    ```
    TOKEN=$(curl -s -X POST -H "Content-Type: application/json" -d @login.json http://10.14.6.14/api/auth/login | jq -r '.token') 
    echo $TOKEN
    ```
  - Meyimpan informasi untuk login pada login.json
  - Lakukan testing dengan apache benchmark
    ```
    ab -n 100 -c 10 -p login.json -T application/json http://10.14.6.14/api/auth/login
    ```

<br>

## Soal 17

> Coba testing pada endpont /me sebanyak 100 request dengan 10 request/second di salah satu worker menggunakan apache benchmark dari SusanBones! Periksa responsenya apakah sudah sesuai dengan yang diloginkan? 

> _Test the /me endpoint with 100 requests and 10 requests per second on one of the workers using Apache Benchmark from SusanBones! Check if the response matches the logged-in user!_

**Answer:**

- Screenshot

  ![image](https://github.com/user-attachments/assets/4f9cee8b-9b42-40fc-bc38-5c0b3fba5acf)
  ![image](https://github.com/user-attachments/assets/e0fa7581-b104-4096-ac53-2fa22ac9a255)

- Configuration

  `Put your configuration in here`

- Explanation
  #### SusanBones
  - Lakukan testing dengan apache benchmark
  ```
  ab -n 100 -c 10 -H "Authorization: Bearer $TOKEN" http://10.14.6.14/api/me
  ```

<br>

## Soal 18

> Mendekati tugas akhir perlombaan ini, mari seimbangkan kekuatan LunaLovegood, FiliusFlitwick, dan ChoChang untuk bekerja sama secara adil! Buatkan load balancer Laravel dengan Dementor dan implementasikan Proxy Bind untuk mengaitkan IP dari ketiga worker tersebut!

> _As the competition nears its end, balance the workload of LunaLovegood, FiliusFlitwick, and ChoChang! Create a Laravel load balancer using Dementor and implement Proxy Bind to link the IPs of the three workers!_

**Answer:**

- Screenshot
  ![WhatsApp Image 2024-10-31 at 15 09 01](https://github.com/user-attachments/assets/d475c72c-c918-40b0-acee-4db7bf288a6c)

- Configuration
  #### Dementor
  - Konfigurasi proxy bind pada `/etc/nginx/sites-available/ravenclaw.hogwarts.A13.com`
  ```
  upstream worker {
    server 10.14.6.2;
    server 10.14.6.3;
    server 10.14.6.14;
  }
  server {
      listen 80;
      server_name ravenclaw.hogwarts.A13.com;
      location / {
          proxy_pass http://worker;
          proxy_set_header X-Real-IP $remote_addr;
          proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
          proxy_set_header Host $http_host;
      }
  
      location /LunaLovegood/ {
          proxy_bind 10.14.4.4;
          proxy_pass http://10.14.6.2/index.php;
      }
      
      location /FiliusFlitwick/ {
          proxy_bind 10.14.4.4;
          proxy_pass http://10.14.6.3/index.php;
      }
  
      location /ChoChang/ {
          proxy_bind 10.14.4.4;
          proxy_pass http://10.14.6.14/index.php;
      }
  
      error_log /var/log/nginx/error.log;
      access_log /var/log/nginx/access.log;
  }
  ```

- Explanation
  #### Dementor
  - Melakukan Instalasi yang diperlukan (PHP, nginx, php-fpm, serta apache2-utills)
    ```
    apt-get update && apt-get install nginx php php-fpm -y
    apt-get update && apt-get install apache2-utils -y
    ```
  - Jalankan nginx dan php-fpm
    ```
    service nginx start
    service php7.4-fpm start
    ```
  - Menghapus konfigurasi default nginx untuk mencegah konflik
    ```
    unlink /etc/nginx/sites-enabled/default
    rm /etc/nginx/sites-enabled/default
    ```
  - Merestart konfigurasi nginx
    ```
    ln -s /etc/nginx/sites-available/ravenclaw.hogwarts.A13.com /etc/nginx/sites-enabled/
    service nginx restart
    ```
  #### Client
  - Testing dengan command berikut
    ```
    lynx http://ravenclaw.hogwarts.A13.com/LunaLovegood
    lynx http://ravenclaw.hogwarts.A13.com/FiliusFlitwick
    lynx http://ravenclaw.hogwarts.A13.com/ChoChang
    ```

<br>

## Soal 19

> Untuk menguatkan para Laravel Worker, coba implementasikan PHP-FPM pada LunaLovegood, FiliusFlitwick, dan ChoChang. Untuk testing kinerja naikkan: 
pm.max_children
pm.start_servers
pm.min_spare_servers
pm.max_spare_servers
sebanyak tiga percobaan dan lakukan analisis testing menggunakan apache benchmark sebanyak 100 request dengan 10 request/second atau menggunakan jmeter dengan 100 threads! (Pilih 1 metode testing)

> _To strengthen the Laravel workers, implement PHP-FPM on LunaLovegood, FiliusFlitwick, and ChoChang. For performance testing, adjust: pm.max_children, pm.start_servers, pm.min_spare_servers, pm.max_spare_servers. Run the tests three times and analyze the performance by using Apache Benchmark with 100 requests at a rate of 10 requests per second or using JMeter with 100 threads! (Choose 1 testing method)_

**Answer:**

- Screenshot
  
  ![image](https://github.com/user-attachments/assets/a6f68a73-a31b-4b5b-8438-2de14093955e)
  
  Testing 1

  ![image](https://github.com/user-attachments/assets/81d5d775-3bfe-4624-ae9e-9a482f5a8a89)

  Testing 2

  ![image](https://github.com/user-attachments/assets/f680a265-2dbd-490a-8148-10ceed3fdeee)

  Testing 3
  
- Configuration
  #### Node Laravel Worker -- ChoChang, LunaLovegood, FiliusFlitwick
  - Konfigurasi Pertama
    ```
    echo '[www]
    user = www-data
    group = www-data
    listen = /run/php/php8.0-fpm.sock
    listen.owner = www-data
    listen.group = www-data
    php_admin_value[disable_functions] = exec,passthru,shell_exec,system
    php_admin_flag[allow_url_fopen] = off
    
    ; Choose how the process manager will control the number of child processes.
    
    pm = dynamic
    pm.max_children = 5
    pm.start_servers = 2
    pm.min_spare_servers = 1
    pm.max_spare_servers = 3' > /etc/php/8.0/fpm/pool.d/www.conf
    
    service php8.0-fpm restart
    ```
  - Konfigurasi Kedua
    ```
    echo '[www]
    user = www-data
    group = www-data
    listen = /run/php/php8.0-fpm.sock
    listen.owner = www-data
    listen.group = www-data
    php_admin_value[disable_functions] = exec,passthru,shell_exec,system
    php_admin_flag[allow_url_fopen] = off
    
    ; Choose how the process manager will control the number of child processes.
    
    pm = dynamic
    pm.max_children = 25
    pm.start_servers = 5
    pm.min_spare_servers = 3
    pm.max_spare_servers = 10' > /etc/php/8.0/fpm/pool.d/www.conf
    
    service php8.0-fpm restart
    ```
  - Konfigurasi Ketiga
    ```
    echo '[www]
    user = www-data
    group = www-data
    listen = /run/php/php8.0-fpm.sock
    listen.owner = www-data
    listen.group = www-data
    php_admin_value[disable_functions] = exec,passthru,shell_exec,system
    php_admin_flag[allow_url_fopen] = off
    
    ; Choose how the process manager will control the number of child processes.
    
    pm = dynamic
    pm.max_children = 50
    pm.start_servers = 8
    pm.min_spare_servers = 5
    pm.max_spare_servers = 15' > /etc/php/8.0/fpm/pool.d/www.conf
    
    service php8.0-fpm restart
    ```
- Explanation
  #### Node Laravel Worker -- ChoChang, LunaLovegood, FiliusFlitwick
  - Konfigurasi Proses Manager 1
    ```
    pm = dynamic
    pm.max_children = 5
    pm.start_servers = 2
    pm.min_spare_servers = 1
    pm.max_spare_servers = 3
    ```
  - Konfigurasi Proses Manager 2
    ```
    pm = dynamic
    pm.max_children = 25
    pm.start_servers = 5
    pm.min_spare_servers = 3
    pm.max_spare_servers = 10
    ```
  - Konfigurasi Proses Manager 3
    ```
    pm = dynamic
    pm.max_children = 50
    pm.start_servers = 8
    pm.min_spare_servers = 5
    pm.max_spare_servers = 15
    ```
  - Restart php-fpm
    ```
    service php8.0-fpm restart
    ```
  #### Client
  - Lakukan testing dengan perintah berikut
    ```
    ab -n 100 -c 10 -p login.json -T application/json http://ravenclaw.hogwarts.A13.com/api/auth/login
    ```

<br>

## Soal 20

> Yey terakhir. Menurut Professor Dumbledore, sepertinya menggunakan PHP-FPM tidak cukup untuk meningkatkan performa worker-worker. Implementasikan Least-Conn pada Dementor. Lakukan analisis pada testing kinerja menggunakan apache benchmark sebanyak 100 request dengan 10 request/second atau menggunakan jmeter dengan 100 threads! (Pilih 1 metode testing)

> _Finally, Professor Dumbledore suggests that PHP-FPM might not be enough to improve the workers' performance. Implement the Least-Conn algorithm on Dementor. Analyze the performance by using Apache Benchmark with 100 requests at a rate of 10 requests per second or using JMeter with 100 threads! (Choose 1 testing method)_

**Answer:**

- Screenshot

  ![image](https://github.com/user-attachments/assets/b456f5d2-7ce4-417a-b5db-da983a93665e)

- Configuration
  #### Dementor
  - Konfigurasi pada `/etc/nginx/sites-available/ravenclaw.hogwarts.A13.com`
    ```
    upstream worker {
    least_conn;
        server 10.14.6.2;
        server 10.14.6.3;
        server 10.14.6.14;
    }
    
    server {
        listen 80;
        server_name ravenclaw.hogwarts.A13.com;
    
            location / {
                proxy_pass http://worker;
                proxy_set_header    X-Real-IP $remote_addr;
                proxy_set_header    X-Forwarded-For $proxy_add_x_forwarded_for;
                proxy_set_header    Host $http_host;
            }
    
        error_log /var/log/nginx/error.log;
        access_log /var/log/nginx/access.log;
    }
    ```
  
- Explanation
  #### Dementor
  - Melakukan instalasi php, nginx, php-fpm, dan apache2-utils
    ```
    apt-get update && apt-get install nginx php php-fpm -y
    apt-get update && apt-get install apache2-utils -y
    ```
  - Merestart konfigurasi nginx
    ```
    ln -s /etc/nginx/sites-available/ravenclaw.hogwarts.A13.com /etc/nginx/sites-enabled/
    service nginx restart
    ```
  #### Client
  - Lakukan testing dengan perintah berikut
    ```
    ab -n 100 -c 10 -p login.json -T application/json http://ravenclaw.hogwarts.A13.com/api/auth/login
    ```

<br>
  
## Problems
Pada beberapa kasus, Hilmi mengalami issue, entah pada GNS3nya atau devicenya, sehingga beberapa konfigurasi tidak bisa dilakukan pada devicenya. Btw sampe install ulang gns :)

## Revisions (if any)
