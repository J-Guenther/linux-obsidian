Ob ein Spiel auf Linux läuft kann man hier entnehmen: https://www.protondb.com/

### Erste Schritte

- Steam über den Software-Manager installieren
- Steam->Settings->Compatibility:
	- Enable Steam Play for all other Titles
	- Run other titles with: Proton Experimental
	- Proton wird automatisch von Steam runtergeladen
- Steam->Settings->Downloads:
	- Deaktivieren: "Enable Shader Pre-caching"
-  Steam->Settings->Storage:
	- Sicherstellen, dass man /home nutzt. Siehe [[Home auf zweite SSD umziehen]]

Auf Linux Mint (vielleicht auch anderen Ubuntu Derivaten):
System Settings -> General -> Disable compositing for full-screen windows


### Fan Control
- Lüftersteuerung für CPU und Mainboard lässt man am Besten über das BIOS regeln
- Für die GPU kann man CoreCtrl nutzen `sudo apt install corectrl`
- Ein Lüfterprofil ist in diesem Obisidian Repo enthalten im Ordner `Files`
- CoreCtrl muss laufen, wenn es einen Effekt haben soll

Temp Sensor
- Um die Temperatur zu überwachen kann man PSensor nutzen (Gibts im App-Store)