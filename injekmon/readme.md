## injekmon
### Tool untuk monitor libernet

Cara kerjanya, ketika IP server yang sudah ditentukan sesuai IP yang digunakan sekaran, maka akan kembali melakukan pengeceka IP, begitu seterusnya. Sebaliknya jika IP yang ditentukan tidak sesuai dengan IP yang digunakan sekarang maka libernet akan melakukan reconnect, setelah konek akan melakukan pengecekan ip berlulang.

- Cek IP server => sesuai => loop cek IP
- Cek IP server => tidak sesuai => stop libernet => start libernet => loop cek IP

### Instalasi

1. Download script https://raw.githubusercontent.com/laksa19/openwrt-tools/main/injekmon/injekmon
2. Edit bagian baris 6 "serverip=", sesuaikan dengan ip server masing-masing.
3. Upload ke OpenWrt taruh di ```/usr/bin```.
4. ketikkan perintah di terminal ```chmod +x /usr/bin/injekmon```.
5. Tambahkan ke rc.local agar scriptnya berjalan saat startup, dengan cara edit file ```/etc/rc.local```, isikan perintah berikut

    ```screen -AmdS injekmon /usr/bin/injekmon```

    sebelum ```exit 0```
