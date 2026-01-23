# Hastane Yönetim Sistemi

## 📋 Proje Açıklaması

Bu proje, doktor ve hasta yönetimi için geliştirilmiş kapsamlı bir hastane yönetim sistemidir. Sistem, randevu yönetimi, hasta kayıtları, doktor bilgileri ve tıbbi raporlar gibi 
temel hastane işlevlerini içermektedir.

## 🛠️ Kullanılan Teknolojiler 

### Frontend
- **HTML5** - Web sayfası yapısı
- **CSS3** - Stil ve tasarım
- **JavaScript** - Kullanıcı etkileşimleri ve dinamik içerik

### Backend 
- **Node.js** - Sunucu tarafı işlemleri 
- **Express.js** - Web sunucusu ve API geliştirme  
- **MySQL** - Veritabanı yönetim sistemi
- **Faker.js** - Test verisi oluşturma 
 
## 📊 Veritabanı Yapısı 

### Tablolar

#### 1. `doctors` - Doktor Bilgileri
```sql
- id (INT, Primary Key, AUTO_INCREMENT)
- name (VARCHAR(255))
- department (VARCHAR(255))
- username (VARCHAR(255), UNIQUE)
- password (VARCHAR(255))
```

#### 2. `patients` - Hasta Bilgileri
```sql
- id (INT, Primary Key, AUTO_INCREMENT)
- firstName (VARCHAR(255))
- lastName (VARCHAR(255))
- age (INT)
- gender (VARCHAR(10))
- password (VARCHAR(255))
```

#### 3. `appointments` - Randevu Bilgileri
```sql
- id (INT, Primary Key, AUTO_INCREMENT)
- appointmentDate (DATE)
- appointmentTime (TIME)
- doctor_id (INT, Foreign Key)
- patient_id (INT, Foreign Key)
```

#### 4. `medicalReports` - Tıbbi Rapor Bilgileri
```sql
- id (INT, Primary Key, AUTO_INCREMENT)
- reportDate (DATE)
- reportContent (TEXT)
- doctor_id (INT, Foreign Key)
- patient_id (INT, Foreign Key)
``` 

## 🚀 Kurulum ve Çalıştırma

### Gereksinimler
- Node.js (v14 veya üzeri)
- MySQL (v8.0 veya üzeri)
- npm veya yarn

### Kurulum Adımları

1. **Projeyi klonlayın:**
```bash
git clone https://github.com/umitdansuk/hastane-yonetim-sistemi.git
cd hastane-yonetim-sistemi
```

2. **Gerekli paketleri yükleyin:**
```bash
npm install
```

3. **MySQL veritabanını kurun:**
```sql
CREATE DATABASE hospital_management;
USE hospital_management;
```

4. **Veritabanı tablolarını oluşturun:**
```bash
# SQL dosyasını çalıştırın
mysql -u root -p hospital_management < database/schema.sql
```

5. **Çevre değişkenlerini ayarlayın:**
```bash
# .env dosyası oluşturun
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_password
DB_NAME=hospital_management
PORT=3000
```

6. **Sunucuyu başlatın:**
```bash
npm start
```

7. **Tarayıcınızda açın:**
```
http://localhost:3000
```

## 🔧 Proje Yapısı

```
hastane-yonetim-sistemi/
├── public/
│   ├── css/
│   │   └── style.css
│   ├── js/
│   │   └── script.js
│   └── images/
├── views/
│   ├── index.html
│   ├── doctor-login.html
│   ├── patient-login.html
│   ├── doctor-dashboard.html
│   └── patient-dashboard.html
├── routes/
│   ├── doctors.js
│   ├── patients.js
│   ├── appointments.js
│   └── reports.js
├── database/
│   ├── connection.js
│   ├── schema.sql
│   └── seed.js
├── server.js
├── package.json
└── README.md
```

## 📱 Özellikler

### Doktor Paneli
- ✅ Güvenli giriş sistemi
- ✅ Randevu yönetimi
- ✅ Hasta bilgilerini görüntüleme
- ✅ Tıbbi rapor oluşturma ve düzenleme
- ✅ Randevu ekleme ve güncelleme

### Hasta Paneli
- ✅ Hasta kayıt sistemi
- ✅ Güvenli giriş
- ✅ Randevu görüntüleme
- ✅ Tıbbi raporları görüntüleme
- ✅ Kişisel bilgileri yönetme

### Sistem Özellikleri
- ✅ Responsive tasarım
- ✅ Kullanıcı dostu arayüz
- ✅ Güvenli veri işleme
- ✅ Test verisi oluşturma (Faker.js)


## 🧪 Test Verisi

Proje, Faker.js kullanılarak test verisi oluşturma özelliğine sahiptir:

```bash
# Test verisi oluşturmak için
npm run seed
```

## 📝 API Endpoints

### Doktor Endpoints
```
POST /api/doctors/login      - Doktor girişi
GET  /api/doctors/:id        - Doktor bilgileri
PUT  /api/doctors/:id        - Doktor bilgilerini güncelle
```

### Hasta Endpoints
```
POST /api/patients/register  - Hasta kaydı
POST /api/patients/login     - Hasta girişi
GET  /api/patients/:id       - Hasta bilgileri
PUT  /api/patients/:id       - Hasta bilgilerini güncelle
```

### Randevu Endpoints
```
GET  /api/appointments       - Tüm randevular
POST /api/appointments       - Yeni randevu
PUT  /api/appointments/:id   - Randevu güncelle
DELETE /api/appointments/:id - Randevu sil
```

### Rapor Endpoints
```
GET  /api/reports/patient/:id - Hasta raporları
POST /api/reports             - Yeni rapor
PUT  /api/reports/:id         - Rapor güncelle
```

## 🚀 Gelecek Geliştirmeler

- [ ] Email bildirim sistemi
- [ ] SMS ile randevu hatırlatma
- [ ] Mobil uygulama desteği
- [ ] Gelişmiş raporlama sistemi
- [ ] Ödeme sistemi entegrasyonu
- [ ] Çoklu dil desteği
- [ ] Role-based access control (RBAC)

## 🤝 Katkıda Bulunma

1. Projeyi fork edin
2. Yeni bir branch oluşturun (`git checkout -b feature/yeni-ozellik`)
3. Değişikliklerinizi commit edin (`git commit -am 'Yeni özellik eklendi'`)
4. Branch'inizi push edin (`git push origin feature/yeni-ozellik`)
5. Pull Request oluşturun


## 👨‍💻 Geliştirici

**Ümit Dansuk**  
Bilgisayar Mühendisliği

## 📞 İletişim

- GitHub: [@umitdansuk](https://github.com/umitdansuk)
- Email: umitdansuk@gmail.com


## 📚 Referanslar

- [Node.js Resmi Dokümantasyonu](https://nodejs.org/docs/)
- [MySQL Resmi Dokümantasyonu](https://dev.mysql.com/doc/)
- [Faker.js Kütüphanesi](https://fakerjs.dev/)
- [MDN Web Docs](https://developer.mozilla.org/)

---
