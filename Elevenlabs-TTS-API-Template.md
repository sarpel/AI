Elbette, istediğiniz bilgileri sağlanan URL ve fotoğraftan derleyerek aşağıda Markdown formatında sunuyorum. Görüntüyü doğrudan iyileştiremem veya bulanıklığı gideremem ancak API referansını inceleyerek tüm gerekli bilgileri sizin için hazırladım.

---

### **ElevenLabs Metinden Sese (Text-to-Speech) API Referansı**

Bu API, metni seçilen bir sesi kullanarak konuşmaya dönüştürür ve bir ses dosyası olarak döndürür.

#### **Endpoint**

- **Metod:** `POST`
- **URL:** `https://api.elevenlabs.io/v1/text-to-speech/{voice_id}`

---

#### **Gerekli Parametreler**

Fotoğrafta ve dokümantasyonda belirtilen gerekli alanlar şunlardır:

| Parametre Türü | Anahtar | Değer Türü | Açıklama | Örnek Değer (Fotoğraftan) |
| :--- | :--- | :--- | :--- | :--- |
| **Header** | `xi-api-key` | string | API anahtarınız. | `sk_61a1d13cb2aa07c...` |
| **Path** | `voice_id` | string | Kullanılacak sesin kimliği (ID). | `xsGHrtxT5AdDzyXTQTOd` |
| **Body** | `text` | string | Konuşmaya dönüştürülecek metin. | `"Bir zamanlar, çok uzak bir ülkede, Ayşe adında çok akıllı ve cesur bir kız yaşar."` |

---

#### **İsteğe Bağlı Parametreler (Body & Query)**

Aşağıda fotoğrafta yapılandırılmış olan isteğe bağlı parametreler ve açıklamaları bulunmaktadır.

| Parametre Türü | Anahtar | Değer Türü | Açıklama | Örnek Değer (Fotoğraftan) |
| :--- | :--- | :--- | :--- | :--- |
| **Query** | `output_format` | enum | Oluşturulacak sesin formatı. Varsayılan: `mp3_44100_128`. | `mp3_44100_128` |
| **Body** | `model_id` | string | Kullanılacak modelin kimliği. Varsayılan: `eleven_multilingual_v2`. | `eleven_multilingual_v2` |
| **Body** | `voice_settings`| object | Ses ayarlarını içeren bir nesne. | |
| | ┕ `stability` | double | Sesin değişkenliğini kontrol eder. Daha yüksek değerler daha stabil, daha düşükler daha etkileyici bir konuşma üretir. | `0.75` |
| | ┕ `similarity_boost`| double | Orijinal sese olan benzerliği artırır. Yüksek değerler sese daha sadık kalır. | `0.75` |
| | ┕ `style` | double | Konuşma stilinin ne kadar abartılacağını belirler. | `0` |
| | ┕ `use_speaker_boost`| boolean | Konuşmacı artırma özelliğini etkinleştirir. | `true` |
| | ┕ `speed` | double | Konuşma hızını ayarlar. | `0.9` |
