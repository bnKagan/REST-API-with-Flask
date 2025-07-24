# 📹 Flask Video API

Bu proje, Flask, Flask-RESTful ve SQLAlchemy kullanılarak geliştirilmiş basit bir RESTful API örneğidir. Kullanıcılar videoları ekleyebilir, görüntüleyebilir, güncelleyebilir ve silebilir.

## 🛠️ Kullanılan Teknolojiler

- Python
- Flask
- Flask-RESTful
- Flask-SQLAlchemy
- SQLite

## 🚀 Kurulum ve Çalıştırma

### 1. Projeyi Klonlayın

```bash
git clone https://github.com/bnKagan/REST-API-with-Flask.git
cd REST-API-with-Flask
```

### 2. Sanal Ortam Oluşturun (Opsiyonel ama önerilir)

```bash
python3 -m venv venv
source venv/bin/activate  # Windows için: venv\Scripts\activate
```

### 3. Gerekli Paketleri Yükleyin

```bash
pip install -r requirements.txt
```

Eğer `requirements.txt` dosyası yoksa, aşağıdaki komutu kullanarak bağımlılıkları yükleyebilirsin:

```bash
pip install flask flask-restful flask-sqlalchemy
```

### 4. Uygulamayı Başlatın

```bash
python main.py
```

Uygulama `http://127.0.0.1:5000/` adresinde çalışacaktır.

## 🧪 API Uç Noktaları

### `GET /video/<video_id>`

Belirtilen ID'ye sahip videoyu döner.

### `PUT /video/<video_id>`

Yeni bir video oluşturur. Aynı ID varsa 409 hatası döner.

#### JSON Gövde:
```json
{
  "name": "Test Video",
  "views": 123,
  "likes": 45
}
```

### `PATCH /video/<video_id>`

Var olan bir videonun bilgilerini günceller.

#### Örnek JSON Gövdesi:
```json
{
  "views": 150
}
```

### `DELETE /video/<video_id>`

Belirtilen videoyu siler.

## 💾 Veritabanı

- SQLite veritabanı kullanılır.
- Uygulama ilk çalıştırıldığında `database.db` dosyası otomatik olarak oluşturulur.
- `db.create_all()` komutu, veritabanı daha önce oluşturulmuşsa yeniden yazmaz; sadece eksik tabloları oluşturur.

## 📂 Proje Yapısı

```
video-api/
├── main.py
├── database.db  # Uygulama çalışınca oluşur
├── README.md
└── requirements.txt
```

## 📝 Notlar

- Proje geliştirme ortamı için uygundur.
- Gerçek projelerde Flask-Migrate gibi migration araçları tercih edilmelidir.
- API JSON formatında veri ile çalışır.

## 👨‍💻 Geliştirici

Kağan Kubat  