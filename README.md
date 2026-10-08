# AMX TrustMesh™ — Releases

Official downloads for **AMX TrustMesh**, the cryptographic document sealing and verification suite by [AMXNexus Technologies L.L.C.](https://amxnexus.com)

التنزيلات الرسمية لمنظومة **AMX TrustMesh** لختم الوثائق والتحقق منها تشفيريًا.

## Latest version / أحدث إصدار

**[Download the latest release →](https://github.com/AMXNexus/trustmesh-releases/releases/latest)**

| File | Platform |
|---|---|
| `AMX-TrustMesh-Desktop-<version>-windows-x64.zip` | Desktop agent — Windows 10/11 |
| `AMX-TrustMesh-Server-<version>-linux-x64.tar.gz` | Self-hosted server (core + API gateway + web portal) — Ubuntu 24.04 |
| `AMX-TrustMesh-<version>.apk` | Mobile verifier — Android |
| `SHA256SUMS.txt` | Checksums for every file above |

## Evaluation and licensing / النسخة التجريبية والترخيص

Every download runs without a license as an **evaluation copy**: each sealed document carries the mark
`EVALUATION COPY - NOT LICENSED` inside its signature. A license file (`license.amx`) from AMXNexus removes
the mark. Buy a license at [amxnexus.com](https://amxnexus.com).

كل تنزيل يعمل بلا ترخيص كنسخة تجريبية: كل وثيقة مختومة تحمل علامة النسخة التجريبية داخل توقيعها.
ملف الترخيص من AMXNexus يزيل العلامة.

## Quick start

**Desktop:** unzip, run `run-agent.bat`, then paste your license text in the *License* tab.

**Server:**
```bash
sudo mkdir -p /opt && sudo tar xzf AMX-TrustMesh-Server-*-linux-x64.tar.gz -C /opt
sudo bash /opt/amx-trustmesh/deploy/install-server.sh <web-domain> <api-domain> <admin-email>
sudo cp license.amx /var/lib/amx-trustmesh/core/license.amx && sudo chown amx:amx /var/lib/amx-trustmesh/core/license.amx
sudo systemctl restart amx-core
```

## Updates

The desktop agent checks `latest.json` from the newest release. The file is signed by AMXNexus; the agent
verifies the signature and the download's fingerprint before saving anything.

---
© 2026 AMXNexus Technologies L.L.C. All rights reserved. Proprietary software — no source code is published here.
