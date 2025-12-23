# 📊 Pawnshop Price List - IME Roleplay

Database harga lengkap untuk sistem pawnshop di server IME Roleplay. Repository ini menyimpan data harga jual berbagai item yang dapat dijual ke pawnshop.

## 📋 Daftar Isi

- [Kategori Item](#kategori-item)
- [Struktur Data](#struktur-data)
- [Cara Kontribusi](#cara-kontribusi)
- [Format Update Data](#format-update-data)
- [Aturan Kontribusi](#aturan-kontribusi)

## 🏷️ Kategori Item

Database ini mencakup 7 kategori utama:

### 1. **PERTANIAN** 🌾
Item hasil farming seperti sayuran, buah-buahan, dan tanaman pangan.
- Total: 17 jenis item
- Harga: $3 - $5

### 2. **RONGSOKAN** ♻️
Barang bekas yang dapat dijual untuk daur ulang.
- Total: 4 jenis item
- Harga: $2 - $150

### 3. **TAMBANG** ⛏️
Material mentah hasil mining dan olahan.
- Total: 12 jenis item
- Harga: $7 - $78

### 4. **PERHIASAN** 💎
Aksesoris mewah hasil crafting dari material tambang.
- Total: 22 jenis item
- Harga: $129 - $678

### 5. **ALKOHOL** 🍷
Minuman beralkohol dan mixer.
- Total: 13 jenis item
- Harga: $28 - $45

### 6. **HUNTING** 🦌
Item hasil berburu hewan liar.
- Total: 14 jenis item
- Harga: $7 - $28

## 📁 Struktur Data

### File Utama

```
├── data.txt          # Daftar lengkap semua item dan harga
└── mining.txt        # Detail crafting perhiasan dan material tambang
```

### Format Data (data.txt)

```
[KATEGORI]
Nama Item = $Harga
```

### Format Data (mining.txt)

```
Nama Item
- Require : Material x Jumlah
- Price   : Harga
```

## 🤝 Cara Kontribusi

### Langkah-langkah Update Data

1. **Fork Repository**
   - Fork repository ini ke akun GitHub Anda

2. **Clone ke Lokal**
   ```bash
   git clone https://github.com/ardelagi/pawndata.git
   cd pawndata
   ```

3. **Buat Branch Baru**
   ```bash
   git checkout -b update-prices-DD-MM-YYYY
   ```

4. **Edit File Data**
   - Buka `data.txt` atau `mining.txt`
   - Update harga sesuai informasi terbaru
   - Pastikan format tetap konsisten

5. **Commit Perubahan**
   ```bash
   git add .
   git commit -m "Update: [Kategori] - Tanggal Update"
   ```

6. **Push ke GitHub**
   ```bash
   git push origin update-prices-DD-MM-YYYY
   ```

7. **Buat Pull Request**
   - Buka repository di GitHub
   - Klik "New Pull Request"
   - Isi deskripsi perubahan dengan jelas

## 📝 Format Update Data

### Template Update Harga

```
[KATEGORI]
Nama Item = $Harga_Baru  # (sebelumnya: $Harga_Lama)
```

### Template Tambah Item Baru

**Untuk data.txt:**
```
[KATEGORI]
Nama Item Baru = $Harga
```

**Untuk mining.txt:**
```
Nama Item Baru
- Require : Material x Jumlah, Material2 x Jumlah
- Price   : Harga
```

### Contoh Pull Request Description

```markdown
## Update Harga - 23 Desember 2025

### Perubahan:
- [PERTANIAN] Potato: $3 → $4
- [TAMBANG] Diamond: $31 → $35
- [PERHIASAN] Ruby Ring: $351 → $360

### Item Baru:
- [PERTANIAN] Pumpkin = $5
- [HUNTING] Skin Bear Low = $25

### Sumber:
Screenshot in-game / Informasi dari admin / Testing langsung

### Verified by:
@username
```

## ⚠️ Aturan Kontribusi

### ✅ DO (Lakukan)

- Pastikan data akurat dan ter-verifikasi
- Gunakan format yang sudah ada
- Cantumkan sumber informasi
- Update kedua file jika item terkait crafting
- Gunakan nama branch yang deskriptif
- Buat commit message yang jelas

### ❌ DON'T (Jangan)

- Mengubah struktur format file
- Menambah data tanpa verifikasi
- Menghapus item tanpa konfirmasi
- Commit langsung ke branch main
- Menggunakan harga estimasi/tebakan

## 🔍 Verifikasi Data

Sebelum submit update, pastikan:

- ✅ Harga sudah di-cross check dengan pawnshop in-game
- ✅ Format penulisan konsisten (huruf kapital, tanda baca)
- ✅ Tidak ada typo pada nama item
- ✅ Perhitungan profit crafting masuk akal
- ✅ File dapat dibaca dengan benar (encoding UTF-8)

## 📊 Template Analisis Profit

Untuk item crafting, Anda dapat menambahkan analisis:

```
Ruby Ring
- Material: Gold Ingot ($58) + Ruby x4 ($39 x 4 = $156)
- Total Cost: $214
- Sell Price: $351
- Profit: $137
```

## 📞 Kontak & Dukungan

- **Discord Server:** [IME Roleplay]
- **Issues:** Laporkan bug atau ketidaksesuaian data melalui GitHub Issues
- **Discussion:** Gunakan tab Discussions untuk diskusi umum

## 📜 Lisensi

Data ini dikumpulkan untuk kepentingan komunitas IME Roleplay dan bersifat open-source.

## 🙏 Kontributor

Terima kasih kepada semua yang telah berkontribusi dalam menjaga data tetap akurat dan up-to-date!

---

**Last Updated:** 23 Desember 2025
**Maintained by:** IME Roleplay Community