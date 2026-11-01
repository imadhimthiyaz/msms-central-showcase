<div align="center">

<img src="./docs/banner.svg" width="100%" alt="MSMS Central" />

<br/>

![PHP](https://img.shields.io/badge/PHP-0a0e17?style=for-the-badge&logo=php&logoColor=8892BF)
![MySQL](https://img.shields.io/badge/MySQL-0a0e17?style=for-the-badge&logo=mysql&logoColor=4479A1)
![WebAuthn](https://img.shields.io/badge/WEBAUTHN-BIOMETRIC-0a0e17?style=for-the-badge&color=ffb020)
![PWA](https://img.shields.io/badge/PWA-READY-0a0e17?style=for-the-badge&logo=pwa&logoColor=5A0FC8)
![Encryption](https://img.shields.io/badge/BACKUPS-ENCRYPTED-0a0e17?style=for-the-badge&color=ff4d8d)

**One control panel for every MSMS client installation.**

</div>


> 🔒 **Source code is private.** This repository is a public showcase of the project. For demos or collaboration, contact [hello@imadhimthiyas.nl](mailto:hello@imadhimthiyas.nl).

---

## Overview

MSMS Central is a standalone portal that manages many client installs of [Ivenza POS](https://github.com/imadhimthiyaz/ivenza-pos-showcase) from a single place. Register a client by domain, sync its live status, control its license, push announcements and updates, top up SMS credit and pull encrypted database backups.

## Features

- 🏢 **Client registry**: register every installation by domain, with a detail page per client
- 🔄 **Live sync**: status, SMS balance, reload history, users, customers, products, pending repairs and database size, individually or all at once
- 🪪 **Licensing**: mark clients active, trial, suspended or expired, with a license API clients can enforce
- 📣 **Announcements**: publish messages (with images) to client installs
- ⬆️ **Updates**: package and track update rollouts, with client update reports
- 💬 **SMS credits**: manage SMS credit reloads per client
- 💾 **Backups**: trigger client-side database backups, stored encrypted and downloadable on demand
- 🚨 **Alerts & history**: sync and backup history with an alerts view
- 🔐 **Secure sign-in**: hashed admin password plus WebAuthn / biometric login
- 📲 **PWA**: installable, with offline screen and icons

## Architecture

```mermaid
flowchart LR
    A[Admin] -->|HTTPS + WebAuthn| C[MSMS Central]
    C <-->|agent token| X1[Client install 1]
    C <-->|agent token| X2[Client install 2]
    C <-->|agent token| X3[Client install N]
    X1 -.->|license check| C
    C --> DB[(MySQL)]
    C --> B[(Encrypted backup storage)]
```

