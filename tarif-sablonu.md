# Tarif: "<uygulamanın adı>"

<!--
NASIL DOLDURULUR
1. Her kural tek bir davranışı anlatır ve DENENEBİLİR olmalı: biri uygulamayı açıp "evet oluyor / hayır olmuyor" diyebilmeli.
2. Sayıları ve ekranda görünecek metinleri birebir yaz ("Kalan hak: N", "en fazla 10", "10 MB").
3. Nasıl kodlanacağını yazma; ne olması gerektiğini yaz. Tarif kodun dışındaki doğrudur.
Bu açıklamayı doldurduktan sonra silebilirsin.
-->

<Uygulama tek paragrafta: kim kullanır, ne yapar, sonunda ne görür. Giriş/üyelik var mı? Nereye yayınlanacak?>

## Dış servisler
- <Hangi servis, hangi amaçla. Örnek: görsel üretimi için X servisi.>
- <Anahtarlar nerede durur. Örnek: anahtar yalnızca sunucuda, ortam değişkeninden okunur.>
- <Geliştirirken gerçek servis çağrılacak mı? Çağrılmayacaksa yerine ne dönecek?>

## Kurallar
1. <Girdi kuralı. Örnek: yükleme alanı yalnızca JPG, PNG ve WEBP kabul eder; başka türde "…" uyarısı çıkar.>
2. <Seçim kuralı. Örnek: oda tipi tek seçimdir: A, B, C.>
3. <Düğme ne zaman pasif, ne zaman aktif.>
4. <İşlem sürerken ekranda ne görünür; aynı anda ikinci işlem başlayabilir mi?>
5. <Sonuç nasıl gösterilir.>
6. <Sınır kuralı, sayısıyla. Örnek: her kullanıcının 3 ücretsiz hakkı vardır; ekranda "Kalan hak: N" yazar. Başarılı işlem 1 hak düşürür, başarısız işlem düşürmez.>
7. <Sınır dolunca ne olur.>
8. <Kalıcılık. Örnek: sayfa yenilense de liste ve kalan hak korunur.>
9. <Hata durumu, mesajıyla. Örnek: işlem başarısız olursa "…" mesajı görünür.>
10. <Güvenlik. Örnek: anahtar tarayıcıya giden hiçbir dosyada görünmez; aynı adresten saatte N'den fazla istek reddedilir ve "…" mesajı çıkar.>
11. <Ekran boyutu. Örnek: 390 piksel genişlikte her şey tek sütunda, taşmadan çalışır.>

## Yeni özellikler (sürüm 2)
<!-- Yeni özellik eklerken ÖNCE buraya kuralını yaz, SONRA ajana "N. kuralı uygula" de. -->
12. <Yeni kural.>

<!--
YENİ KURAL EKLERKEN ÜÇ SORU
- Bu kural eski bir kuralın sayısıyla çakışıyor mu? (Örnek: "saatte en fazla 10" ile "sınırsız".) Çakışıyorsa hangisinin geçerli olduğunu buraya yaz.
- İki ayrı ajan iki ayrı kuralı uygulayacaksa, ikisinin de dokunacağı ortak şey ne? (Sayaç, liste, ortak düğme.)
- Bu kuralı uygulamayı açıp nasıl denerim? Deneyemiyorsam kural yeterince net değil.
-->
