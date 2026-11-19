# White-Box Unit Test – Penerapan Kupon Promo ShopEase

## Ruang lingkup
Pengujian hanya mencakup fungsi asli `applyCoupon()` yang berada di `js/views/cart.js`.
Source code aplikasi tidak diubah.

## Test case
- TC-01: input ` discount10 ` harus dinormalisasi menjadi `DISCOUNT10`, menyimpan kupon dengan rate `0.10`, menampilkan notifikasi sukses, dan meminta render ulang.
- TC-02: input `PROMO20` harus mempertahankan `appliedCoupon` bernilai `null`, menampilkan notifikasi gagal, dan meminta render ulang.

## Test Double
- Stub: `createInputStub()` menyediakan nilai input untuk elemen `coupon-code-input` tanpa browser.
- Spy: `createSpy()` mencatat pemanggilan `showToast()` dan `renderCartView()` beserta argumennya.

## Prasyarat
- Node.js 18 atau lebih baru (disarankan Node.js 22).
- Tidak membutuhkan instalasi package tambahan.

## Menjalankan pengujian
Dari terminal, masuk ke folder utama `shopease-app`, lalu jalankan:

```bash
npm test
```

Hasil yang diharapkan saat kedua test lulus: `# pass 2` dan `# fail 0`.

## Catatan coverage
Pengujian ini menjalankan fungsi asli melalui lingkungan terisolasi dan memalsukan dependensi browser. Laporan coverage bawaan Node terhadap file test tidak boleh dianggap sebagai coverage source `js/views/cart.js`. Laporan Statement/Branch Coverage manual pada dokumen Pre-Lab tetap terpisah. Jika dosen meminta laporan coverage otomatis untuk source aplikasi, diperlukan instrumentasi coverage yang secara eksplisit mengukur fungsi asli tersebut.
