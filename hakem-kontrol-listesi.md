# Hakem kontrol listesi

Ajanların işini birleştirdikten sonra, yayına almadan (ya da hemen aldıktan sonra) uygulamaya bağımsız bir gözle baktırmak için.

Hakem kim olabilir: bağımsız bir test aracı, işi yazmamış başka bir model ya da sen. Önemli olan iki şey: hakem **kodu yazan ajan olmamalı** ve doğru cevabı **koddan değil tariften** almalı.

## 1. Hakeme ne verilir
- [ ] Çalışan uygulamanın adresi (kendi bilgisayarındaki değil, yayındaki hali).
- [ ] Tarif dosyası (`tarif.md`).
- [ ] Başka bir şey verme: kod yok, ajanın yazdığı testler yok.

Videoda hakeme verdiğim mesaj: [`promptlar/4-hakeme-verilen.md`](promptlar/4-hakeme-verilen.md).

## 2. Hakemden ne istenir
- [ ] Tarifteki her kural için "uygulamada oluyor mu?" diye baksın.
- [ ] Kuralları yalnız tek tek değil, **birlikte** denesin (bir özelliğin sayacı başka bir özellikle birlikte doğru çalışıyor mu).
- [ ] Sayı içeren kuralları sınırında zorlasın: sınır 3 ise aynı anda 6 istek göndersin.
- [ ] Aynı soruyu art arda birkaç kez sorsun; cevap her seferinde aynı mı.
- [ ] Bulduğunu kendi cümlesiyle, hangi adımları attığını yazarak raporlasın.
- [ ] İki kural çelişiyorsa kendi karar vermesin, sana sorsun.

## 3. Rapor geldikten sonra
- [ ] Her bulgu için: bu bir kod hatası mı, yoksa tarifteki bir boşluk mu?
- [ ] Kod hatasıysa düzeltmeyi ajana ver; tarifi değiştirme.
- [ ] Tarif boşluğuysa önce tarifi sen düzelt (hangi kural geçerli?), sonra ajana ver.
- [ ] Düzeltmeden sonra hakeme **aynı kontrolleri** yeniden yaptır; önce/sonra tablosu iste.

## 4. Videoda çıkan iki hata sınıfı (kendi uygulamanda ara)
- **Aynı anda gelen istekler sınırı deliyor.** Sayaç "oku, kontrol et, düşür" diye üç adımda işliyorsa, aynı anda gelen istekler hepsi birden geçer. Düşürme tek adımda (atomik) olmalı.
- **Sayaç sunucu kopyaları arasında zıplıyor.** Sayı sunucunun belleğinde tutuluyorsa kendi bilgisayarında doğru görünür; yayında her istek başka bir kopyaya düşebilir ve her kopya kendi sayısını tutar. Sayı tüm kopyaların paylaştığı tek bir yerde (veritabanı) durmalı.

## 5. Bir sonraki sefer için
- [ ] Yeni özellik = önce tarife yeni kural, sonra kod.
- [ ] Yeni kural eski bir kuralın sayısıyla çakışıyorsa, hangisinin geçerli olduğunu tarife yaz.
