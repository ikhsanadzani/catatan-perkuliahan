# Dokumentasi install arch manual
## jika sudah masuk kedalam install arch linux nya langsung ikutin langkah dibawah

# CHECKING PARTISI
## jika ingin melihat partisi beserta type nya
```
lsblk -o name,fstype,size 
```
## Jika ingin melihat partisinya saja
```
lsblk
```

# MEMBAGI PARTISI
```
cfdisk /dev/[partisi] (untuk membentuk layout yg mah di install)
```

### MINIMAL PARTISI 
#### **MENYESUAIKAN DENGAN PENYIMPANAN YANG ADA**
```
boot = 1G [EFI system]
swap = 4G [linux swap]
root = 460G [linux filesystem]
```

# CONNECT WIFI

```bash
iwctl
```
---
```bash
device list
```
#### Catatan : Untuk cek driver wifi setiap laptop
---
```bash
station (driver wifi) get-network
```
#### Catatan : untuk melihat jaringan yang tersedia
---
```bash
station (driver wifi) scan
```
#### Catatan : Untuk memindai jaringan yang ada
---
```bash
station {device wifi} connect "{nama wifi}"
```
```
exit
```
#### Catatan : Untuk menghubungkan ke jaringan yang sudah ditentukan



# Memeriksa jaringan 

```bash
ping 1.1.1.1
```

