# WorkTrack Enterprise — dağıtım

Bu depo yalnızca **kurulum paketlerini** ve uygulamanın otomatik güncelleme
için okuduğu **imzalı sürüm bildirimini** barındırır. Kaynak kod burada
değildir.

## Kurulum

En son sürümü [Releases](../../releases) sayfasından indirin ve çalıştırın.

- Program Files'a kurulduğunda veriler `%APPDATA%\WorkTrack` altına yazılır.
- İlk kullanıcı `admin` / `1234`'tür; uygulama şifreyi değiştirmeden devam
  etmenize izin vermez.
- Lisanssız kullanım **30 gün deneme** modundadır.

## `surum.json` nedir

Uygulama açılışta bu dosyayı okuyarak yeni sürüm olup olmadığına bakar.
Dosya satıcının özel anahtarıyla **imzalıdır** ve kurulum paketinin SHA-256
özetini taşır; uygulama indirdiği dosyanın özetini bununla karşılaştırır,
tutmazsa kurulumu yapmaz.

Güncelleme denetimi uygulamanın internete çıktığı **tek** yerdir ve yalnızca
bu dosyayı okur — hiçbir kullanıcı verisi gönderilmez.

Güncelleme adresi:

```
https://raw.githubusercontent.com/lemuxon/worktrack-releases/main/surum.json
```

## Lisans

Tescilli yazılım, tüm hakları saklıdır. Kullanım koşulları kurulumla gelen
`LISANS_SOZLESMESI.txt` dosyasındadır.
