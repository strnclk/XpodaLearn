# XpodaLearn

# 🚀 İlk Uygulamanızı Oluşturun – Önemli Noktalar ve Uyarılar

* Form oluşturma
* Table Name (Tablo Adı) kuralları
* Field Name (Alan Adı) kuralları
* Veri tabanı güvenliği
* Modül ve form limitleri


## 🗄️ Table Name (Tablo Adı) Kuralları

Form özelliklerinde bulunan **Table Name** alanı, veri tabanında oluşturulacak tablonun adını temsil eder.

### ⚠️ Dikkat Edilmesi Gerekenler:

* ❌ Türkçe karakter kullanılamaz
* ❌ Özel karakter kullanılamaz
* ❌ Sayı ile başlayamaz
* ✅ Sadece `_` (alt çizgi) kullanılabilir
* ✅ Büyük harf kullanılması önerilir

### ✅ Önerilen Yaklaşım

Projede tablolar için bir **ön ek (prefix)** belirlemek sistematik ilerlemeyi kolaylaştırır.

**Örnek:**

```text
HR_EMPLOYEE
HR_LEAVE
CRM_CUSTOMER
```

Bu yapı sayesinde proje büyüdüğünde tablo yönetimi çok daha düzenli olur.

---

## 🧾 Field Name (Alan Adı) Kuralları

Form içindeki elemanların `name` özelliği, veri tabanındaki kolon adını oluşturur.

### ⚠️ Kurallar:

* ❌ Türkçe karakter kullanılmaz
* ❌ Özel karakter kullanılmaz
* ❌ Sayı ile başlamaz
* ✅ Sadece `_` kullanılabilir
* ✅ PascalCase kullanılması önerilir

### 🔤 PascalCase Nedir?

Her kelimenin ilk harfi büyük yazılır.

**Örnek:**

```text
FirstName
LastName
BirthDate
EmployeeCode
```

Bu yöntem kod okunabilirliğini artırır.

---

## 🔐 Veri Güvenliği ve Alan Güncelleme Mantığı

Xpoda Studio’da form alanı değiştirildiğinde:

* Alan adı değiştirilirse 👉 veri tabanındaki eski kolon adı değişmez.
* Yeni bir kolon oluşturulur.
* Eski kolon veri güvenliği sebebiyle silinmez.
* Silinen alanlar veri tabanında pasif olarak kalır.

Bu nedenle:

> 🚨 Form alan isimleri belirlenirken dikkatli planlama yapılmalıdır.

---

## 📦 Modül ve Form Limitleri

* 1 modül içinde **1 adet akış (flow)** bulunabilir.
* En fazla **15 form** oluşturulabilir.
* Aynı firmadaki tüm modüller ve formlar birbiriyle ilişkilendirilebilir.

Bu yapı büyük sistem tasarımlarında mimari planlamayı önemli hale getirir.

---

## 🏗️ En İyi Uygulamalar (Best Practices)

✔ Proje başında tablo isimlendirme standardı belirle
✔ Alan isimlerini baştan netleştir
✔ Gereksiz alan değişikliklerinden kaçın
✔ Modül yapısını önceden planla
✔ İlişkisel veri yapısını düşünerek ilerle







Aşağıya, bu ders sayfasındaki içeriğe göre hazırlanmış, GitHub’a koyabileceğin temiz ve teknik bir README taslağı bırakıyorum 👇

---

# 🧩 Basit Bir Kullanıcı Arayüzü Oluşturmak

Bu çalışma, **Xpoda Studio** üzerinde basit bir form tasarımı oluştururken dikkat edilmesi gereken teknik kuralları ve veri tabanı bağlantı mantığını kapsamaktadır.

Bu derste:

* Form özelliklerinin düzenlenmesi
* Tablo ve alan isimlendirme kuralları
* Veri tipi yönetimi
* Açılır kutu (Dropdown) yapılandırması
* Veri tabanı bağlantı mantığı

öğrenilmektedir.

---

## 🏗️ 1. Form Özellikleri

Form tasarımına başlamadan önce:

* Form adı belirlenir.
* Table Name (Tablo adı) tanımlanır.
* Veri tabanı bağlantı yapısı planlanır.

### ⚠️ Tablo Adı Kuralları

* ❌ Türkçe karakter kullanılamaz
* ❌ Özel karakter kullanılamaz
* ❌ Sayı ile başlayamaz
* ✅ Yalnızca `_` (alt çizgi) kullanılabilir

**Örnek:**

```text
EMPLOYEE_FORM
USER_PROFILE
CUSTOMER_RECORD
```

---

## 🧾 2. Field (Alan) Yapısı

Form içerisindeki her bileşenin `name` alanı:

👉 Veri tabanında açılacak kolon adını temsil eder.

### ⚠️ Alan Adı Kuralları

* ❌ Türkçe karakter yok
* ❌ Özel karakter yok
* ❌ Sayı ile başlangıç yok
* ✅ Alt çizgi kullanılabilir

**Örnek:**

```text
FirstName
LastName
EmailAddress
PhoneNumber
```

