# İki Ajan, Bir Hakem

Claude ve ChatGPT'ye aynı uygulamayı aynı tarifle yaptırdığım, sonra ikisini aynı koda aynı anda soktuğum videonun dosyaları.

Video: YAKINDA

## Burada ne var

| Dosya | Ne işe yarar |
|---|---|
| [`tarif-sablonu.md`](tarif-sablonu.md) | Kendi uygulaman için dolduracağın boş tarif. Buradan başla. |
| [`hakem-kontrol-listesi.md`](hakem-kontrol-listesi.md) | Ajanların işini birleştirdikten sonra uygulamaya nasıl baktıracağın, adım adım. |
| [`tarif/tarif-v1.md`](tarif/tarif-v1.md) | Videodaki "Odam" uygulamasının ilk tarifi: 13 kural. İki ajana da bu verildi. |
| [`tarif/tarif-v2.md`](tarif/tarif-v2.md) | İki yeni özellik eklenmiş hali: 15 kural (davet, yeniden üret). |
| [`tarif/tarif-v3.md`](tarif/tarif-v3.md) | Bonus turdaki hali: 17 kural. 12. ve 16. kural birbiriyle çelişiyor; videoda yakalanan çelişki bu. |
| [`promptlar/`](promptlar) | Ajanlara ve hakeme verdiğim promptlar, kelimesi kelimesine. |

## Videonun üç dersi

1. **Ajanın kendi yazdığı test hatayı yakalamaz, korur.** Doğru cevabı kendi yazdığı koddan alır; kod yanlışsa test de yanlışı doğru sayar.
2. **Doğru cevabı kodun dışında tut.** Uygulamanın ne yapması gerektiğini madde madde bir tarif dosyasına yaz. Kod değişir, tarif ancak sen karar verirsen değişir.
3. **Birleştirdikten sonra bağımsız bir hakem baktır.** İki ajanın işi ayrı ayrı doğru olabilir; hata, ikisi yan yana gelince ve kimsenin bakmadığı yerde çıkar.

Hangi ajanı kullandığın fark etmez. Tarif sabit kalır, kod ona uyar.

## Nasıl kullanılır

1. `tarif-sablonu.md` dosyasını kendi projene kopyala, adını `tarif.md` yap ve doldur.
2. Ajanına işi verirken tarifi göster. Örnek: [`promptlar/1-ilk-yapim.md`](promptlar/1-ilk-yapim.md).
3. Yeni özellik eklerken önce tarife yeni kuralı yaz, sonra ajana "şu kuralı uygula" de. Örnek: [`promptlar/2-yeni-ozellik.md`](promptlar/2-yeni-ozellik.md).
4. Birleştirdikten sonra [`hakem-kontrol-listesi.md`](hakem-kontrol-listesi.md) ile yayındaki uygulamaya baktır.

## Videoda ne oldu

- Aynı tarifle Claude (Claude Code) uygulamayı 9 dakika 18 saniyede, ChatGPT (Codex) 30 dakika 32 saniyede bitirdi.
- İki ajan aynı uygulamaya, birbirinden habersiz, birer özellik ekledi. İkisinin de kendi testleri geçti.
- Birleşmiş ve yayına alınmış uygulamada hakem iki gerçek hata buldu: 3 bedava hak sınırı aynı anda gelen isteklerle delinebiliyordu, hak sayısı da sunucu kopyaları arasında zıplıyordu.
- Bonus turda iki kural birbiriyle çelişti: 12. kural "saatte en fazla 10", 16. kural "Premium denemede sınırsız".

Videoda hakem olarak TestSprite kullanıldı (ücretli iş birliği): https://www.testsprite.com/?via=selma-k-2611a

Uygulamanın kaynak kodu bu depoda yok; burada yalnız tarifler, promptlar ve şablonlar var.

## Lisans

Tüm hakları saklıdır. Şablonları (`tarif-sablonu.md`, `hakem-kontrol-listesi.md`) kendi projelerinde doldurup kullanabilirsin. Ayrıntı: [LICENSE](LICENSE).
