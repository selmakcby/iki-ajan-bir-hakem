# Tarif: "Odam" — AI ile oda yeniden tasarım uygulaması (Home AI benzeri)

Kullanıcı odasının fotoğrafını yükler, oda tipini ve tarzı seçer; yapay zeka aynı odayı o tarzda yeniden döşenmiş hâliyle gösterir. Giriş/üyelik yok. Uygulama Vercel'e yayınlanacak.

## Görsel üretimi
- fal.ai `fal-ai/nano-banana/edit` uç noktası (`@fal-ai/client` paketi). Girdi: `prompt` + `image_urls` (dizi). Görsel başına ~0,04 $.
- Anahtar yalnızca sunucuda, `FAL_KEY` ortam değişkeninden okunur.
- `FAL_KEY` tanımlı değilse sunucu gerçek çağrı yapmaz, `public/` içindeki örnek bir sonuç görselini döndürür (geliştirme modu). Geliştirirken gerçek API'yi çağırma.
- Oda yerleşimi (duvarlar, pencereler, kapı, perspektif) korunmalı; yalnızca mobilya, renk, malzeme ve dekor değişmeli. Prompt'u buna göre sen yaz.

## Kurallar
1. Yükleme alanı yalnızca JPG, PNG ve WEBP kabul eder; başka türde "Yalnızca JPG, PNG veya WEBP yükleyebilirsin" uyarısı çıkar. 10 MB'tan büyük dosyada "Fotoğraf 10 MB'tan büyük olamaz" uyarısı çıkar. Yüklenen fotoğraf önizlenir.
2. Oda tipi seçilir (tek seçim): Salon, Yatak odası, Mutfak, Banyo, Çalışma odası.
3. Tarz seçilir (tek seçim, 8 kart): Modern, İskandinav, Endüstriyel, Bohem, Minimalist, Japandi, Klasik, Akdeniz. Her kartta tarzın adı ve 3 renklik paleti görünür.
4. "Tasarla" düğmesi fotoğraf, oda tipi ve tarz seçilmeden pasiftir.
5. Üretim sürerken "Tasarlanıyor…" yazısı ve ilerleme göstergesi görünür; düğmeye tekrar basılamaz (aynı anda ikinci üretim başlamaz).
6. Sonuç, önce/sonra karşılaştırma kaydırıcısıyla gösterilir: kaydırıcı sürüklendikçe eski ve yeni görsel arasında geçiş yapılır.
7. Her kullanıcının 3 ücretsiz tasarım hakkı vardır; ekranda "Kalan hak: N" yazar. Her başarılı üretim 1 hak düşürür. Başarısız üretim hak düşürmez.
8. Hak bitince "Tasarla" yerine "Premium'a geç" düğmesi görünür; tıklanınca Premium ekranı açılır (ödeme yok, "Yakında" yazar).
9. "Tasarımlarım" sayfası üretilen tüm tasarımları yeniden eskiye listeler; her birinde oda tipi, tarz ve tarih görünür. Sayfa yenilense de liste ve kalan hak korunur.
10. Sonuç ekranındaki "İndir" düğmesi yeni görseli bilgisayara indirir.
11. Üretim başarısız olursa "Tasarım oluşturulamadı, hakkın düşmedi" mesajı görünür.
12. Güvenlik: AI anahtarı tarayıcıya giden hiçbir dosyada görünmez. Sunucu aynı IP'den saatte 10'dan fazla üretim isteğini reddeder ve kullanıcı "Çok fazla deneme, biraz sonra tekrar dene" mesajını görür.
13. 390 piksel genişlikte (telefon) her şey tek sütunda, taşmadan çalışır.

## Yeni özellikler (sürüm 2)
14. Davet: "Arkadaşını davet et" düğmesi kişiye özel bir davet linki üretir. Link ile ilk kez gelen kişi 1 ek hak kazanır, davet eden de 1 ek hak kazanır. Bir kişi en fazla 3 davetten hak kazanabilir.
15. Yeniden üret: Sonuç ekranındaki "Yeniden üret" düğmesi aynı fotoğraf, oda tipi ve tarzla yeni bir varyasyon üretir. Yeni varyasyon da "Tasarımlarım"a eklenir.

## Yeni özellikler (sürüm 3)
16. Premium deneme: Premium ekranında "Premium'u dene" düğmesi var. Basan kullanıcı 24 saat boyunca SINIRSIZ tasarım yapar (yeniden üret dahil); bu sürede hak düşmez ve "Premium'a geç" görünmez. Ödeme yok.
17. Hızlı yeniden üret: "Yeniden üret", fotoğrafı tarayıcıdan tekrar göndermeden, sunucuda saklanan son tasarımın girdileriyle yeni varyasyon üretir (daha hızlı, daha az veri). Diğer tüm kurallar aynen geçerlidir.
