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
