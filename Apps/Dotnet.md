Damit man mit Dotnet entwickeln kann benötigt man das SDK. Hier die Anleitung für Dotnet 9.0
Ich habe die Debian Anleitung genommen, sie hat auf Linux Mint funktioniert.

https://learn.microsoft.com/en-us/dotnet/core/install/linux-debian?tabs=dotnet9#debian-12

Beispiel:
```bash
wget https://packages.microsoft.com/config/debian/12/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
rm packages-microsoft-prod.deb
```

```
sudo apt-get update && sudo apt-get install -y dotnet-sdk-9.0
```

Mit `dotnet --info` kann überprüft werden ob alles geklappt hat und ob Runtime und SDK da sind.