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

