## Sebelum mulai

- Saya tidak di-_endorse_ oleh tim _Deno_ untuk mempromosikan produknya.
- Saya hanya pengguna yang menyukai _tools_ yang mudah dan sederhana seperti
  _Deno_.
- Saat ini hanya digunakan untuk projek sampingan berukuran kecil/sederhana.
- Presentasi bisa diliat di repositori MoF.JS di github:
  [github.com/mofjs/sharing-deno](https://github.com/mofjs/sharing-deno).

---

## Apa itu Deno

---

- _Runtime_ untuk menjalankan kode TypeScript/JavaScript.
- Diciptakan oleh Ryan Dahl yang juga menciptakan NodeJS.
- Dibuat dengan bahasa program _Rust_, awalnya menggunakan _Go_.
- Dirilis v1.0 pada 13 Mei 2020, sekarang telah mencapai versi 1.35.2.

---

## Mengapa dibuat Deno?

---

### 10 Kekecewaan dengan NodeJS - JSConf EU 2018

Video : [youtu.be/M3BM9TB-8yA](https://www.youtube.com/watch?v=M3BM9TB-8yA)

---

- Promise
  - bahasa JS, jaman dulu masih menggunakan _callback_.
  - sekarang sudah _async/await_.
- Security
  - NodeJS saat dijalankan langsung bisa akses _system calls_.
  - kode dari pihak-ketiga bisa akses _file system_ tanpa disadari.
- Build System
  - awalnya dipakai oleh Chrome.
  - Chrome beralih ke GN.

---

- package.json
  - node menggunakan konfigurasi di """package.json"""
  - menggunakan _NPM_ yang terpusat.
- node_modules
  - module diunduh di _local_ folder.
  - ukuran node_modules bisa sangat besar.
- require without extension
  - kerumitan harus mengecek rujukan module dengan ekstensi tertentu.
  - sangat berbeda dengan cara kerja di _browser_.

---

- index.js
  - meniru cara kerja index.html
  - menambah kerumitan rujukan module kembali.
- (Di judulnya sih 10, tapi isi slidenya cuma 7.)

---

> We want a fun and productive system from scripting. Neither Node.js nor Python
> or Ruby are satisfactory.

Ryan Dahl & Kitson Kelly, TSConf 2019

---

## Jadi mengapa pakai Deno

---

### Menggunakan standar WebAPI

- _fetch_ berjalan sesuai yang spesifikasi.
- definisi _TypeScript_ sudah tersedia.

---

### Secure by default

- Secara _default_ script tidak memiliki akses sistem (_file system_, _network_,
  _environment variable_).
- CLI harus dijalankan dengan argumen yang mengijinkan akses ke sistem.
- Deno akan menanyakan ke pengguna untuk mengijinkan akses atau tidak ke
  _script_ yang sedang diajalankan.

---

### Hanya cukup satu executable saja, di-_compile_ dari _Rust_.

- Tersedia untuk berbagai _platform_ dan beberapa _package manager_ di Windows.
- untuk memperbarui versi juga cukup dengan CLI yang sama.

---

### Sudah termasuk _tools_ yang diperlukan:

- install
- bundle
- doc
- fmt
- lint
- test
- ...

---

### Tersedia VS Code extension

- Language server untuk pemeriksaaan _TypeScript_ dan _JavaScript_.
- Integrasi dengan versi CLI Deno
- Autocomplete, Formatter, Linter
- Deno Tasks

---

### Standard Library (std)

- std terpisah dari instalasi CLI.
- versi std masih belum stabil (saat ini v0.195.0).
- direview oleh Deno core team.

---

### Mendukung Module Node / NPM

- dengan awal `node:` bisa menggunakan nodejs built-in modules seperti _fs_,
  _path_, atau _process_
- dengan awalan `npm:` bisa menggunakan library pada _npm_.
- mendukung `package.json`.
- alternatifnya menggunakan CDN seperti _esm.sh_, _unpkg_, atau _jspm.io_.

---

## Cobainnya gimana?

---

### Gunakan _playground_?

- [deno.town](https://deno.town/)
- [Replit](https://replit.com/languages/deno)

---

### Install langsung di mesin

MacOS & Linux
```sh
curl -fsSL https://deno.land/x/install/install.sh | sh
```
atau (Windows)
```ps
irm https://deno.land/install.ps1 | iex
```

---

### Jalankan contoh script

```sh
deno run https://deno.land/std@0.195.0/examples/welcome.ts
```
