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


# Penjelasan setiap atribut
## nodev
> melarang segala aktivitas device dipartisi tsb yang memiliki atribut `nodev`

## nosuid 
> tidak ada user id yang diperbolehkan untuk memodifikasi partisi yang emiliki atribut `nosuid`

## noexec
> tidak ada file yang memiliki izin eksekusi didalam partisi yang memiliki atribut `noexec`

## relatime
> mencatat waktu setiap file yang dimodifikasi 



