# 🌀 Portal 3 — Makinelerin Dili

```
╔════════════════════════════════════════╗
║  NEXUS Portal Sistemi — Portal 3/10   ║
║  Tür: Binary (İkili Sayı) Çözme       ║
╚════════════════════════════════════════╝
```

Burak, bu portalın anahtarını **binary (ikili sayı sistemi)** ile
şifrelemiş. Bilgisayarların dilini çözebilir misin?

---

## Binary Nedir?

Bilgisayarlar sadece 0 ve 1'lerle konuşur. Her sayı, ikili sistemde
şu şekilde yazılır:

```
İkili (Binary)  →  Onluk (Decimal)
─────────────────────────────────
00001           →  1
00010           →  2
00011           →  3
00100           →  4
00101           →  5
00110           →  6
00111           →  7
01000           →  8
01001           →  9
01010           →  10
```

**Nasıl çevriliyor?** Sağdan sola her basamak 2'nin kuvvetini temsil eder:

```
Basamak değeri:  16   8   4   2   1
Örnek sayı:       1   0   0   1   1  →  16+0+0+2+1 = 19  →  S harfi
```

## Harf-Sayı Tablosu

```
A=1   B=2   C=3   D=4   E=5   F=6   G=7   H=8   I=9
J=10  K=11  L=12  M=13  N=14  O=15  P=16  Q=17  R=18
S=19  T=20  U=21  V=22  W=23  X=24  Y=25  Z=26
```

## Şifreli Mesaj

```
╔═══════════════════════════════════════════════════════════╗
║                                                           ║
║   00011  00101  10011  00001  10010  00101  10100          ║
║                                                           ║
╚═══════════════════════════════════════════════════════════╝
```

## Görev

Her 5 bitlik grubu **onluk sayıya** çevir, sonra **harf tablosundan**
karşılığını bul. 7 harf, 7 binary grup — hepsini çöz!

**Adım adım:**
```
00011 → 0+0+0+2+1 = ?  → Harf tablosunda ? = ?
00101 → 0+0+1+0+1 = ?  → Harf tablosunda ? = ?
10011 → 16+0+0+2+1 = ? → Harf tablosunda ? = ?
00001 → 0+0+0+0+1 = ?  → Harf tablosunda ? = ?
10010 → 16+0+0+2+0 = ? → Harf tablosunda ? = ?
00101 → 0+0+1+0+1 = ?  → Harf tablosunda ? = ?
10100 → 16+0+1+0+0 = ? → Harf tablosunda ? = ?
```

> İpucu: İlk grup `00011` = 0+0+0+2+1 = 3 → Harf tablosunda 3 = C

---

Cevabını `cevaplar.py` dosyasındaki `"vaka3"` anahtarına yaz.
