<img align="right" src="https://raw.githubusercontent.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/main/nabu.png" width="425" alt="Windows 11 Running On A Xiaomi Pad 5">

# App e istruzioni utili per Windows su Xiaomi pad 5

## Installare Microsoft Office

- Scarica questo [file](https://mega.nz/file/Q7p1XK6L#J-KPp_-MNJ8iXGqEwwZ3_sfv2tMiq_AJjUiiaX6TBrI) al tablet
  
- Disattiva Windows Defender per evitare interferenze con l'installazione
  
- Fare clic con il pulsante destro del mouse sul file iso e selezionare Monta per aprirlo in Explorer

- Fare doppio clic su AUTORUN.exe per avviare la procedura guidata di installazione
  
- Scegliere la lingua e i componenti da installare, quindi fare clic su Avvia installazione
  
- Attendere il completamento dell'installazione e dell'attivazione

- Attivare nuovamente Windows Defender

- Divertiti con Office!

 ## Attiva Windows

> Aprire PowerShell e digitare: 

  ```cmd
irm https://massgrave.dev/get | iex 
```
> Quando viene visualizzata una finestra, selezionare 1


 ## Come usare la torcia

 - Scaricare [Flashlight.7z](https://github.com/erdilS/Port-Windows-11-Xiaomi-Pad-5/releases/download/1.0/flashlight_fix.7z) e decomprimere in qualsiasi cartella

> Eseguire torcia Flashlight.exe per abilitare torcia elettrica

> Premere un tasto qualsiasi per disabilitarlo

## Abilitazione della modalità di ricarica e host USB

> [!WARNING]
>  Assicurati che tutte le modifiche del registro di sistema siano eseguite sul Mi Pad 5 stesso

> [!NOTE]
> La ricarica da C a C con un dispositivo supportato da PD è stata confermata funzionante e anche il caricabatterie da 33 W fornito da Xiaomi è confermato funzionante

- Scarica [Script da Misha803](https://t.me/droidscripts/52) per abilitarlo facilmente
 
- Oppure utilizzare il metodo tradizionale: nell'editor del Registro di sistema, modificare il valore del parametro ```RoleSwitchMode``` da ```3``` per ```1```: ```Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\ACPI\QCOM0597\0\Device Parameters```. 

