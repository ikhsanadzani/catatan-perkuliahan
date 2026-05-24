# XFCE4 Documentation
## connect wifi
### setelah masuk ke fresh install kita sambungkan ke wifi dengan networkmanager
```
systemctl enable NetworkManager
```

```
systemctl start NetworkManager
```

```
nmtui
```

<img width="1350" height="673" alt="image" src="https://github.com/user-attachments/assets/d57070e2-ee9e-44cf-930c-3734cf2112b3" />

> pilih opsi "activate a connection"

<img width="1343" height="688" alt="image" src="https://github.com/user-attachments/assets/26d16b74-24af-481e-9d59-8e838995bc54" />

> lalu pilih wifi yang tersedia

## depedencies xfce4

```
sudo pacman -S xfce4 xfce4-goodies lightdm lightdm-gtk-greeter pipewire pipewire-pulse wireplumber pavucontrol
```

## Mengaktifkan display manager
```
sudo systemctl enable lightdm
```

```
reboot
```

### setelah reboot kita akan disambut oleh tampilan lightdm, masukan pass user dan kita masuk kedalam xfce

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/ebb5a509-0053-4f14-bf3c-4873cd5eb2ba" />

# Problem Solving ketika ada kondisi terpental terus ketika sedang di dekstop manager
- tekan `alt` `ctrl` `shift` `f2`