---

## 🗃️ 3. Veri Tipi – nvarchar Kullanımı

Metinsel veriler veri tabanında:

```text
nvarchar
```

tipinde saklanmaktadır.

### Önemli Nokta:

* nvarchar için maksimum karakter sayısı belirtilmelidir.
* Varsayılan değer: **50 karakter**

Eğer daha uzun veri saklanacaksa bu değer artırılmalıdır.

**Örnek:**

```text
nvarchar(100)
nvarchar(250)
```

Yanlış karakter uzunluğu veri kesilmesine neden olabilir.

---

## 🔽 4. Açılır Kutu (Dropdown) Yapılandırması

### 4.1 Sabit Değer Kullanımı

Değerler alt alta yazılır.

```text
Birinci Seçenek
İkinci Seçenek
Üçüncü Seçenek
```

### 4.2 Görüntülenen ve Kaydedilen Değer Farklıysa

Yıldız (`*`) karakteri ile ayrılır:

```text
Birinci Seçenek*1
İkinci Seçenek*2
Üçüncü Seçenek*3
```

👉 Sol taraf kullanıcıya gösterilir.
👉 Sağ taraf veri tabanına kaydedilir.

---

## 🗄️ 4.3 Veri Tabanından Dropdown Besleme

Eğer açılır kutu veri tabanından doldurulacaksa:

* Sorgu **2 kolon** döndürmelidir.
* 1. kolon → Veri tabanına kaydedilecek değer
* 2. kolon → Kullanıcıya gösterilecek değer

Örnek SQL Mantığı:

```sql
SELECT Id, FullName FROM Employees
```

* `Id` → Kaydedilen değer
* `FullName` → Görüntülenen değer

---

## 🎯 Öğrenim Kazanımları

Bu ders sonunda:

* Form ile veri tabanı arasındaki ilişkiyi anlayabilme
* Alan isimlendirme standartlarını uygulayabilme
* Dropdown veri yapısını doğru kurgulayabilme
* nvarchar veri limitlerini bilinçli belirleyebilme

becerileri kazanılır.

---

## 💡 Kritik Not

Form alan adı değiştirildiğinde veri tabanındaki kolon otomatik güncellenmez. Bu nedenle:

> İsimlendirme en başta doğru planlanmalıdır.








# ▶️ Studio Run ile Uygulamayı Çalıştırmak

Bu ders, **Xpoda Studio** ortamında geliştirilen bir modülün **Studio Run** özelliği ile nasıl çalıştırıldığını ve Client tarafında nasıl görüntülendiğini açıklamaktadır.

Bu aşama, geliştirme sürecindeki en kritik test adımıdır.

---

## 🧩 Xpoda Mimarisi

Xpoda iki ana yapıdan oluşur:

### 1️⃣ Studio (Geliştirme Ortamı)

* Uygulamalar burada tasarlanır.
* Formlar oluşturulur.
* Modül yapısı planlanır.
* İş kuralları tanımlanır.

### 2️⃣ Client (Çalışma Ortamı)

* Kullanıcıların uygulamayı gördüğü ve kullandığı alandır.
* Formlar menüde görüntülenir.
* Veri giriş ve test işlemleri yapılır.

---

## ▶️ Studio Run Nedir?

**Studio Run**, geliştirilen modülü anlık olarak Client tarafında çalıştırmayı sağlar.

### Çalışma Mantığı:

1. Studio'da modül geliştirilir.
2. "Run" butonuna basılır.
3. Client tarafında modül aktif olur.
4. Modüldeki formlar menüde görünür.
5. Test işlemleri gerçekleştirilir.

Bu sayede deploy işlemi yapmadan hızlı test imkanı sağlanır.

---

## 🖥️ Client Kurulum Seçenekleri

### ☁️ Xpoda Cloud

* Client Xpoda Cloud sistemlerinde barındırılır.
* Hızlı başlangıç için idealdir.
* Ek sunucu kurulumu gerekmez.

### 🏢 On-Premise Kurulum

* Client ve veri tabanı müşterinin kendi server'ına kurulur.
* Maksimum veri güvenliği sağlanır.
* Kurumsal yapılar için tercih edilir.

---

## 🧪 Test Süreci

Studio Run ile:

* Formlar menüde otomatik listelenir.
* Veri girişleri yapılabilir.
* Akışlar test edilebilir.
* Hatalar hızlıca tespit edilir.

Bu yöntem, geliştirme sürecini hızlandırır ve anlık geri bildirim sağlar.

---

## ⚙️ Öğrenim Kazanımları

Bu ders sonunda:

* Studio ve Client farkını anlayabilme
* Run mantığını kavrayabilme
* Hızlı test süreçlerini uygulayabilme
* Cloud ve On-Premise farkını ayırt edebilme

becerileri kazanılır.

---

## 🎯 Kritik Nokta

Studio’da yapılan geliştirme, Run edilmeden kullanıcı tarafında görünmez.

> Geliştirme sürecinde her önemli değişiklik sonrası Run ile test yapılmalıdır.

---


