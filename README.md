# android-hardening-and-tooling

Android Hardening & Tooling — Galaxy Z Fold 8

A working log of turning a stock, unrooted Samsung Galaxy Z Fold 8 into a
useful security and remote-access device — without root, without unlocking
the bootloader, and without breaking Knox.
The constraint is the point. Samsung has removed OEM bootloader unlocking,
so root, custom recovery, and NetHunter Lite/full are off the table. Everything
here works within that limit using ADB-level privilege via Shizuku.

Device: Samsung Galaxy Z Fold 8 (stock, locked bootloader)
Host lab: CachyOS (Arch-based)
Sources: F-Droid, IzzyOnDroid, Obtainium (GitHub releases)

Scope note: what "no root" actually means here..
Access level ~ Available? ~ Why?
Root / Magisk ~ No ~ Bootloader locked
Custom kernel (NetHunter full) ~ No ~ No custom recovery
ADB shell (uid shell) ~ Yes ~ Via Shizuku + wireless debugging
Knox container (user 150) ~ No ~ Hardware-backed isolation

Shizuku brokers ADB-level privilege to individual apps on a per-app,revocable basis. It is a least-privilege permission broker, not a root substitute.