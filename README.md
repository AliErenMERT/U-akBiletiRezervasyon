Uçak Bilet Rezervasyon Konsol Uygulaması
Dil: Java 17 | Tür: Tek-dosyalık konsol uygulaması | Veri formatı: CSV

Proje Tanımı
Bu konsol uygulaması, uçak seferlerini listeleyip yolcu rezervasyonu yapmanızı sağlar.
Veriler (uçak, lokasyon, uçuş, rezervasyon) çalışma dizinine CSV dosyaları olarak kaydedilir; böylece uygulama kapansa bile bilgiler korunur.

Temel Özellikler
Uçuş Listeleme
Tüm aktif uçuşlar, kalkış–varış havaalanı, tarih-saat ve boş koltuk sayısıyla görüntülenir.

Rezervasyon
Kullanıcı, uçuş ID’si ve yolcu bilgilerini (ad, soyad, yaş) girerek koltuk kapasitesi müsaitse rezervasyon oluşturur.

Kalıcı Depolama
Dört CSV: planes.csv, locations.csv, flights.csv, reservations.csv.

Tek Dosya Tasarımı
Main.java içinde tüm sınıflar (Plane, Location, Flight, Reservation, DataStore) ve basit CSVConvertible arayüzü bulunur.

Kurulum & Çalıştırma
# 1. Kaynak kodu indirin
Main.java

# 2. Derleyin (Java 17+ önerilir)
javac Main.java

# 3. Çalıştırın
java Main


Dosya Yapısı
.
├── Main.java              ← Tüm kaynak kod
├── planes.csv             ← (Oluşur) Uçak kayıtları
├── locations.csv          ← (Oluşur) Lokasyon kayıtları
├── flights.csv            ← (Oluşur) Uçuş kayıtları
└── reservations.csv       ← (Oluşur) Rezervasyonlar


Teknik Tasarım
| Sınıf            | Rol / Önemli Alanlar                                         |
| ---------------- | ------------------------------------------------------------ |
| `Plane`          | `model`, `brand`, `serialNumber`, `seatCapacity`             |
| `Location`       | `country`, `city`, `airport`, `active`                       |
| `Flight`         | `origin`, `destination`, `dateTime`, `plane`, `reservations` |
| `Reservation`    | Bağlı uçuş ID’si + yolcu bilgileri                           |
| `DataStore`      | Basit `save()` – tüm listeleri CSV’ye yazar                  |
| `CSVConvertible` | Nesnenin `toCSV()` metodunu garanti eden arayüz              |


