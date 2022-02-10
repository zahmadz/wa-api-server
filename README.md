## Whatsapp Client REST API

---

Ini adalah REST API untuk mengelola client Whatsapp, seperti login, logout, mengirim broadcast, menscrape data group, menscrape data label, dll.

## Quick Link

*   Guide Video (work in progress)
*   [Fitur](#fitur)
*   [Instalasi Server](#instalasi-server-requirement)
*   [Instalasi Project / REST API](#instalasi-rest-api)
*   [Dokumentasi](https://app.swaggerhub.com/apis/wa-restapi/waclientrestapi/1.0.0)

## Fitur

<table><tbody><tr><td>Broadcast</td><td>✅</td></tr><tr><td>Schedule Broadcast</td><td>✅</td></tr><tr><td>Scrape Label</td><td>✅</td></tr><tr><td>Scrape Label Contacts</td><td>✅</td></tr><tr><td>Scrape Groups</td><td>✅</td></tr><tr><td>Scrape Groups Contact</td><td>✅</td></tr><tr><td>Broadcast/Message Status (single tick, double tick, double blue tick, failed)</td><td>✅</td></tr></tbody></table>

## Instalasi Server Requirement

#### **REST API ini membutuhkan:**

*   NodeJS sebagai runtime (wajib menggunakan v14++)
*   NPM sebagai package manager
*   MongoDB sebagai database untuk menyimpan data yang dihasilkan oleh whatsapp client

#### **Install NodeJS:**

[https://nodejs.org/en/download/](https://nodejs.org/en/download/)

#### **Install NPM:**

Untuk OS Windows, secara default NPM akan otomatis terinstall saat sudah menginstall NodeJS. Tapi pada OS Linux, kadang NPM tidak terinstall. Install NPM di ubuntu:

```powershell
sudo apt install npm
```

#### **Install MongoDB:**

Bisa menginstall MongoDB didalam server sendiri, atau menggunakan MongoDB Atlas.

1\. Menggunakan MongoDB Atlas (cloud database): [https://www.mongodb.com/atlas/database](https://www.mongodb.com/atlas/database)

2\. Menginstall MongoDB di server sendiri:

windows: [https://docs.mongodb.com/manual/tutorial/install-mongodb-on-windows/](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-windows/)

ubuntu: [https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/)

#### **Install Liblary Tambahan (khusus untuk linux/ubuntu):**

```powershell
sudo apt install libnss3-dev libgdk-pixbuf2.0-dev libgtk-3-dev libxss-de libgconf-2-4 libatk1.0-0 libatk-bridge2.0-0 libgdk-pixbuf2.0-0 libgtk-3-0 libgbm-dev libnss3-dev libxss-dev ffmpeg google-chrome-stable
```

## Instalasi REST API

#### **1\. Clone project**

```
git clone https://github.com/zahmadz/mylofi.git
```

#### **2\. Install dependencies**

```
npm install
```

#### **3\. Konfigurasi**

_\- /config/client.config.js_ rubah **executablePath** menjadi lokasi instalasi chrome

_\- /config/webhook.config.js_ rubah **chatWebhook** menjadi url webhook untuk menerima chat masuk

\- ._env_ rubah **MONGODB\_CONNECTION\_URI** menjadi koneksi URI mongodb

jika install mongodb di server sendiri maka koneksi URI = mongodb://localhost:27017/\<nama database>

jika menggunakan mongodb atlas maka ambil koneksi URI menggunakan cara ini: [https://docs.mongodb.com/guides/cloud/connectionstring/#copy-the-connection-string](https://docs.mongodb.com/guides/cloud/connectionstring/#copy-the-connection-string)

#### **4\. Jalankan Project**

```
npm start
```
