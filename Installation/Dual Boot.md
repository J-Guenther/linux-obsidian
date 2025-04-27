- Linux und Windows sollten auf zwei unterschiedlichen Festplatten installiert werden
- Am Besten wird Linux zuerst installiert und danach Windows
- Für Windows 11 muss TRM im BIOS aktiviert sein. Secure Boot im BIOS sollte aus sein für Linux. Legacy Support sollte auch aus sein, stattdessen sollte UEFI genutzt werden

## 1. Linux installieren
- USB Bootstick mit Balena Etcher erstellen
- Bei Installation Clean Install auswählen (Festplatte überschreiben). Dabei wird die Festplatte automatisch formatiert und eine EFI Partition angelegt.

## 2. Windows installieren
- USB Bootstick mit Media Creation Tool erstellen
- Andere Festplatte auswählen und dann formatieren bevor man fortfährt


## 3. Linux booten
- Entweder booted der PC automatisch in Linux oder man geht ins BIOS und wählt die Linux Festplatte zum Booten aus

## 4. GRUB Bootloader einrichten
#### 1. **GRUB aktualisieren**

Öffne ein Terminal und gib ein:
`
```bash
sudo update-grub
```

GRUB sollte automatisch Windows erkennen und einen Eintrag dafür erzeugen, z. B. „Found Windows boot manager. Adding boot menu entry for uefi firmware settings...done“.

#### 2. GRUB auf das primäre Bootlaufwerk installieren
 Jetzt GRUB auf dem Laufwerk installieren, das im BIOS/UEFI als **erste Boot-Option** gesetzt werden soll.

Wenn dein Linux-Laufwerk z. B. **nvme0n1** ist:

```bash
sudo grub-install /dev/nvme0n1
```
(⚠️ Nicht /dev/nvme0n1p1, sondern wirklich nur das Laufwerk ohne Partitionsnummer!)

#### 3. UEFI Boot-Reihenfolge anpassen

- im BIOS das Linux-Laufwerk an die erste Stelle der Boot-Order setzen


⚠️ Falls Windows nach einem Update GRUB zerstört, dann sollte es reichen im BIOS die Boot Reihenfolge wiederherzustellen. Falls nicht, dann nochmal update-grub und grub-install (die Code Snippets oben)

### 🛠️ **GRUB Timeout ändern (z. B. auf 10 Sekunden):**

1.  GRUB-Konfigurationsdatei bearbeiten:
```bash
sudo nano /etc/default/grub
```
2. Neuer Zahlenwert in Sekunden
```
GRUB_TIMEOUT=10
```
