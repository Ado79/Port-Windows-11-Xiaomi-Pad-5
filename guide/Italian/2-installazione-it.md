<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">


# Installare Windows su mi pad 5
> [!WARNING]
> SI PREGA DI NON UTILIZZARE ALCUNA GUIDA VIDEO SU YOUTUBE O QUALSIASI ALTRA PIATTAFORMA! Quei VIDEO SONO DATATI!

## Installazione

## installare Windows

### Prerequisiti

- [Immagine Windows On Arm](https://uupdump.net/)
  
- [immagine UEFI](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_20240115.img)
  
- [Drivers](https://github.com/map220v/MiPad5-Drivers/releases/latest)

### Riavvia di nuovo la recovery per avviare l'installazione di Windows

```cmd
fastboot boot <recovery.img>
```


#### Esegui lo script msc
> Se ti chiede di eseguirlo un altra volta allora fallo.

```cmd
adb shell msc
```

### Assegna le lettere ai dischi 
  

#### Avvia il gestore delle partizioni di Windows (diskpart) 

> Quando lo Xiaomi Pad 5 viene rilevato come disco

```cmd
diskpart
```


#### Assegna la lettera `X` al volume di Windows

#### Seleziona il volume di Windows (WINNABU)
> Usa il comando `list volume` per trovarlo , é quello chiamato "WINNABU"

```diskpart
select volume <number>
```

#### Assegna la lettera X
```diskpart
assign letter=x
```

### Assegna la lettera `Y` al volume ESP 

#### Seleziona il volume ESP (ESPNABU)
> Usa il comando `list volume` per trovarlo, é quello chiamato "ESPNABU"

```diskpart
select volume <number>
```

#### Assegna la lettera Y

```diskpart
assign letter=y
```

#### Esci da diskpart:
```diskpart
exit
```

  
  

### Installa

> Sostituisci `<path/to/install.wim>` con il percorso del file install.wim,

> `install.wim` si trova nella cartella "sources" dentro la ISO di Windows
> Puoi ottenere questo file montandola o estraendola

```cmd
dism /apply-image /ImageFile:<path/to/install.wim> /index:1 /ApplyDir:X:\
```

### Installazione drivers

> È possibile scaricare i driver [qui](https://github.com/map220v/MiPad5-Drivers/releases/latest)

```cmd
Apri la cartella con i driver ed esegui OfflineUpdater.cmd
```

  

### Crea i file del bootloader (file di avvio) di Windows per l'EFI 

```cmd
bcdboot X:\Windows /s Y: /f UEFI
```

## Rimuovere la lettera di unità per ESPNABU per evitare la comparsa di una lettera di unità fantasma

```cmd
mountvol y: /d
```
 
  
## Avvia Windows

### Crea un backup dell'immagine di avvio (boot.img) esistente

```cmd
adb shell "dd if=/dev/block/platform/soc/1d84000.ufshc/by-name/boot$(getprop ro.boot.slot_suffix) of=/tmp/boot.img"
```

### Salva il backup sul computer

```cmd
adb pull /tmp/boot.img
```

### Riavvia il dispositivo nel bootloader

```cmd
adb reboot bootloader
```

### Scarica e installa l'immagine UEFI
> Scarica [immagine UEFI](https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/images/xiaomi-nabu_20240115.img)
```cmd
fastboot flash boot <path to image>
```
## Riavvia a Windows
```cmd
fastboot reboot
```
> [!NOTE]
> Al primo avvio di Windows, non vedrà alcuna rete Wi-Fi, basta riavviarlo tenendo premuto il pulsante di accensione e dopo il riavvio quando si tenta di connettersi alla rete e si vede" gelato "fare clic su" riprova " 7 volte

### Per riavviare il dispositivo in Android
> Usa il backup dell'immagine di avvio che hai salvato precedentemente sul tuo computer ed esegui il flashing da fastboot 

```cmd
fastboot flash boot boot.img
```

## Finito!
> Puoi unirti al nostro [Telegram chat](https://t.me/nabuwoa) per ricevere le ultime notizie sul progetto
## [Per il dualboot](/guide/Italian/dualboot-it.md)
