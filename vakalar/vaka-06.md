# 🌀 Portal 6 — Sezar'ın Portalı

```
╔════════════════════════════════════════╗
║  NEXUS Portal Sistemi — Portal 6/10   ║
║  Tür: Sezar Şifresi                   ║
╚════════════════════════════════════════╝
```

Kübra, bu portalın anahtarını **Sezar şifresi** ile korumuş.
Julius Sezar'ın 2000 yıl önce kullandığı bu şifreleme yöntemini
çözebilir misin?

---

## Sezar Şifresi Nedir?

Her harf, alfabede **belirli bir sayı kadar kaydırılır**.

Örnek — 3 harf ileri kaydırma:
```
Orijinal:   A  B  C  D  E  F  G  ...
Şifreli:    D  E  F  G  H  I  J  ...
```

Yani `A → D`, `B → E`, `C → F` olur.

**Çözmek için:** Her harfi aynı sayı kadar **geri** kaydır!

## Şifreli Mesaj

Kübra'nın notu: *"Her harfi 3 geri kaydır."*

```
╔══════════════════════════════════════╗
║                                      ║
║       D  Q  D  K  W  D  U            ║
║                                      ║
╚══════════════════════════════════════╝
```

## Alfabe Tablosu (yardımcı)

```
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
```

## Görev

Şifreli mesajdaki her harfi **3 harf geri** kaydırarak orijinal kelimeyi bul.

```
D → 3 geri → D...C...B...?
Q → 3 geri → Q...P...O...?
D → 3 geri → ?
K → 3 geri → ?
W → 3 geri → ?
D → 3 geri → ?
U → 3 geri → ?
```

> İpucu: D'den 3 geri gidersen: D → C → B → A

---

Cevabını `cevaplar.py` dosyasındaki `"vaka6"` anahtarına yaz.
