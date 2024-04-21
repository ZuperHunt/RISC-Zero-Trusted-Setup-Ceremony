Penulis: [Naufal](https://twitter.com/0xfal)

# Pengenalan
Bab ini berisi pengenalan mengenai RISC Zero

## RISC Zero
> [!NOTE]
> RISC Zero adalah salah satu alternatif _execution environment_ berbasis _zero-knowledge_ atau biasa disebut zkVM (_zero-knowledge virtual machine_)

### Investor
![image](https://github.com/ZuperHunt/RISC-Zero-Trusted-Setup-Ceremony/assets/80172679/d5b6380a-ba87-45f6-b677-6cc8fa2bf737)

# Tutorial _Trusted Setup Ceremony_
Bab ini berisi tutorial cara ikut berkontribusi dalam perayaan _RISC Zero’s trusted setup_ yang merupakan fase pertama dari RISC Zero zkVM 1.0.0 _Roadmap_

## _Requirements_
Yang diperlukan untuk menjalankan _Trusted Setup Ceremony_:
- Akun GitHub berumur 1 bulan, memiliki pengikut minimal 1 orang, mengikuti minimal 5 orang, dan memiliki 2 repositori publik
- Komputer dengan spesifikasi:

| ✅ Linux | ✅ macOS | ✅ Windows (Native / WSL) |
| ------------- | ------------- | ------------- |

| Part | Minimum | Recommended |
| ------------- | ------------- | ------------- |
| CPU | - | - |
| RAM | - | 8 GB |
| SSD | - | - |

Tidak ada detail _system requirement_ dari _official_, hanya menyebutkan RAM saja. Tutorial ini dibuat menggunakan sistem operasi Linux (Ubuntu), untuk sistem operasi lainnya mungkin akan sedikit berbeda ([cek referensi](https://github.com/ZuperHunt/RISC-Zero-Trusted-Setup-Ceremony#acknowledgments)).

## _Dependencies_
Yang perlu dilakukan sebeleum menjalankan _Trusted Setup Ceremony_:

### Instalasi NVM (Node Version Manager)
Instal NVM versi berapa pun, tidak perlu _instal_/_update_ jika di komputer kalian sudah terinstal.
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

### Konfigurasi _Environment_ / _Profile_
Abaikan step ini jika di komputer kalian sudah terinstal NVM dengan benar.
```
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
```

### Instalasi `Node.js`
Instal versi 16.20.
```
nvm install 16.20
```
Gunakan versi 16.20.
```
nvm use 16.20
```

### Instalasi `phase2cli`
```
npm i @p0tion/phase2cli
```

## Menjalankan _Trusted Setup Ceremony_

### Buat `tmux`
```
tmux
```

### _Authenticate with GitHub_
```
npx phase2cli auth
```
Tunggu sebentar sampai muncul _authentication link_ dan _authentication code_, klik _link_-nya dan masukkan kode.

### _Contribute!_
```
npx phase2cli contribute
```
Akan muncul opsi `RISC Zero STARK-to_SNARK Prover`, tekan `enter` pada _keyboard_ komputer. Selanjutnya akan ada opsi `randomly` dan `manually`, kalian bebas memilih yang mana, saya pribadi memilih `randomly` biar cepat.
Kalian akan masuk antrian, tunggu sampai giliran kalian nanti akan memproses kontribusi secara otomatis.

> [!CAUTION]
> Proses kontribusi mungkin akan memakan waktu tergantung antrian, sampai prosesnya selesai jangan melanjutkan ke step selanjutnya.

### _Cleanup_
Setelah proses kontribusi selesai, kalian bisa membersihkan GitHub _authorization_.
```
npx phase2cli clean
npx phase2cli logout
```
Buka _authorized apps_ pada GitHub mu dan hapus _permissions_ untuk `pse-p0tion-production`. Kamu juga boleh menghapus folder `~/p0tion-tmp` yang dibuat di awal tadi.

## Misc
Hal-hal lain yang mungkin bermanfaat:

### Gimana kalau _disconnect_?
Menurut blog mereka, antrianmu akan tersimpan. Untuk _re-join_, jalankan ulang perintah `npx phase2cli contribute`.

### Gagal menjalankan via `screen`?
Gunakan `tmux`.

## Help

Join komunitas [Discord ZuperHunt](https://t.co/n7TeWVlA48) jika kamu ada pertanyaan.

Follow [GitHub ZuperHunt](https://github.com/ZuperHunt) dan [X(Twitter) ZuperHunt](https://twitter.com/ZuperHunt)

## Change Logs

* 0.0.1
  * Initial release
* 0.0.2
  * correct writing
  * add tmux step and cheatsheet
  * add misc

## Acknowledgments

Referensi
* [Ceremony contribution public instructions](https://www.risczero.com/blog/ceremony-contribution-public-instructions)
* [tmux cheatsheet](https://quickref.me/tmux.html)
