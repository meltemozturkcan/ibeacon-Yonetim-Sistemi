# # iBeacon Yönetim Sistemi

iBeacon teknolojisini temel alan ve büyük ölçekli veri işleme kapasitesine sahip web tabanlı bir yönetim sistemidir. Sistem üç ana bileşen üzerine kurulmuştur:

1.  Veri Toplama: Gateway cihazları üzerinden gelen iBeacon sinyallerini (UUID, Major, Minor, RSSI, TxPower, Battery) gerçek zamanlı olarak toplar ve işler.
2.  Veri İşleme: Microsoft SQL Server üzerinde özel olarak geliştirilen stored procedure'ler ile:
    -   Saniyede binlerce sinyal verisini paralel işleme
    -   Optimum veri depolama ve indeksleme
    -   Gerçek zamanlı veri analizi ve filtreleme
   
3.  Analiz ve Raporlama: Web tabanlı arayüz üzerinden:
    -   Konum bazlı hareket analizi
    -   Personel ve cihaz etkileşim raporları
    -   Gerçek zamanlı dashboard görüntüleme

Sistem, özellikle büyük ölçekli üretim tesisleri ve kampüs alanları için optimize edilmiş olup, yüksek performanslı veri işleme ve analiz kabiliyetleri sunmaktadır.

> **📝 Not:** Bu proje Dataprom firmasında geliştirilmiş olup, herhangi bir gizlilik anlaşması (NDA) imzalanmamıştır. Proje kodları ve dokümantasyon açık kaynak olarak paylaşılabilir durumdadır.

## 🚀 Özellikler

### 📡 Gerçek Zamanlı iBeacon Takibi

-   Cihaz ve etiket sinyallerini anlık toplama ve işleme
-   Sinyal gücü ve pil seviyelerini izleme
-   Cihaz hareketlerini ve etkileşimlerini takip etme

### 📊 Gelişmiş Raporlama

-   Detaylı cihaz ve tag hareket raporları oluşturma
-   Geçmiş verileri  takip etme
-   Verileri çeşitli formatlarda dışa aktarma

### 🔄 Personel-Tag Eşleştirme

-   BLE Tagları personel kayıtlarıyla ilişkilendirme
-   Çalışan hareketlerini takip etme
-   Tag atamalarını dinamik olarak yönetme

### 🛠️ Cihaz Ve Tag Yönetimi

-   Yeni cihaz ve Tag ekleme ve yapılandırma
-   Cihaz ve Tag durumunu izleme
-   Cihaz ve Tag ayarlarını güncelleme

### 🖥️ Modern Web Arayüzü

-   Webix UI Framework ile geliştirilmiş
-   Tüm cihazlar için uyumlu tasarım
-   Material Design entegrasyonu

## 🏗️ Teknoloji Altyapısı

### Backend

-   **Çalışma Ortamı**: Node.js
-   **Framework**: Express.js
-   **Veritabanı**: Microsoft SQL Server
-   **Kimlik Doğrulama**: Özel middleware

### Frontend

-   **UI Framework**: Webix UI
-   **Tasarım**: Material Design Icons
-   **Temel**: HTML5, CSS3, JavaScript
-   **Uyumlu Tasarım**: Mobil ve masaüstü uyumlu


## 💻 Kullanım Örnekleri

### Tag Listesini Getirme

`fetch('/api/tag/list') 
.then(response  => response.json())
.then(data  =>  console.log('Etiketler:', data)) 
.catch(error  =>  console.error('Hata:', error));`

### Yeni Cihaz Ekleme

`const cihazVerisi =  {   MAC_Adres:  "00:11:22:33:44:55", IP_Adres:  "192.168.1.100", Konum:  "Ana Ofis", Aciklama1:  "Giriş Noktası" };  
 fetch('/api/cihaz/ekle',  {   method:  'POST', headers:  { 'Content-Type':  'application/json' },
 body:  JSON.stringify(cihazVerisi) })   
.then(response  => response.json())
.then(data  =>  console.log('Cihaz eklendi:', data)) 
.catch(error  =>  console.error('Hata:', error));`

### Tag Sinyal Raporu Oluşturma

`const raporParametreleri =  {   startDate:  "2024-01-01 00:00:00", endDate:  "2024-01-31 23:59:59", macAddress:  "00:11:22:33:44:55" };   
fetch('/api/tag-report',  {   method:  'POST', headers:  { 'Content-Type':  'application/json' }, 
body:  JSON.stringify(raporParametreleri) })   
.then(response  => response.json()) .then(data  =>  console.log('Rapor:', data)) 
.catch(error  =>  console.error('Hata:', error));`

## 🛡️ Güvenlik Özellikleri

### SQL Enjeksiyon Koruması

-   Parametreli sorgular
-   Girdi doğrulama ve temizleme
-   Hazırlanmış ifadeler

### CORS Güvenliği

-   Yapılandırılmış cors middleware
-   Korumalı API endpoint'leri
-   Kaynak doğrulama

### Veri Koruması

-   Şifrelenmiş bağlantılar
-   Güvenli parola saklama
-   Oturum yönetimi

## 📄 Lisans

Bu proje MIT Lisansı altında lisanslanmıştır - detaylar için [LICENSE.md](LICENSE.md) dosyasına bakınız.

## 👥 Yazarlar

-   Meltem Öztürkcan

## 🙏 Teşekkürler

-   Mükemmel UI bileşenleri için Webix UI Framework ekibine
-   Sağlam backend framework'ü için Node.js topluluğuna
-   Bu projenin şekillenmesine yardımcı olan tüm katkıda bulunanlara
