# KE-TEST: Live Style Editing & QA

Ekstensi Chrome & Edge (Manifest V3) untuk frontend developer dan QA: pilih elemen di halaman, ubah style-nya,
geser posisinya, cek aksesibilitas, lalu ekspor semua perubahan sebagai laporan QA.

Repo ini berisi ekstensi yang **sudah siap pakai**. Tidak perlu install atau build apa pun.

## Instalasi

1. Unduh salah satu:
   - Tombol hijau **Code → Download ZIP** di halaman ini, atau
   - [**ke-test.zip**](../../releases/latest/download/ke-test.zip) dari rilis terbaru.
2. Ekstrak ZIP-nya.
3. Buka `chrome://extensions` (Chrome) atau `edge://extensions` (Edge).
4. Aktifkan **Developer mode**.
5. Klik **Load unpacked**, lalu pilih folder hasil ekstrak (folder yang berisi `manifest.json`).
6. (Opsional) Untuk file lokal (`file://`): buka **Details** → aktifkan **Allow access to file URLs**.

Jangan hapus atau pindahkan folder itu setelah dimuat, karena browser membacanya langsung dari sana.

**Update ke versi baru:** unduh lagi, timpa isi folder lama, lalu klik tombol ⟳ (reload) pada kartu KE-TEST di halaman ekstensi.

## Cara pakai

1. Buka halaman web, lalu klik ikon KE-TEST. Badge **ON** muncul.
2. Arahkan kursor ke elemen untuk melihat highlight, lalu klik untuk memilihnya.
3. Pilih mode di toolbar panel:
   - **Edit**: ubah typography, box, layout, visual, gambar, isi teks, semua properti CSS, dan force `:hover`/`:focus`/`:active`.
   - **Move**: geser elemen (offset) atau ubah urutannya di antara sibling (reorder).
   - **Measure**: jarak antar elemen ala Figma dan visualisasi padding/margin.
   - **A11y**: kontras WCAG AA/AAA dengan saran warna, non-text contrast, role/nama aksesibel, alt gambar, ukuran target sentuh, dan scan kontras seluruh halaman.
   - **Log**: riwayat perubahan, undo per item, simpan per URL, dan ekspor **CSS / Markdown / JSON**.
4. Ikon 👁 di header membandingkan **before/after**. Ikon kamera di kartu elemen mengambil **screenshot** elemen.
5. Klik ikon KE-TEST lagi (atau tekan `Esc` dua kali) untuk menonaktifkan.

Selama aktif, klik di halaman dicegat: link tidak berpindah halaman dan form tidak ter-submit.

## Shortcut

| Tombol | Aksi |
| --- | --- |
| Klik | Pilih elemen |
| `Esc` | Lepas pilihan; tekan lagi untuk keluar |
| `Shift+Enter` / `Enter` | Pilih parent / child pertama |
| `Tab` / `Shift+Tab` | Sibling berikutnya / sebelumnya |
| Panah (mode Move) | Geser 1px (`Shift` = 10px) atau pindah urutan |
| `Ctrl/Cmd+Z` | Undo |
| `Ctrl/Cmd+Shift+Z`, `Ctrl+Y` | Redo |
| `↑` / `↓` di input angka | ±1 (`Shift` ±10, `Alt` ±0.1) |

## Batasan

- Tidak berjalan di halaman internal browser (`chrome://`, `edge://`), Chrome Web Store, dan Edge Add-ons.
- Isi iframe dan shadow root tertutup tidak didukung.
- Inline style halaman yang memakai `!important` tidak bisa dikalahkan.
- Screenshot hanya menangkap bagian elemen yang terlihat di layar.
- Ekspor CSS memakai selector buatan ekstensi (id → data-* → nth-of-type); sesuaikan dengan class di codebase kamu.
- Role dan nama aksesibel adalah perkiraan. Untuk hasil pasti, gunakan Accessibility pane di DevTools.

## Lisensi

[MIT](LICENSE)
