## injekmon
### Tool untuk monitor libernet

Cara kerjanya, ketika IP server yang sudah ditentukan sesuai IP yang digunakan sekaran, maka akan kembali melakukan pengeceka IP, begitu seterusnya. Sebaliknya jika IP yang ditentukan tidak sesuai dengan IP yang digunakan sekarang maka libernet akan melakukan reconnect, setelah konek akan melakukan pengecekan ip berlulang.

- Cek IP server => sesuai => loop cek IP
- Cek IP server => tidak sesuai => stop libernet => start libernet => loop cek IP

### Persiapan
```bash
opkg update && opkg install bind-dig wget
```

### Instalasi

1. Download script

```bash
wget --show-progress --progress=bar:force -qO installinjekmon https://raw.githubusercontent.com/laksa19/openwrt-tools/master/injekmon/installinjekmon && chmod +x installinjekmon
```

2. Install script 

```bash
./installinjekmon
```
3. Tambahkan ke rc.local agar scriptnya berjalan saat startup, dengan cara edit file ```/etc/rc.local```, isikan baris berikut

    ```/usr/bin/injekmon```

    sebelum ```exit 0```
    
    Bisa edit dari WinSCP atau menggunakan nano langsung dari terminal.

    Edit dengan nano

    ```bash
    nano /etc/rc.local
    ```
    
    tambahkan ```/usr/bin/injekmon``` sebelum ```exit 0```
    
    kemudian tekan CTRL + X, lalu Y dan Enter.
    
 4. Reboot

### Cara penggunaan

Gunakan perintah berikut untuk menentukan ip server vpn.
```injekmon ip-server-vpn```

Contoh:
```bash
injekmon 130.31.32.33
```

### Catatan
Di Libernet tidak perlu centang PING loop dan Auto start.
