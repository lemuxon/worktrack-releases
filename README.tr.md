<div align="center">

# WorkTrack Enterprise

**Küçük ve orta ölçekli işverenler için çevrimdışı personel devam takibi ve bordro.**

Sunucu yok. Bulut hesabı yok. Abonelik yok.
Tek bir Windows makinesi, tek bir veritabanı dosyası, tek bir kurulum paketi.

[İndir](../../releases) · [English](README.md)

</div>

---

![Özet](docs/screenshots/01-dashboard.png)

## Çözdüğü sorun

Küçük üreticiler saatleri kâğıda yazar, ay sonunda ücret hesaplamak için
tabloya yeniden girer. Bu döngü hem saatler alır hem de sessizce yanlış sayı
üretir — atlanan bir geç giriş, yanlış yazılan bir mesai saati ve bordro daha
kimse bakmadan hatalıdır.

WorkTrack devam kaydını tutar ve **bordroyu ondan türetir**; ikisi birbirinden
ayrışamaz.

## Devam takibi

Giriş, çıkış, yemek ve ara molaları, kişi başına günlük hedef, tolerans
penceresiyle geç kalma eşiği. Durum yazılmaz, hesaplanır.

![Devam](docs/screenshots/02-attendance.png)

## Bordro yeniden girilmez, türetilir

Normal ve fazla mesai saatleri ayrıştırılıp kişinin kendi ücretiyle fiyatlanır.
Aylık net bordro kademeli gelir vergisi dilimlerini, asgari ücret istisnasını,
SGK ve işsizlik primlerini, damga vergisini, tavanıyla birlikte kıdem ve ihbar
tazminatını uygular.

![Bordro](docs/screenshots/03-payroll.png)

Tüm oranlar Ayarlar'dan düzenlenebilir — vergi dilimleri, asgari ücret, işveren
prim oranları. Çünkü bunlar her yıl değişir ve son sözü yazılım satıcınız değil,
mali müşaviriniz söylemelidir.

## İstatistik

![İstatistik](docs/screenshots/04-analytics.png)

## Aylık puantaj

Kişi ve ay bazında: çalışılan gün, devam oranı, geç kalmalar, kalan izin ve
resmî tatiller. Muhasebenin beklediği resmî puantaj cetvelini PDF veya Excel
olarak verir.

![Takvim](docs/screenshots/05-calendar.png)

## İK dosyası

Süre takipli belgeler (süresi geçmiş bir İSG sertifikası yasal risktir; dolmadan
önce uyarılır), zimmetler, ücret geçmişi ve fazla mesai onay akışı.

![İK](docs/screenshots/06-hr-records.png)

## Raporlar

![Raporlar](docs/screenshots/07-reports.png)

## Türkçe veya İngilizce arayüz

Arayüz çalışma anında değişir. **Üretilen belgeler Türkçe kalır** — bordro
pusulası ve puantaj cetveli resmî kurumlara verilir, İngilizce sürümlerinin
hukuken bir karşılığı yoktur.

![Ayarlar](docs/screenshots/08-settings.png)

---

## Kurulum

En son kurulum paketini [Releases](../../releases) sayfasından indirip
çalıştırın.

- Program Files'a kurulduğunda veriler `%APPDATA%\WorkTrack` altına yazılır.
- İlk kullanıcı `admin` / `1234`'tür; uygulama şifreyi değiştirmeden devam
  etmenize izin vermez.
- Lisanssız kullanım **30 gün deneme** modundadır.

> Kurulum paketi henüz kod imzalı değildir; Windows SmartScreen ilk çalıştırmada
> "bilinmeyen yayımcı" uyarısı gösterir.

**Gereksinimler:** 64 bit Windows; Windows 10 ve 11 üzerinde geliştirilip
sınandı. Kurulacak çalışma zamanı, veritabanı sunucusu veya internet bağlantısı
gerekmez.

## Ne gönderir: hiçbir şey

Uygulama ağa tek bir yerde çıkar — güncelleme denetimi — ve o denetim hiçbir
veri göndermez. Bu depodaki statik bir dosya (`surum.json`) için tek bir GET
yapar ve içinden sürüm numarasını okur.

Telemetri yok, hesap yok, lisans doğrulama çağrısı yok.

## Güncellemeye nasıl güvenilir

Otomatik güncelleyici tanımı gereği uzaktan kod çalıştırma kanalıdır; bu yüzden
güven taşımaya değil **imzaya** dayanır:

```
imzalı bildirim → sürüm karşılaştırma → sizin onayınız → indirme
               → SHA-256, imzalı bildirimdeki özetle karşılaştırılır
               → kurulum
```

`surum.json` satıcının özel anahtarıyla imzalanır ve kurulum paketinin SHA-256
özetini taşır. Uygulama önce imzayı, sonra indirdiği dosyanın bu özetle
eşleştiğini doğrular. **Özet tutmazsa dosya çalıştırılmaz, silinir.**

Yani sunucu ele geçirilse bile ne sahte bir sürüm duyurulabilir ne de kurulum
paketi takas edilebilir. HTTPS burada güvenin kaynağı değil, ek bir katmandır.

## Lisans

Tescilli yazılım, tüm hakları saklıdır. Kullanım koşulları kurulumla gelen
`LISANS_SOZLESMESI.txt` dosyasındadır.

Kaynak kod bu depoda yayımlanmaz.
