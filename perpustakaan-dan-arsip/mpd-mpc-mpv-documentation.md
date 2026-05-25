# MPV
## Depedencies yang dibutuhkan jika ingin mendownload video dari yt langsung di putar ke mpv
```
sudo pacman -S yt-dlp
```

```
nvim ~/.config/mpv/mpv.conf
```
### add value
```
script-opts=ytdl_hook-ytdl_path=/usr/bin/yt-dlp
```
> save and quit

```
mpd [link youtube]
```
