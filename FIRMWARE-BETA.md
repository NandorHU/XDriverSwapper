XDriverSwapper 1.1.0-beta - EXPERIMENTAL FIRMWARE PORT

Magyar:
A Firmware... (beta) gomb megnyitja a firmware-ablakot.
One S 1708 es Series 1914 (beleertve Serieskent jelentkezo konvertalt One S).
Csak egy kontroller legyen csatlakoztatva; WinUSB szukseges.
1. Eloszor: Kontroller adatai / Aktualis firmware-csomag mentese.
2. Valassz modellt es verziot, majd Letoltes (vagy Helyi .bin).
3. Eloellenorzes: regiok, verziok, kompatibilitas es sorozatszam.
4. A Firmware irasa kulon megerositest ker. USB-t ne huzd ki.
A mentes verziosnapshot es pontos verzioval egyezo letoltheto stock firmware-csomag.
NEM teljes flash-dump; NEM menti a kalibraciot, egyedi tanusitvanyt/adatokat.
Ha a jelenlegi verzio nincs a katalógusban, a snapshot megmarad, a csomagmentes hibat jelez.
A bootloader nem irhato; ez a beta nem vegez One S -> Series konverziot.

English:
Open Firmware... (beta) from XDriverSwapper.exe.
Only One S 1708 and Series 1914 / converted One S are enabled.
Use WinUSB and connect exactly one controller.
Save current firmware package first; select/download a version; run Preflight;
then separately confirm Write firmware. Do not disconnect USB or let the PC sleep.
Backup saves actual region versions and a matching downloadable stock package if available.
It is NOT a full flash dump and does NOT preserve calibration or unique device data.
Bootloader writes are blocked. This beta does NOT perform One S -> Series conversion.

Validation: 19 backend tests passed, including a real Series 5.22.16.0 package
against a simulated controller. Native Windows x64 binaries compiled.
Cached download SHA-256/header verification passed. No Windows execution or USB
hardware testing was possible. Online download using the Rust backend was blocked
in the development environment; the checked sample was retrieved separately.
A remote archive can change or disappear: errors stop the operation.
Hash consistency is not an independent proof of Microsoft authenticity.
The EXEs are unsigned; Windows may show SmartScreen warnings.
The driver-switch algorithm is unchanged in this beta; no instant-speed claim.

Firmware engine: bb441db/xboxctl (0BSD), with documented local changes.
Full corresponding source and dependency license notices are in XDriverSwapper-Source.zip.
No Microsoft firmware bytes are included in this archive.
