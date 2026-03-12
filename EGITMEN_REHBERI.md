# 🎓 Eğitmen Rehberi — NEXUS Portal Serüveni CI/CD Bootcamp

## Konsept Özeti

Bu bootcamp, CI/CD kavramlarını **sıfır kodlama gerektiren** bir portal
macerası oyunuyla öğretir. Katılımcılar 10 farklı bulmacayı (ters yazı,
matris, binary, gizli dosya, koordinat, Sezar şifresi, akrostiş, Mors kodu,
mantık ve meta-bulmaca) çözer ve cevaplarını basit bir dosyaya yazar.
Her `git push` otomatik testleri tetikler. Tüm cevaplar doğru olduğunda
site otomatik deploy olur.

**Neden bu format?**
- Kod yazmak bilmeyenler de katılabilir (sadece bulmaca çöz + cevap yaz)
- Yapay zekaya yapıştırarak çözmek zor (gizli dosya, repo keşfi, matris)
- CI/CD döngüsünü gerçekten deneyimliyorlar (push → test → deploy)
- Hikaye ve rekabet motivasyonu yüksek tutuyor

## Cevap Anahtarı (Sadece Eğitmen İçin!)

```
Portal 1  — MERHABA    (ABAHREM'i tersten oku)
Portal 2  — ALKÜ       (Matris: (1,B)=1→A, (2,B)=12→L, (3,C)=11→K, (4,B)=21→U)
Portal 3  — CESARET    (Binary: 00011=3→C, 00101=5→E, 10011=19→S,
                         00001=1→A, 10010=18→R, 00101=5→E, 10100=20→T)
Portal 4  — EVREN      (vakalar/.kubra-gizli-portal.txt dosyasında)
Portal 5  — ROTA       (Koordinat: (1,2)=R, (2,3)=O, (3,1)=T, (2,1)=A)
Portal 6  — ANAHTAR    (Sezar -3: D→A, Q→N, D→A, K→H, W→T, D→A, U→R)
Portal 7  — LABİRENT   (Akrostiş: L-A-B-I-R-E-N-T)
Portal 8  — ARAYIŞ     (Mors: .-=A, .-.=R, .-=A, -.--=Y, ..=I, ...=S)
Portal 9  — REHBER     (Güç>6: REHBER,USTA,MENTOR →
                         Yaş<200: REHBER,USTA →
                         Ad>5 harf: REHBER)
Portal 10 — MACERALAR  (İlk harfler: M+A+C+E+R+A+L+A+R)
```

### Kübra'nın Gizli Mesajı
Her doğru cevap bir kelime açar:
```
Portal  1 → "Her"          Portal  6 → "adımla"
Portal  2 → "büyük"        Portal  7 → "başlar"
Portal  3 → "yolculuk"     Portal  8 → "NEXUS"
Portal  4 → "küçük"        Portal  9 → "seninle"
Portal  5 → "bir"          Portal 10 → "büyür"

→ "Her büyük yolculuk küçük bir adımla başlar, NEXUS seninle büyür."
```

Son reveal: "Kübra'nın aradığı yeni NEXUS'lular... SİZSİNİZ!"

## Ön Hazırlık (1 gün önce)

### Template Repo
1. GitHub'da `bootcamp` adlı public repo oluşturun
2. Dosyaları yükleyin, `cevaplar.py`'deki cevapları boşaltın
3. **Settings → Actions → General** → "Allow all actions" etkin olmalı
4. Kendiniz fork edip tüm akışı test edin

### Katılımcılara Gönderin
- GitHub hesabı açsınlar
- Git kurulumu: https://git-scm.com
- Python 3.12+: https://python.org
- VS Code (veya herhangi bir editör)
- **GitHub Desktop** (terminal kullanmak istemeyenler için alternatif)

## Bootcamp Planı (~90 dk)

### 🕐 Bölüm 1 — Giriş + Kurulum (30 dk)

| Süre | Aktivite |
|------|----------|
| 00-10 | **CI/CD Nedir?** Günlük hayattan benzetme: "Yemek tarifi yazdın, her değişiklikte otomatik tadım yapılıyor. Lezzetliyse otomatik servise çıkıyor." |
| 10-18 | **Canlı Demo:** Template repo'yu göster, bilerek yanlış cevap yaz, push et, pipeline'ın KIRMIZI olduğunu göster. Sonra doğru cevabı yaz, YEŞİL pipeline + deploy |
| 18-25 | **Herkes Fork Etsin:** Adım adım ekranı paylaşarak fork → clone → pip install |
| 25-30 | **İlk Portal Birlikte:** Portal 1'i birlikte açın, çözün, cevaplar.py'ye yazın, birlikte push edin |

