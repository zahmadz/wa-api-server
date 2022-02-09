## Whatsapp Client REST API

---

Ini adalah REST API untuk mengelola client Whatsapp, seperti login, logout, mengirim broadcast, menscrape data group, menscrape data label, dll.

## Quick Link

*   Guide Video (work in progress)
*   Fitur (work in progress)
*   List END POINT yang dapat digunakan (work in progress)

## Fitur

\-

## Instalasi Server Requirement

REST API ini membutuhkan:

*   NodeJS sebagai runtime (wajib menggunakan v14++)
*   NPM sebagai package manager
*   MongoDB sebagai database untuk menyimpan data yang dihasilkan oleh whatsapp client

**Install NodeJS:**

[https://nodejs.org/en/download/](https://nodejs.org/en/download/)

**Install NPM:**

Untuk OS Windows, secara default NPM akan otomatis terinstall saat sudah menginstall NodeJS. Tapi pada OS Linux, kadang NPM tidak terinstall. Install NPM di ubuntu:

```powershell
sudo apt install npm
```

**Install MongoDB:**

Bisa menginstall MongoDB didalam server sendiri, atau menggunakan MongoDB Atlas.

1\. Menggunakan MongoDB Atlas (cloud database): [https://www.mongodb.com/atlas/database](https://www.mongodb.com/atlas/database)

2\. Menginstall MongoDB di server sendiri:

windows: [https://docs.mongodb.com/manual/tutorial/install-mongodb-on-windows/](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-windows/)

ubuntu: [https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/)

**Install Liblary Tambahan (khusus untuk linux/ubuntu):**

```powershell
sudo apt install libnss3-dev libgdk-pixbuf2.0-dev libgtk-3-dev libxss-de libgconf-2-4 libatk1.0-0 libatk-bridge2.0-0 libgdk-pixbuf2.0-0 libgtk-3-0 libgbm-dev libnss3-dev libxss-dev ffmpeg google-chrome-stable
```

## Instalasi REST API

**1\. Clone project**

```
git clone https://github.com/zahmadz/mylofi.git
```

**2\. Install dependencies**

```
npm install
```

**3\. Konfigurasi**

_\- /config/client.config.js_ rubah **executablePath** menjadi lokasi instalasi chrome

_\- /config/webhook.config.js_ rubah **chatWebhook** menjadi url webhook untuk menerima chat masuk

\- ._env_ rubah **MONGODB\_CONNECTION\_URI** menjadi koneksi URI mongodb

jika install mongodb di server sendiri maka koneksi URI = mongodb://localhost:27017/\<nama database>

jika menggunakan mongodb atlas maka ambil koneksi URI menggunakan cara ini: [https://docs.mongodb.com/guides/cloud/connectionstring/#copy-the-connection-string](https://docs.mongodb.com/guides/cloud/connectionstring/#copy-the-connection-string)

**4\. Jalankan Project**

```
npm start
```

## List END POINT

BASE\_URL = http://domain:port/api (contoh: http://localhost:5000/api, [http://apiwa.watzap.com/api](http://apiwa.watzap.com/api)

fetch = BASE\_URL/END\_POINT (contoh: BASE\_URL/auth/init)

```javascript
fetch("BASE_URL/auth/init", {
    method: 'POST'
})
```

<table><tbody><tr><td>Keterangan</td><td>END POINT</td><td>Method</td><td>Body</td><td>Return</td></tr><tr><td>login client WA</td><td>/auth/init</td><td>POST</td><td><pre><code class="language-json">{
"userId":&nbsp;"zulzul",
"whatsappNumber":&nbsp;"082118358997"
}</code></pre></td><td><pre><code class="language-json">{
 "status": "ok" / "failed"
 "message":
}</code></pre></td></tr><tr><td>logout client WA</td><td>/auth/logout</td><td>POST</td><td><pre><code class="language-json">{
"userId":&nbsp;"zulzul",
"whatsappNumber":&nbsp;"082118358997"
}</code></pre></td><td><pre><code class="language-json">{
 "status": "ok" / "failed"
 "message",
 "data": {
          "userId",
          "082118358997"
 }
}</code></pre></td></tr><tr><td>cek koneksi WA by whatsappNumber</td><td>auth/connection/:userId/:whatsappNumber</td><td>GET</td><td>-</td><td><pre><code class="language-json">{
 "status": "ok" / "failed"
 "connectionStatus": {
   "state": "UNAUTHORIZE" / "SCANNING_QR" / "READY",
   "qrString": , // disisi client, rubah string qr ke gambar
   "info": // client info (nama, no wa, dll)
 }
}</code></pre></td></tr><tr><td>cek semua koneksi WA by userId</td><td>/api/auth/connection/:userId</td><td>GET</td><td>-</td><td><pre><code class="language-json">{
 "status": "ok" / "failed"
 "whatsappAccounts": [], // daftar nomor akun wa
 "connections": [] // daftar detail koneksi akun wa
}</code></pre></td></tr><tr><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td></tr><tr><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td></tr><tr><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td></tr><tr><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td></tr><tr><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td><td>&nbsp;</td></tr></tbody></table>
