# AMX TrustMesh™ — Releases

Official downloads for **AMX TrustMesh**, the cryptographic document sealing and verification suite by [AMXNexus Technologies L.L.C.](https://amxnexus.com)

التنزيلات الرسمية لمنظومة **AMX TrustMesh** لختم الوثائق والتحقق منها تشفيريًا.

**[⬇ Download the latest release / تنزيل آخر إصدار](https://github.com/AMXNexus/trustmesh-releases/releases/latest)**

## Which file do I need? / أي ملف أحتاج؟

| File / الملف | For / لمن |
|---|---|
| `AMX-TrustMesh-Setup-<version>.exe` | **Windows desktop app — start here.** Installer with Start-menu shortcut and uninstaller. / **برنامج ويندوز — ابدأ من هنا.** مثبّت باختصار في قائمة ابدأ وإزالة تثبيت. |
| `AMX-TrustMesh-Desktop-<version>-windows-x64.zip` | Same desktop app without installing (portable). / نفس البرنامج بلا تثبيت (محمول). |
| `AMX-TrustMesh-Server-<version>-linux-x64.tar.gz` | Self-hosted server: core + API + verification website (Ubuntu 24.04). / الخادم للاستضافة الذاتية مع موقع التحقق. |
| `AMX-TrustMesh-<version>.apk` | Android app to verify documents by QR code. / تطبيق أندرويد للتحقق برمز QR. |
| `SHA256SUMS.txt` | Checksums to confirm the downloads are intact. / بصمات للتأكد من سلامة التنزيل. |
| `latest.json`, `version.json` | Used automatically by the app's update check — you don't need them. / يستخدمها البرنامج تلقائيًا لفحص التحديثات — لا تحتاج تنزيلها. |

## Desktop app / برنامج سطح المكتب

1. Run `AMX-TrustMesh-Setup-<version>.exe`. / شغّل ملف التثبيت.
2. Open **AMX TrustMesh** from the Start menu. / افتح البرنامج من قائمة ابدأ.
3. **License** tab → **Choose license file…** → pick your `license.amx`. / تبويب **الترخيص** ← **اختيار ملف الترخيص…** ← اختر ملف `license.amx`.

Without a license it runs as an **evaluation copy**: every sealed document is marked `EVALUATION COPY - NOT LICENSED` inside its signature.
بلا ترخيص يعمل كنسخة تجريبية: كل وثيقة مختومة تحمل علامة النسخة التجريبية داخل توقيعها.

## Server / الخادم

```bash
sudo mkdir -p /opt && sudo tar xzf AMX-TrustMesh-Server-*-linux-x64.tar.gz -C /opt
sudo bash /opt/amx-trustmesh/deploy/install-server.sh <web-domain> <api-domain> <admin-email>
sudo cp license.amx /var/lib/amx-trustmesh/core/license.amx && sudo chown amx:amx /var/lib/amx-trustmesh/core/license.amx
sudo systemctl restart amx-core
sudo amx-user add -name "Full Name"            # website sign-in key for a staff member
sudo amx-trust-issuer add <key> "Issuer name"  # accept documents sealed on a desktop (key: desktop app → About)
```

## Updates / التحديثات

The desktop app checks for a newer version when it opens. The update is signed by AMXNexus; the app verifies the signature and the file's fingerprint before saving anything.
يفحص البرنامج وجود إصدار أحدث عند فتحه. التحديث موقَّع من AMXNexus، والبرنامج يتحقق من التوقيع وبصمة الملف قبل حفظه.

---
© 2026 AMXNexus Technologies L.L.C. All rights reserved. Proprietary software — no source code is published here.