### 🕐 Bölüm 2 — Portal Çözme (45 dk)

| Süre | Aktivite |
|------|----------|
| 00-05 | **Kurallar:** Her portal bağımsız, istediğinden başla. Her push'ta Actions'ı kontrol et |
| 05-40 | **Serbest Çalışma:** Katılımcılar kendi hızlarında çözer |
| 40-45 | **Durum Kontrolü:** Kim kaçıncı portalda? Scoreboard güncelleme |

**Eğitmen Stratejisi:**
- Sınıfta dolaşın, tıkananlara ipucu verin (çözümü DEĞİL!)
- 10. dakikada: "Portal 4'te gizli dosyayı `ls -a` ile bulabilirsiniz" genel ipucu
- 20. dakikada: Binary çözme için tahtaya örnek adım yazın
- Hızlı çözenleri yavaş olanlara eşleyin (pair çalışma)
- **Canlı scoreboard** tutun (aşağıdaki şablona bakın)

**Beklenen İlerleme (~10-15 dk toplam çözüm süresi):**
- Portal 1-2: Herkes 2-3 dk'da çözer
- Portal 3-6: 5-8 dk, binary ve matris biraz zaman alır
- Portal 7-9: 3-5 dk, tablo bakma işi
- Portal 10: Diğer 9'u çözmüş olanlar 1-2 dk'da çözer

### 🕐 Bölüm 3 — Deploy + Kapanış (15 dk)

| Süre | Aktivite |
|------|----------|
| 00-05 | **GitHub Pages Kurulumu:** Birlikte Settings → Pages → GitHub Actions |
| 05-10 | **İlk Deploy!** Tüm portalları çözmüş birinin sitesini canlı gösterin |
| 10-15 | **Kapanış:** Deploy URL'lerini paylaşın, NEXUS'a hoş geldiniz! |

## Olası Sorunlar

| Sorun | Çözüm |
|-------|-------|
| Fork edemiyor | Email doğrulaması gerekli olabilir |
| `pip install` hata veriyor | `python --version` kontrol (3.12+ olmalı) |
| Push yapamıyor | GitHub credential/token ayarı gerekli |
| Actions çalışmıyor | Settings → Actions → "Allow all" kontrol |
| Pages deploy olmuyor | Settings → Pages → Source: "GitHub Actions" seçili mi? |
| Portal 4: Gizli dosyayı bulamıyor | `ls -a vakalar/` veya GitHub'da klasöre tıkla |
| Türkçe karakter sorunu | Test normalizer var, büyük/küçük + Türkçe fark etmez |

## Canlı Scoreboard Şablonu

Tahtaya veya Google Sheet'e:

```
╔═══════════════╦══╦══╦══╦══╦══╦══╦══╦══╦══╦═══╦════════╗
║ Katılımcı     ║1 ║2 ║3 ║4 ║5 ║6 ║7 ║8 ║9 ║10 ║Deploy? ║
╠═══════════════╬══╬══╬══╬══╬══╬══╬══╬══╬══╬═══╬════════╣
║ Grup Alfa     ║✅║✅║✅║✅║✅║⬜║⬜║⬜║⬜║ ⬜ ║  ❌    ║
║ Grup Beta     ║✅║✅║✅║✅║✅║✅║✅║⬜║⬜║ ⬜ ║  ❌    ║
║ Grup Gamma    ║✅║✅║✅║✅║✅║✅║✅║✅║✅║ ✅ ║  ✅ 🎉 ║
╚═══════════════╩══╩══╩══╩══╩══╩══╩══╩══╩══╩═══╩════════╝
```

> 💡 Katılımcıları 3-4 kişilik gruplara ayırmanızı öneriyoruz.

## YZ İle Kopya Çekme Önlemleri

Bu format, yapay zekaya yapıştırarak çözmeyi zorlaştırır çünkü:

1. **Portal 4** repo içinde fiziksel dosya aramayı gerektirir
2. **Portal 10** diğer 9 cevabı bilmeyi gerektirir (tek seferde çözülemez)
3. Bulmacalar bağlam gerektirir (matrisler, tablolar, dosya yapısı)

Ek önlem olarak:
- Zaman sınırı koyun (ilk bitiren gruba ödül)
- Ekranlarda dolaşarak süreci gözlemleyin
- "Nasıl çözdün?" diye sorun, süreci anlatamayan kopya çekmiştir

## Bootcamp Sonrası Kaynaklar

- GitHub Actions Docs: https://docs.github.com/en/actions
- GitHub Skills: https://skills.github.com
- CI/CD Nedir?: https://www.redhat.com/en/topics/devops/what-is-ci-cd
