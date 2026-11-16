# Birleştirme promptu (bonus tur)

İki dal birleşirken Git iki dosyada çakışma verdi. Çakışmayı çözmesi için ajana verilen prompt:

```
Bu depoda iki dal birleştiriliyor: "feat: Premium deneme" (Claude) ve "feat: hızlı yeniden üret" (ChatGPT/Codex). Git iki dosyada çakışma verdi: src/app/api/tasarla/route.ts ve src/components/useTasarim.ts. Çakışmaları çöz: iki dalın da özelliklerini koru, tarif.md kurallarına uy. npm run build ve testler geçsin. Gerçek görsel API'sini çağırma. Bitince birleştirme commitini at (mesaj: "merge: Premium deneme + hızlı yeniden üret"). Bana soru sorma. Sonunda çakışmayı nasıl çözdüğünü 4 satırda yaz.
```

Not: Git yalnız aynı satıra dokunulan yerleri gösterir. Bu turda kod birleşti ve testler geçti; kalan sorun kodda değil, iki kuralın birbiriyle çelişmesindeydi (12. kural ile 16. kural). Onu Git göremez.
