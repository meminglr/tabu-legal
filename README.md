# Tabu — web sitesi

Tabu kelime oyununun web sitesi: [tabu.emniva.com](https://tabu.emniva.com)

Build adımı yok, framework yok: HTML, tek bir CSS, oyunun kendi fontları
(OFL lisanslı, `fonts/`) ve ikonu (`img/`). Sayfa dışarıya istek atmıyor.

- `index.html`: tanıtım sayfası (giriş, nasıl oynanır, özellikler, indirme)
- `privacy.html`: gizlilik politikası
- `delete-account.html`: hesap silme

Gizlilik ve hesap silme sayfaları Türkçe, altlarında İngilizcesi var (`#en`).

## Mağaza bağlantılarını eklemek

`index.html`'de iki yerde (girişte ve en altta `#indir`) Google Play ve App Store
düğmeleri var; şimdilik "Yakında" diyor ve tıklanmıyor. Uygulama yayına girince her
düğmede:

1. `href="#indir"` yerine mağaza adresini yaz
   (Google Play: `https://play.google.com/store/apps/details?id=com.emniva.tabu`).
2. `class="store is-soon"` → `class="store"` ve `aria-disabled="true"`'yu sil.
3. `Yakında` yazısını `Hemen indir` gibi bir şeyle değiştir.

Google'ın ve Apple'ın resmî rozetlerini kullanmak istersen `<a>`'nın içeriğini o
rozetin `<img>`'i ile değiştirmen yeterli.

## Metin uygulamayla birlikte değişmeli

Gizlilik ve hesap silme sayfaları uygulamanın bugünkü davranışını anlatıyor. Yeni bir
veri türü, yeni bir hizmet sağlayıcı (analiz, reklam, çökme raporlama) ya da hesap
silmenin sildiklerinde bir değişiklik olursa sayfalar da güncellenmeli.
