# MasakYuk

Aplikasi mobile pencari resep masakan berbasis **Flutter** yang menampilkan data
dari **TheMealDB API**. Dibuat untuk UTS Pemrograman Mobile (Praktikum Kelas G).

## Deskripsi Singkat

MasakYuk membantu pengguna menemukan ide masakan: menjelajahi resep per kategori,
mencari resep berdasarkan nama, melihat bahan dan langkah memasak, mendapatkan
resep acak, serta menyimpan resep favorit. Seluruh data diambil secara dinamis
dari API publik TheMealDB.

## Fitur Utama

- Daftar kategori resep (Beef, Chicken, Dessert, Seafood, dll.)
- Grid resep berdasarkan kategori yang dipilih
- Pencarian resep berdasarkan nama
- Detail resep: foto, kategori, asal masakan, tag, bahan + takaran, cara memasak
- Resep acak ("Kejutkan saya") dengan tombol acak ulang
- Resep favorit (disimpan di memori selama aplikasi berjalan)
- Penanganan kondisi **loading**, **sukses**, **kosong**, dan **error** (dengan tombol coba lagi) menggunakan `FutureBuilder`

## Teknologi / Package

| Teknologi | Fungsi |
|-----------|--------|
| Flutter & Dart | Framework dan bahasa pemrograman |
| `http` | Permintaan HTTP ke API |
| `flutter_lints` | Aturan kualitas kode (dev) |
| `flutter_test` | Pengujian unit (dev) |
| TheMealDB API (`https://www.themealdb.com/api/json/v1/1`) | Sumber data |

## Struktur Folder

```
lib/
├── main.dart
├── models/meal.dart                 # MealCategory, MealSummary, MealDetail, Ingredient
├── services/meal_api_service.dart   # Permintaan HTTP & parsing JSON
├── state/favorites_store.dart       # Penyimpanan favorit (ValueNotifier)
├── screens/                         # home, detail, favorites
└── widgets/                         # meal_card, state_views
test/meal_test.dart                  # Unit test model & service
```

## Langkah Menjalankan Aplikasi

1. Pastikan Flutter SDK terpasang (`flutter doctor`).
2. Clone repositori:
   ```bash
   git clone <URL-REPOSITORI-ANDA>
   cd masakyuk
   ```
3. Jika folder platform (`android/`, `ios/`, dll.) belum ada, buat dengan:
   ```bash
   flutter create .
   ```
4. Android: pastikan izin internet ada di `android/app/src/main/AndroidManifest.xml`
   (di dalam tag `<manifest>`, sebelum `<application>`):
   ```xml
   <uses-permission android:name="android.permission.INTERNET"/>
   ```
5. Pasang dependensi dan jalankan:
   ```bash
   flutter pub get
   flutter run
   ```
6. (Opsional) Jalankan pengujian: `flutter test`

## Sumber Data

[TheMealDB](https://www.themealdb.com/api.php) - menggunakan test API key publik `1`
(untuk pengembangan dan pembelajaran).
