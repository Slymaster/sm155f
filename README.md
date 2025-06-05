# Samsung Galaxy A15 4G Kernel Source (`SM-A155F`)

Dieses Repository enthält die modifizierten Kernelquellen für das **Samsung Galaxy A15 4G**  
(Modell: **SM-A155F**), basierend auf dem Android 5.10 Kernel aus dem offiziellen Samsung Open Source Release A155FXXU6CYE3.

---

## 🧪 Projektstatus

https://github.com/ReeViiS69/sm155f/releases/tag/v1.1.0

KernelSU-Next 1.0.7
SusFS 1.5.7

Samsung A155FXXU6CYE3  5.10.226-(currently not spoofed but with dirty removed) #1 SMP PREEMPT Fri May 09 22:46:30 UTC 2025

clone the git with:

git clone --recurse-submodules https://github.com/ReeViiS69/sm155f.git -b bys-oneui7-157susfs4ksun107

run fixesforsma155f.sh in its own location (chmod +x ./fixesforsma155f.sh)

copy the boot.img from ./maggi/ into boot.tar for flash with odin AP

Build for you on the newly released opensource code of A155FXXU6CYE3

Pull Requests, Vorschläge und Diskussionen sind herzlich willkommen!

## ✨ Ziel des Projekts

Ich arbeite daran, den Samsung-Kernel so zu erweitern, dass er Root durch folgende Features unterstützt:

- **[KernelSU-Next](https://github.com/KernelSU-Next/KernelSU-Next/releases)**  
  → Ein Fork von KernelSU mit zusätzlichen Fixes und weiterentwickelter Root-Unterstützung
- **[SusFS für KernelSU](https://gitlab.com/simonpunk/susfs4ksu/-/tree/gki-android12-5.10?ref_type=heads)**  
  → Virtuelles Dateisystem zur Kernelspace-Userspace-Interaktion, optimiert für KernelSU

---

## 🧱 Struktur

Der Samsung Kernelcode befindet sich nun im Unterordner `Kernel/` für mehr Übersichtlichkeit.

Das Orginal Samsung A155FXXS5BYC2 boot.img ist im Unterordner `samsungbootimg/`

Topjohnwus magiskboot gebaut durch magojohnji liegt im Unterordner `github.com-topjohnwu @ e791d67`

Simonpunks susfs liegt im Unterordner `gitlab.com-simonpunk @ 53eaa44`

TheWildJames ksun susfs patches liegen im Unterordner `wildplus @ 093e5bf`

KernelSU liegt zur veranschaulichung im adj4build-branch im Unterordner `Kernel/kernel-5.10/`, wird aber in anderen branchs nur live geladen beim Kompilieren

meine Anpassungen sind alle in `/fixesforsma155f.sh`. Bis auf den Samsungsusfspatch. der liegt in `wildplus @ 093e5bf/next/hotfixsamsungnamespace.patch`

---

## 🙏 Acknowledgements

Ich möchte mich besonders bei den Entwicklern der folgenden Projekte bedanken:

- **[KernelSU-Next](https://github.com/KernelSU-Next/KernelSU-Next/releases)**  
  → Vielen Dank an alle mit wirkenden für die großartige Weiterarbeit an **KernelSU-Next** sowie **KernelSU**(https://github.com/tiann/KernelSU) der grundlage, für die einfache Implementierungsmöglichkeit. Das hat die Integration dieses Features in diesem Kernel enorm vereinfacht.

- **[SusFS für KernelSU](https://gitlab.com/simonpunk/susfs4ksu/-/tree/gki-android12-5.10?ref_type=heads)**  
  → Ein riesiges Dankeschön an Simonpunk den Entwickler von **SusFS**, dessen Arbeit es mir ermöglicht hat, **SusFS** einfach durch Patchdateien zu integrieren. Das hat den Implementierungsprozess sehr viel effizienter gemacht.

- [**topjohnwu/Magisk**](https://github.com/topjohnwu/Magisk)  
  Großer Dank geht auch an [topjohnwu](https://github.com/topjohnwu) für die Entwicklung von **Magisk**, insbesondere des Submoduls `magiskboot`, das als mächtiges Werkzeug zur Manipulation und Analyse von Boot-Images dient.

- [**magojohnji/magiskboot-linux**](https://github.com/magojohnji/magiskboot-linux)  
  Vielen Dank an [magojohnji](https://github.com/magojohnji) für seine Arbeit zum erhalt der kompilierten utility `magiskboot`, welche den Umgang mit bestehenden `boot.img` Dateien deutlich erleichtert.

Ein großes Dankeschön geht an **[WildPlusKernel](https://github.com/WildPlusKernel/GKI_KernelSU_SUSFS)** –  
seine Arbeit an einem GKI-kompatiblen Kernel mit integriertem **KernelSU/-next/MKSU + SusFS** war eine wichtige Referenz für mich.  
Seiner GitHub Workflows waren grundlegend, um Verständnis für 5.10 Kernel zu erlangen. 
Ebenfalls sind seine Patchdateien unverzichtbar für die ordentliche Implementierung von KernelSU-Next! 
Danke für deinen Beitrag zur Open-Source-Kernel-Community!

---

## 📜 Lizenz

Der Samsung-Kernel in `/Kernel` steht unter der **GNU General Public License Version 2 (GPLv2)**.  
Weitere Informationen findest du in der [LICENSE](./LICENSE)-Datei.
Der Rest dieser Repository steht unter **GNU General Public License Version 3 (GPLv3)**, wenn nicht anders deklariert in den Submodulen.

BITTE KORRIGIERT MICH HIER WENN DAS NICHT STIMMT, CHATGPT HAT GEHOLFEN DIE LIZENZ ZU WÄHLEN WEIL DER SAMSUNG KERNEL DIE LIZENZ HABEN SOLL!
---

