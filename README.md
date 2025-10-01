# Bitcoin Günlük Rapor Otomasyonu

## Proje Açıklaması
Bu proje, Bitcoin fiyatlarını analiz eden ve günlük raporlar gönderen bir otomasyon sistemi olarak n8n kullanmaktadır. Proje, kullanıcıların Bitcoin piyasasındaki değişiklikleri takip etmelerine ve bu bilgileri e-posta raporları aracılığıyla almalarına olanak tanır.

## Özellikler
- **Gerçek Zamanlı Veri Analizi:** Bitcoin fiyatları anlık olarak analiz edilir.
- **Günlük E-posta Raporları:** Kullanıcılara günlük raporlar e-posta ile gönderilir.
- **Kullanıcı Dostu Arayüz:** n8n ile kolayca özelleştirilebilir bir otomasyon akışı sunar.
- **Esnek Yapı:** Kullanıcı ihtiyaçlarına göre özelleştirilebilen iş akışları sağlar.

## Kurulum Talimatları
1. **n8n Kurulumu:**
   - n8n uygulamasını [resmi web sitesinden](https://n8n.io) indirip kurun.
   - Alternatif olarak Docker kullanarak n8n'i başlatabilirsiniz:
     ```bash
     docker run -d --name n8n -p 5678:5678 n8nio/n8n
     ```

2. **Proje Dosyalarının İndirilmesi:**
   - Bu repository'yi klonlayın:
     ```bash
     git clone https://github.com/last-26/Bitcoin-Daily-Report-Automation.git
     ```
   - Proje dizinine gidin:
     ```bash
     cd Bitcoin-Daily-Report-Automation
     ```

3. **n8n Ayarları:**
   - n8n arayüzüne gidin (http://localhost:5678) ve gerekli ayarları yapın.
   - Bitcoin API anahtarınızı ve SMTP e-posta ayarlarınızı yapılandırın.

## İş Akışı Açıklaması
1. **Veri Toplama:**
   - Bitcoin fiyat verileri, belirlenen API'den alınır.

2. **Veri Analizi:**
   - Alınan veriler, belirli kriterlere göre analiz edilir.

3. **Rapor Oluşturma:**
   - Günlük rapor, analiz sonuçlarını içerecek şekilde oluşturulur.

4. **E-posta Gönderimi:**
   - Oluşturulan rapor, kullanıcının belirttiği e-posta adresine gönderilir.

## Kullanım Kılavuzları
- **Otomasyonu Başlatma:** n8n arayüzünde oluşturduğunuz iş akışını başlatın.
- **Raporları Kontrol Etme:** E-posta hesabınızı kontrol ederek günlük raporları alıp almadığınızı doğrulayın.
- **Hata Ayıklama:** Herhangi bir sorunla karşılaşırsanız, n8n loglarını kontrol edin ve hata ayıklama adımlarını izleyin.

Bu proje, Bitcoin fiyatlarını analiz etmenin ve bu bilgileri etkin bir şekilde iletmenin güçlü bir yolunu sunmaktadır. Herhangi bir sorun veya öneriniz varsa, lütfen iletişime geçin!