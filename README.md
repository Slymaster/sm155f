# Samsung Galaxy A15 4G Kernel Source (`SM-A155F`)

Dieses Repository enthält die modifizierten Kernelquellen für das **Samsung Galaxy A15 4G**  
(Modell: **SM-A155F**), basierend auf dem Android 5.10 Kernel aus dem offiziellen Samsung Open Source Release A155FXXU6CYE3.

> **Fork status:** This is an experimental fork of
> [ReeViiS69/sm155f](https://github.com/ReeViiS69/sm155f). The fork currently
> adds a manually triggered GitHub Actions workflow for building a CYG1 boot
> image with KernelSU-Next and SUSFS. The inherited kernel source and
> third-party submodules remain credited to their respective authors.

---

## 🧪 Projektstatus

[Fork releases](https://github.com/Slymaster/sm155f/releases) ·
[Latest successful build](https://github.com/Slymaster/sm155f/actions/workflows/build.yml)

KernelSU-Next 1.0.9
SusFS 1.5.9

(EUX release as always)

Samsung A155FXXU6CYE3  5.10.226-android12-9-31117096 #1 SMP PREEMPT Thu May 29 08:03:09 UTC 2025

Clone this fork with its submodules:

```bash
git clone --recurse-submodules https://github.com/Slymaster/sm155f.git
```

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

Das Orginal Samsung A155FXXU6CYE3 boot.img ist im Unterordner `samsungbootimg/`

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

The repository root includes the
[GNU General Public License v2.0](./LICENSE). Third-party components,
submodules, patches, and prebuilt tools remain subject to their own license
terms. Consult the license files and notices shipped with each component
before redistributing a build.
