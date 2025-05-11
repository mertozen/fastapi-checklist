# FastAPI Commit Öncesi Kod Checklist

## 📝 Genel Hazırlık
- [ ] **Branch** adlandırma kurallarına uyuldu (örn. `feature/XXX-YYY`, `bugfix/AAA-BBB`)  
- [ ] Commit mesajı anlamlı ve task numarası içeriyor (örn. `TASK-123: Kullanıcı giriş endpoint’i eklendi`)  
- [ ] Kod Türkçe–İngilizce karışıklığı yok  

## 🎨 Kod Stili & Biçimlendirme
- [ ] `black` ile kod formatlandı  
- [ ] `isort` ile import’lar sıralandı  
- [ ] `flake8` ya da `pylint` hatasız çalıştı  
- [ ] `mypy` ile tip kontrolleri geçti  

## 🚀 FastAPI Özel Kuralları
- [ ] Tüm route’larda **`tags`**, **`summary`**, **`description`** tanımlı  
- [ ] Girdi/çıktı modelleri **Pydantic** ile net şekilde ayrıldı (`RequestModel`, `ResponseModel`)  
- [ ] Asenkron (`async`) fonksiyonlar gerektiği yerde kullanıldı  
- [ ] Dependency injection (`Depends`) minimal ve tek işlevli  
- [ ] Router’lar modüllere bölünmüş (örn. `app/routers/users.py`, `app/routers/items.py`)  

## 🔒 Güvenlik Kontrolleri
- [ ] **`SECRET_KEY`**, DB URL vs. `.env` ya da `secrets.toml` içinde, kodda **hard-coded** değil  
- [ ] `DEBUG=False` olarak ayarlandı  
- [ ] CORS konfigürasyonu sadece izin verilen origin’leri içeriyor  
- [ ] Gerekirse rate-limiting veya brute-force koruması uygulanmış  
- [ ] SQL enjeksiyonu, XSS, CSRF gibi yaygın açıklar için önlemler alındı  

## ✅ Test & Kalite Güvence
- [ ] `pytest` ile birim testler yazıldı  
- [ ] Minimum %80 test kapsamı sağlandı  
- [ ] Tüm testler (unit, integration) **yeşil** (başarılı)  
- [ ] API endpoint testleri için `TestClient` veya `httpx` kullanıldı  

## 📚 Dokümantasyon
- [ ] OpenAPI şeması (Swagger) eksiksiz ve doğru  
- [ ] Kritik fonksiyonlara docstring eklendi  
- [ ] README’de şu bölümler var:  
  - Kurulum adımları  
  - Çalıştırma (env, migrate, run)  
  - Test nasıl çalıştırılır  

## ⚙️ CI/CD & Migrasyon
- [ ] Pre-commit hook (`.pre-commit-config.yaml`) kurulu ve çalışıyor  
- [ ] PR açarken bu checklist işaretlendi  
- [ ] Alembic migration dosyaları oluşturuldu ve versiyonlandı  
- [ ] Migration’lar test ortamında başarıyla çalıştırıldı  

## 📈 Performans & Logging
- [ ] Uygun log seviyeleri (`INFO`, `WARNING`, `ERROR`) kullanıldı  
- [ ] Gereksiz `print`/`pdb` debug satırları silindi  
- [ ] Potansiyel yavaş sorgular işaretlendi veya optimize edildi  

## 🧹 Son Temizlik
- [ ] `TODO`/`FIXME` notları gözden geçirildi (gereksizler silindi veya issue açıldı)  
- [ ] Kullanılmayan import’lar ve kod blokları kaldırıldı  
- [ ] İşe yaramayan dosya/klasörler repodan temizlendi  
