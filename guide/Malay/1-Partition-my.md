<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Menjalankan Perisian Windows di Xiaomi Pad 5

## Pemasangan



### Prasyarat dan Kelengkapan
- Otak
- [Imej Rekoveri](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/recovery.img)

- [ADB & Fastboot](https://developer.android.com/studio/releases/platform-tools)

### Nota:
> [!Amaran]\
> Jika anda memadam atau terpadam sebarang partitions melalui diskpart, windows akan menghantar satu perintah ufs yang akan disalah tafsir di mana ia akan memadam semua ufs anda.
> Semua data anda akan dipadam! Sila lakukan data sandaran sekiranya diperlukan.
> 
> Perintah-perintah dibawah telah diuji.
> 
> Abaikan amaran `udevadm`
> 
>  Jangan jalankan perintah yang sama dua kali
> 
> JANGAN REBOOT TABLET ANDA jika anda membuat kesilapan, minta pertolongan dalam [Telegram chat](https://t.me/nabuwoa)
>
> Jangan jalankan semua perintah-perintah sekali gus, jalankan mengikut urutan!
>
> MOHON TIDAK MERUJUK DAN MENGIKUT SEBARANG VIDEO PANDUAN DI YOUTUBE ATAU PLATFORM LAIN. VIDEO-VIDEO TERSEBUT TIDAK BERDASARKAN PANDUAN TERKINI!

### Pemecahan Partition peranti anda

#### Hidupkan rekoveri melalui PC menggunakan perintah
```cmd
fastboot boot <recovery.img>
```
#### Pemecahan Partition peranti anda

> Jalankan perintah tersebut sekali lagi jika anda diarahkan

> Langkah ini adalah **tidak wajip** tetapi and boleh **menetapkan saiz pilihan mengikut skrip ini**

> Untuk menetapkan saiz pilihan, jalankan perintah ```adb shell partition [TARGET WINDOWS SIZE IN GB]```

> Pastikan anda tidak menambah perkataan GB pada akhir perintah tetapi nombor sahaja

```cmd
adb shell partition
```

#### Semak Jika Android Masih Boleh dihidupkan
Hidupkan semula tablet anda, dan pastikan Android masih befungsi
Jika ia tidak boleh dihidupkan atau animasi MIUI yang lama, gunakan rekoveri MIUI atau rekoveri-rekoveri lain untuk memadamkan data.


### [Langkah Seterusnya: Pemasangan Windows](/guide/Malay/2-Pemasangan-my.md)
