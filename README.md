# XDriverSwapper

A portable Windows utility for switching supported Xbox One USB controllers between **WinUSB** and the **factory Xbox driver**.

- Automatic detection of supported USB controllers.
- Verified Microsoft-signed factory driver and backup before switching to WinUSB.
- Factory-driver restoration with a clear completion message after verification.
- English and Hungarian interface.
- Native Windows 10/11 x64 app. No installer, .NET or PowerShell required.

## Download

**[Download XDriverSwapper v1.0.6 portable ZIP](https://github.com/NandorHU/XDriverSwapper/releases/download/v1.0.6/XDriverSwapper-Portable-v1.0.6.zip)**
([corresponding source code](https://github.com/NandorHU/XDriverSwapper/releases/download/v1.0.6/XDriverSwapper-Source.zip))

**[v1.0.7 test release - restore fix](docs/downloads/XDriverSwapper-Portable-v1.0.7.zip)**
([corresponding source code](docs/downloads/XDriverSwapper-Source-v1.0.7.zip)), see [below](#v107-test-release).

Extract the entire ZIP and launch `XDriverSwapper.exe`. Keep `libwdi.dll` beside it.
Approve the Windows administrator prompt, connect the controller with a USB data cable,
and select the driver mode you need. Unplug and reconnect the cable if requested.

The web page is in `docs/index.html`, ready for GitHub Pages. See [PUBLISH.md](PUBLISH.md).

## v1.0.7 test release

Fixes the restore result: since 1.0.3 the app could report a finished restore although Windows had not restarted the
controller, because another program kept it open. It could also remove the WinUSB package in that state.

- Success is reported only when the factory driver is really running; otherwise the app asks to close the program that
  uses the controller and to replug, verifies the device afterwards, and only then cleans up.
- A failed WinUSB installation no longer leaves its package behind; the per-package certificate is removed with it.
- New **Repair** button for leftovers created by this app only. Packages of other tools (e.g. Zadig) are not touched.

Not yet tested with a real controller; driver installation, restore and Repair need hardware validation.
`libwdi.dll` is byte-identical to 1.0.6. SHA-256: `dc7713f3c40bc5e2b5a971298bcb1d0bc31a0d8227856dfb31db08d4a863cb66`

**With 1.0.6 or older:** close the calibration tool, browser and Steam before restoring, and always replug the controller afterwards.

## Supported hardware

Microsoft VID `045E`; USB PIDs `02D1`, `02DD`, `02E3`, `02EA`, `0B00`, `0B05`, `0B12`.
Composite devices: controller interface `MI_00` only.

Bluetooth, wireless adapters, Xbox 360 and third-party controllers
are not included in this release. A compatible Microsoft-signed factory driver must
already be available in Windows before switching. Windows Update can supply it.

The app switches drivers; it does not itself calibrate the controller.
WinUSB normally prevents regular Xbox-controller use in games until the factory
driver is restored. Switching requires administrator privileges and installs a local
certificate for the generated WinUSB catalog. It does not disable Windows security settings.
A model-specific INF may later be selected for another identical controller or port.

## Recovery and testing

Backups remain in `C:\ProgramData\NandorFIX.DriverManager`, including after removing
the portable folder. Restore the factory driver before deleting the app if needed.
Only an unused package owned by this app is eligible for removal, without forced deletion.

This release was cross-compiled and its package and decision logic were checked.
The test report in the source bundle distinguishes static/build checks from actual
Windows USB testing. Not every Windows/controller configuration has been validated.
The EXE is currently not Authenticode-signed, so SmartScreen may display a warning.

## Licenses

Application code: MIT. Dynamically linked libwdi: LGPL v3 or later.
The exact corresponding library source and modifications are included in the
source bundle and portable ZIP. No Microsoft driver binaries are redistributed.
See the bundled licenses for full terms.

The website code is MIT-licensed. The provided logo is project artwork; its use
is not covered by the website code license.

---

made by **NandorFIX**  
[www.konzol-szerviz.hu](https://www.konzol-szerviz.hu/)

Version 1.0.5 adds Series USB PID 0B12, including converted One S. Firmware is never modified. No Windows USB hardware testing was available for this update.

## Experimental firmware beta

[Portable v1.1.0-beta and limitations](https://nandorhu.github.io/XDriverSwapper/firmware-beta.html). Supports One S 1708 and Series 1914 via WinUSB. Includes current-version recovery package backup (not a full flash or calibration dump). No Windows USB hardware testing was available. Stable v1.0.6 remains the default download.
