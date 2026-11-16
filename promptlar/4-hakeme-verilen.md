# Hakeme verilen mesaj

Hakeme (videoda TestSprite) yalnız iki şey verildi: yayındaki uygulamanın adresi ve tarif. Kod yok, ajanların yazdığı testler yok.

Sohbet kutusuna yazılan mesaj, kelimesi kelimesine (tarifin 15 kuralı İngilizce özetlenerek aynı mesaja yapıştırıldı):

```
Test the live app https://odam-birlesik.vercel.app against its PRD below. It is "Odam", a Turkish AI room-redesign web app (like Home AI). No login. The AI image service runs in demo mode and returns a sample image, which is expected. Build the test plan from the PRD rules, especially the free-credit rules (3 free designs, failed design does not use a credit, Premium screen at 0, invite +1 credit max 3, "Yeniden üret" uses a credit). PRD (Turkish): 1) Upload accepts only JPG/PNG/WEBP, max 10 MB, with the exact warning texts "Yalnızca JPG, PNG veya WEBP yükleyebilirsin" and "Fotoğraf 10 MB'tan büyük olamaz"; photo is previewed. 2) Room type single choice: Salon, Yatak odası, Mutfak, Banyo, Çalışma odası. 3) Style single choice, 8 cards: Modern, İskandinav, Endüstriyel, Bohem, Minimalist, Japandi, Klasik, Akdeniz, each shows a 3-color palette. 4) "Tasarla" is disabled until photo, room type and style are chosen. 5) While generating, "Tasarlanıyor…" and a progress indicator show; a second generation cannot start. 6) Result shows a before/after slider. 7) Every user has 3 free designs, header shows "Kalan hak: N"; each successful design uses 1; a failed one uses none. 8) At 0 credits the button becomes "Premium'a geç" and opens a Premium screen saying "Yakında", no payment. 9) "Tasarımlarım" lists all designs newest first with room type, style and date; list and credits survive a page reload. 10) "İndir" downloads the new image. 11) On failure the message "Tasarım oluşturulamadı, hakkın düşmedi" shows. 12) The AI key never appears in browser files; more than 10 generations per hour from one IP are refused with "Çok fazla deneme, biraz sonra tekrar dene". 13) At 390px width everything is one column without overflow. 14) "Arkadaşını davet et" creates a personal invite link; a first-time visitor via the link gets +1 credit and the inviter gets +1; one person can earn from at most 3 invites. 15) "Yeniden üret" on the result creates a new variation with the same photo, room type and style, adds it to "Tasarımlarım", and uses 1 credit like any successful design.
```

## Kendi mesajını yazarken
- İlk cümle: uygulamanın adresi ve "aşağıdaki tarife göre test et".
- Uygulamayı iki cümleyle tanıt (ne yapar, giriş var mı).
- Beklenen ama hata gibi görünebilecek şeyi önceden söyle (burada: görsel servisi demo modunda örnek görsel döndürür).
- En çok önem verdiğin kuralları ayrıca işaretle (burada: ücretsiz hak kuralları).
- Sonra tarifin kurallarını numarasıyla yapıştır.
