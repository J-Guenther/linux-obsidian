Es gibt mehrere Möglichkeiten Apps zu installieren

### 1. APT
- Übers Terminal mit sudo apt install

### 2. Software Manager 
Ich erkläre es am Beispiel von Linux Mint, aber es lässt sich sicher genaus auf z.B. die App Stores von Ubuntu oder Pop!OS anwenden.

- Präferierte Weg, da die Software sich hier automatisch einrichtet
- Gut für zum Beispiel [[Steam]]
- Nicht empfehlenswert, wenn man Software installieren will, bei denen man mehrere Versionen nebeneinander laufen lassen will, oder bei denen man Wert auf die aller neueste Version legt (z.B. [[Godot]] oder [[Blender]])

### 3. TAR
- Tar dahin kopieren wo man die App installieren möchte
- Rechtsklick -> Extract Here...
- Readme der App folgen, wenn vorhanden
- Siehe [[#Menüverknüpfungen]]

### 4. Appimage
- Manche Apps kommen als .AppImage
- Es kann einfach gestartet werden und sollte sich selbst einrichten, inklusive Menüverknüpfung


## Menüverknüpfungen

- Damit eine App im Suchmenü/Startmenü auftaucht muss sie entweder:
	- ein .desktop Eintrag in `/usr/share/applications`
- oder:
	- man nutzt `cinnamon-menu-editor` (auf Linux Mint) und managed es per GUI
	- Alternativ gibt es auch den Editor `alacarte`