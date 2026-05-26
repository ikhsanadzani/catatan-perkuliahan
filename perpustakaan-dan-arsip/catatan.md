# luks dan lvm
## lvm on luks
> luks dlu dibikin baru lvm nya

## luks on lvm 
> lvm dulu dibikin baru luks nya


# Pembagian diks layout CIS

## tmp
```
mounting tmp:
rw,nodev,nosuid,noexec,relatime
```
## var
```
mounting var:
rw,nodev,nosuid,relatime
```
## root
```
mounting selayaknya root
```
## vtmp
```
mounting vtmp:
rw,nodev,nosuid,noexec,relatime
```
## tmpfs
```
mounting tmpfs:
rw,nodev,nosuid,noexec,relatime
```
## vlog
```
mounting vlog:
rw,nodev,nosuid,noexec,relatime
```
## vaud
```
mounting vaud:
rw,nodev,nosuid,noexec,relatime
```
## home
```
mounting home:
rw,nodev,nosuid,relatime
```

# Penjelasan setiap partisi yang dibagi pada CIS
## var
> menyimpan data dinamis, data yang terkadang bisa bertambah juga berkurang

## vlog
> mencatat log terkait komputer & aplikasi yang tidak kritikal

## vaud 
> mencatat log terkait komputer & aplikasi yang bersifat kritikal

## vtmp
> untuk menyimpan data sementara, ketika device dimatikan data yang dipartisi masih ada

## tmp
> ketika device dimatikan data hilang semua

## tmpfs 
> menyimpan semua data di dalam RAM

## Kenapa home di CIS dibagi menjadi 2?
> karena untuk memisahkan data level public & intern / administrator
 

# Penjelasan setiap atribut
## nodev
> melarang segala aktivitas device dipartisi tsb yang memiliki atribut `nodev`

## nosuid 
> tidak ada user id yang diperbolehkan untuk memodifikasi partisi yang emiliki atribut `nosuid`

## noexec
> tidak ada file yang memiliki izin eksekusi didalam partisi yang memiliki atribut `noexec`

## relatime
> mencatat waktu setiap file yang dimodifikasi






