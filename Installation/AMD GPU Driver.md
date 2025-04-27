Der Linux-Kernel hat von Haus aus AMD GPU Treiber und eigentlich muss man nichts mehr machen. Falls man aber die Grafikkarte zum Rendern (Blender) oder Programmieren nutzen will, sind ein paar Schritte erforderlich.


### ROCm installation

Einfach auf diese Seite gehen und ROCm installieren (Distro auswählen und Anweisungen folgen)
https://rocm.docs.amd.com/projects/install-on-linux/en/latest/install/quick-start.html

AMDGPU driver müssen nicht installiert werden, da sie bereits im Linux Kernel sind.

⚠️ Nach der Installation: REBOOT!
⚠️ Immer darauf achten die richtige Version auszuwählen. Die Treiber für Ubuntu 20.04 funktionieren nicht auf Ubuntu 24.04!

### HIP
Damit [[Blender]] Cycles Renderer mit der GPU genutzt werden kann muss man in den Blender Settings HIP auswählen. Es sollte ausreichen, ROCm zu installieren. HIP Runtime wird mitinstalliert

Hiermit kann man testen, ob es funktioniert:
```bash
dpkg -l | grep -E 'rocm|hip'
```