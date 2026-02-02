# 🚦 Dynamic Urban Transportation Route Planner
### Dinamik Şehir İçi Ulaşım Rota Planlama Sistemi

> Otobüs, tramvay ve taksiyi tek bir graf yapısı altında birleştiren;  
> ücret, süre ve mesafe kriterlerine göre en uygun rotayı hesaplayan  
> **modüler ve genişletilebilir** ulaşım planlama sistemi.

---

## 📌 Proje Özeti

Bu proje, şehir içi ulaşımda **çok modlu rota planlama** problemini ele alan,
**graf teorisi** ve **nesne yönelimli tasarım prensipleri** üzerine kurulmuş
dinamik bir sistemdir.

Kullanıcılar:

- Başlangıç ve varış noktalarını **interaktif harita** üzerinden seçebilir
- **Yolcu tipi** (Öğrenci / Yaşlı / Genel)
- **Ödeme yöntemi** (Nakit / Kredi Kartı / Kentkart)
- **Optimizasyon kriteri** (En ucuz / En hızlı / En kısa)

belirleyerek kendileri için **en uygun güzergâhı** anlık olarak elde edebilir.

---

## 🎯 Problemin Tanımı

Geleneksel ulaşım sistemleri:

- Tek ulaşım moduna odaklanır
- Kullanıcı tercihlerini yeterince dikkate almaz
- Dinamik genişlemeye kapalıdır

Bu proje, **çoklu ulaşım modlarını**, **farklı kullanıcı profillerini** ve
**fiyatlandırma politikalarını** tek bir mimari altında birleştirerek
bu eksikleri gidermeyi hedefler.

---

## 🧠 Temel Yaklaşım

### 🔹 Graf Tabanlı Modelleme

- Her **durak** bir düğüm (vertex)
- Duraklar arası bağlantılar **kenar** (edge)
- Kenar ağırlıkları:
  - Mesafe
  - Süre
  - Ücret

### 🔹 Dijkstra Algoritması

- En kısa yol problemi çözümü
- Ağırlık türü **dinamik** olarak seçilebilir
- Kullanıcı tercihine göre:
  - En ucuz
  - En hızlı
  - En kısa rota hesaplanır

---

## 🧩 Mimari Tasarım

### 🏗️ Nesne Yönelimli Tasarım (OOP)

Sistem, **soyut sınıflar ve arayüzler** kullanılarak modüler şekilde
tasarlanmıştır. Bu yaklaşım sayesinde yeni ulaşım araçları, ödeme
yöntemleri veya yolcu tipleri mevcut kodu değiştirmeden sisteme
eklenebilir.

Bu yapı, Open/Closed Principle (Açık/Kapalı Prensibi) ile uyumludur.

## 🧠 Strategy Design Pattern

Rota hesaplama işlemleri **Strategy Pattern** kullanılarak
soyutlanmıştır. Her optimizasyon kriteri ayrı bir strateji olarak
tanımlanmıştır.

### Mevcut rota stratejileri:

- CheapestRouteStrategy (En Ucuz Rota)
- FastestRouteStrategy (En Hızlı Rota)
- ShortestRouteStrategy (En Kısa Rota)
- BusRouteStrategy
- TramRouteStrategy
- TaxiRouteStrategy

Bu yapı sayesinde:

- Kod tekrarından kaçınılmıştır
- Yeni rota kriterleri kolayca eklenebilir
- Algoritma bağımsızlığı sağlanmıştır

---

## 🌍 Ön Yüz ve Harita Entegrasyonu

Sistem, **Leaflet.js** kullanılarak geliştirilen interaktif bir harita
arayüzüne sahiptir.

Harita üzerinde:

- Duraklar işaretlenir
- Hesaplanan rotalar çizilir
- Farklı ulaşım türleri farklı renklerle gösterilir

Kullanıcıya sunulan bilgiler:

- Toplam ücret
- Toplam süre
- Toplam mesafe
- Kullanılan ulaşım türleri

Bu sayede kullanıcı, rotayı hem **görsel** hem **sayısal** olarak
değerlendirebilir.

---

## ⚙️ Kullanılan Teknolojiler

| Katman | Teknoloji |
|------|----------|
| Backend | Java |
| Yazılım Mimarisi | OOP, Strategy Pattern |
| Algoritmalar | Dijkstra |
| Veri Formatı | JSON |
| Harita | Leaflet.js |
| IDE | Visual Studio Code |
| Veri İşleme | Gson |

---

## 🧪 Test ve Doğrulama

Sistem aşağıdaki senaryolar altında test edilmiştir:

- Sadece taksi kullanılan rotalar
- Sadece tramvay kullanılan rotalar
- Otobüs + tramvay + taksi içeren karma rotalar

Ek olarak:

- Rota bulunamadığında anlamlı hata mesajları üretilmiştir
- Hesaplamalar düşük gecikme ile gerçekleştirilmiştir
- Kullanıcı parametrelerine göre doğru sonuçlar elde edilmiştir

---

## 🔮 Genişletilebilirlik ve Esneklik

Bu mimari aşağıdaki genişletmelere uygundur:

- 🚲 Elektrikli scooter entegrasyonu
- 🚕 Otonom taksi eklenmesi
- 👴 Yaşlı yolcular için ücretsiz seyahat sınırı
- 💳 Yeni ödeme yöntemleri
- 🗺️ Farklı şehir verileri

Yeni bir ulaşım aracı eklemek için:

- Yeni bir sınıf tanımlanır
- Gerekirse yeni bir rota stratejisi eklenir
- Mevcut kod değiştirilmez

---

## 📊 Akademik ve Teknik Değer

Bu proje:

- Graf teorisinin pratik bir uygulamasını
- SOLID prensiplerinin gerçek kullanımını
- Algoritma ve yazılım mimarisinin entegrasyonunu
- Ölçeklenebilir sistem tasarımını

başarılı şekilde ortaya koymaktadır.

---

## 👥 Geliştiriciler

- **Saffet Hakan Koçak**
- **Yusuf Bülbül**

> Kocaeli Üniversitesi  
> Bilgisayar Mühendisliği  
> Programlama Laboratuvarı II – Proje I


